---
layout: post
title: Developing a scientific workflow, the case of OnStove
date: 2023-09-27
author: Camilo Ramirez
category: knowledge
---

In this post, I will describe how a [Snakemake](https://snakemake.readthedocs.io/en/stable/)
automated workflow is applied to the open-source spatial clean cooking tool
[OnStove](https://github.com/Open-Source-Spatial-Clean-Cooking-Tool/OnStove).

## Content

1. [What is the `OnStove` tool?](#onstove)
2. [The automated workflow structure](#workflow)
   1. [The `process_data` rule](#process_data)
   2. [The `prepare_model` rule](#prepare_model)
   3. [The `run_model` rule](#run_model)
   4. [The `merge_results` rule](#merge_results)
5. [Conclusion](#conclusion)

## What is the OnStove tool? <a name="onstove"></a>

<img src="{{site.baseurl}}/assets/img/OnStoveLogo.svg" alt="OnStove logo" width="200"/>

OnStove is a geospatial modelling tool that allows users to determine the net-benefit of different
cooking stoves relative to a stated baseline. Net-benefit, in this case, is defined as all the
achieved benefits minus all the incurred costs of transitioning to a cleaner cooking option.

OnStove is written in an open-source programming language (Python) with
thorough use of version control, and published in Github under an open license. It
uses automated workflows that are run using [Snakemake](https://snakemake.readthedocs.io/en/stable/).
It is thoroughly documented with automated documentation generated using Sphinx and
published openly in [Read The Docs](https://about.readthedocs.com/?ref=readthedocs.com).
Moreover, it uses automated unitary tests that enhance the software's stability and
allow for more robust collaboration.

To date, the tool has been launched in a [major publication][1] for sub-Saharan Africa published in
the Nature Sustainability journal. Moreover, several publications are forthcoming analysing
clean cooking transitions in Nepal and Kenya.

## The automated workflow structure <a name="workflow"></a>
To make our research truly reproducible, we implement automated workflows. These workflows are used
to automate and make clear in which order all computational processes are run. This process covers
steps from reading and processing of raw data, to final production and visualization of results.

We use the [Snakemake](https://snakemake.readthedocs.io/en/stable/) package to manage our
workflows. Snakemake simplifies our data analysis pipelines by allowing us to create clear rules
defining the order, inputs dependency and outputs of each computational step. This way, we can build
modular and more scalable software that comes together in the workflow process. I will show next
the main workflow we use to run the OnStove model for all sub-Saharan countries and broadly explain
how it is constructed and what each step does. For more detailed information on how to build a
Snakemake workflow, please visit the [documentation](https://snakemake.readthedocs.io/en/stable/).

The workflow consists of four main steps, which are run through four rules: `process_data`, `prepare_model`,
`run_model`, and `merge_results`. I will explain each rule in detail in the sections below.

<figure>
  <img src="{{site.baseurl}}/assets/img/OnStoveDag.svg" alt="OnStove's workflow directed acyclic graph (DAG)"/>
  <figcaption>
    <strong>OnStove's workflow directed acyclic graph (DAG):</strong> shows the conceptual
    representation and order of computational steps of the model.
  </figcaption>
</figure>

We begin the workflow by defining the scenarios we want to run and store that in a list
``SCENARIOS``. Then we create another list with all the ``COUNTRIES`` of the study area we want
to run, and any other required parameter as ``RESTRICTION``. Then the first rule we want to
create is the "final" rule that we call ``all``. This rule will tell Snakemake what is the
expected output of the entire workflow, and we define that output as an ``input`` to the rule. In
this case, it is a final ``results.pkl`` file for Africa for each scenario in ``SCENARIOS``.

```python
import os
cwd = os.getcwd()

SCENARIOS = ['Social_private_benefits', 'Private_benefits']
RESTRICTION = ['Positive_Benefits']

COUNTRIES = ['AGO', 'BDI', 'BEN', 'BFA', 'BWA', 'CAF', 'CIV', 'CMR',
             'COD', 'COG', 'DJI', 'ERI', 'ETH', 'GAB', 'GHA', 'GIN',
             'GMB', 'GNB', 'GNQ', 'KEN', 'LBR', 'LSO', 'MDG', 'MLI',
             'MOZ', 'MRT', 'MWI', 'NAM', 'NER', 'NGA', 'RWA', 'SDN',
             'SEN', 'SLE', 'SOM', 'SSD', 'SWZ', 'TCD', 'TGO', 'TZA',
             'UGA', 'ZAF', 'ZMB', 'ZWE']

rule all:
    input:
        expand("Results/Africa/{scenario}/{restriction}/results.pkl",
               scenario=SCENARIOS,
               restriction=RESTRICTION)
```

Then we need to create all intermediate rules required to go from raw data processing until
generating the desired final output files.

### The `process_data` rule <a name="process_data"></a>
The first rule we need is a ``process_data`` one,
where we read and process a set of geospatial datasets. All this datasets should already be
downloaded into the system and organized in the specified folder structure. In the
[documentation](https://onstove-documentation.readthedocs.io/en/latest/?badge=latest) of
the model we provide links to the raw data sources and information on how to use them.
Each dataset is then specified as an individual input for the rule.

Note that, somethimes we use
[wildcards](https://snakemake.readthedocs.io/en/stable/snakefiles/rules.html)
when defining the path of a dataset. This is done to generalize one rule to different
input datasets. Take the case of the `population` input in the `process_data` rule for example,
it contains the wildcard `{country}` in its path. From this, Snakemake can then infer which are
the countries that need to be run based on the amount of `population` datasets found in the
`Population` data folder.

After the ``input`` we define any parameter needed for the analysis
in the ``params`` section. These are parameters that can be used within the defined
``script``.  Next, we define the expected ``output`` files after the rule was run.
Snakemake will use these information to check that the rule was run successfully and
track that the output files are up-to-date. Finally, we specify in the ``script`` section,
a python script that should be run in order to perform the desired data processing and
processing the ``output`` files.

```python
rule process_data:
    input:
         population = "GIS-data/Population/{country}_ppp_2020_UNadj_constrained.tif",
         mask_layer = r"GIS-data\Admin\Admin_1.shp",
         ghs = r"GIS-data\Urban\Urban.tif",
         forest = "GIS-data/Forest/{country}/Forest.tif",
         walking_friction = r"GIS-data\Walking_friction\walking_friction.tif",
         hv_lines = r"GIS-data\HV\All_HV.shp",
         mv_lines = r"GIS-data\MV\All_MV.gpkg",
         ntl = r"GIS-data\NightLights\Africa.tif",
         traveltime_cities = r"GIS-data\Traveltime_to_cities\2015_accessibility_to_cities_v2.tif",
         roads = r"GIS-data\Roads/{country}/Roads.shp",
         temperature = r"GIS-data\Temperature\Temperature.tif",
         buffaloes = r"GIS-data\Global livestock\buffaloes\buffaloes.tif",
         cattles = r"GIS-data\Global livestock\cattles\cattles.tif",
         poultry = r"GIS-data\Global livestock\poultry\poultry.tif",
         goats = r"GIS-data\Global livestock\goats\goats.tif",
         pigs = r"GIS-data\Global livestock\pigs\pigs.tif",
         sheeps = r"GIS-data\Global livestock\sheeps\sheeps.tif",
         water = r"GIS-data\Water scarcity\y2019m07d11_aqueduct30_annual_v01.gpkg"
    params:
          output_directory = "Processed data/{country}",
          country = "{country}"
    output:
          mask_layer = "Processed data/{country}/Administrative/Country_boundaries/Country_boundaries.geojson",
          population = "Processed data/{country}/Demographics/Population/Population.tif",
          ghs = "Processed data/{country}/Demographics/Urban/Urban.tif",
          forest = "Processed data/{country}/Biomass/Forest/Forest.tif",
          biomass_friction = ".Processed data/{country}/Biomass/Friction/Friction.tif",
          mv_lines = "Processed data/{country}/Electricity/MV_lines/MV_lines.geojson",
          ntl = "Processed data/{country}/Electricity/Night_time_lights/Night_time_lights.tif",
          traveltime_cities = "Processed data/{country}/LPG/Traveltime/Traveltime.tif",
          roads = "Processed data/{country}/LPG/Roads/roads.geojson",
          temperature = "Processed data/{country}/Biogas/Temperature/Temperature.tif",
          buffaloes = "Processed data/{country}/Biogas/Livestock/buffaloes/buffaloes.tif",
          cattles = "/Processed data/{country}/Biogas/Livestock/cattles/cattles.tif",
          poultry = "Processed data/{country}/Biogas/Livestock/poultry/poultry.tif",
          goats = "Processed data/{country}/Biogas/Livestock/goats/goats.tif",
          pigs = "Processed data/{country}/Biogas/Livestock/pigs/pigs.tif",
          sheeps = "Processed data/{country}/Biogas/Livestock/sheeps/sheeps.tif",
          water = "Processed data/{country}/Biogas/Water scarcity/Water scarcity.tif"
    script:
          "scripts/data_processing.py"
```

### The `prepare_model` rule <a name="prepare_model"></a>
After all raw data has been processed, then we can crate and calibrate our OnStove model. We
define the ``prepare_model`` rule for this. This rule reads in the raw data processed in the
``process_data`` rule, plus additional techno-economic information of the study area. Then
it runs the ``model_preparation.py`` script to create and calibrate the model. The ``output``
of this script is a ``model.pkl`` file containing all the information of our model.

```python
rule prepare_model:
   input:
        prep_file = "Prep_files/{country}_prep_file.csv",
        techs_file = r"Technical_specs\{scenario}\{country}_file_tech_specs.csv",
        mask_layer = rules.process_data.output.mask_layer,
        population = rules.process_data.output.population,
        ghs = rules.process_data.output.ghs,
        forest = rules.process_data.output.forest,
        biomass_friction = rules.process_data.output.biomass_friction,
        mv_lines = rules.process_data.output.mv_lines,
        ntl = rules.process_data.output.ntl,
        traveltime_cities = rules.process_data.output.traveltime_cities,
        roads = rules.process_data.output.roads,
        temperature = rules.process_data.output.temperature,
        water = rules.process_data.output.water,
        buffaloes = rules.process_data.output.buffaloes,
        cattles = rules.process_data.output.buffaloes,
        poultry = rules.process_data.output.poultry,
        goats = rules.process_data.output.goats,
        pigs = rules.process_data.output.pigs,
        sheeps = rules.process_data.output.sheeps
   params:
         wealth_index = r"GIS-data\Poverty\{country}_relative_wealth_index",
         output_directory = "Results/{country}/{scenario}",
         country = "{country}"
   output:
         model = "Results/{country}/{scenario}/model.pkl"
   script:
         "scripts/model_preparation.py"
```

### The `run_model` rule <a name="run_model"></a>
Next, we define a ``run_model`` rule, where we read in the prepared model file ``model.pkl``
and additional scenario data for each specific country. The output expected is a ``results.pkl``
file for each country, which are produced by the ``model_run.py`` script.

```python
rule run_model:
   input:
        model = rules.prepare_model.output.model,
        scenario_file = r"Results\Scenario_files\{scenario}\{country}_scenario_file.csv"
   params:
         output_directory = "Results/{country}/{scenario}/{restriction}",
         country = "{country}",
         restriction = "{restriction}"
   output:
         results = "Results/{country}/{scenario}/{restriction}/results.pkl",
   script:
        "scripts/model_run.py"
```

### The `merge_results` rule <a name="merge_results"></a>
Finally, after having all result files for all countries, the ``merge_results`` rule takes care
of reading all countries results and merging them into a large Africa model. The expected
``output`` is a ``results.pkl`` file for Africa.

```python
rule merge_results:
   input:
        results = expand("Results/{country}/{{scenario}}/{{restriction}}/results.pkl",
                         country=COUNTRIES),
        boundaries = r"GIS-data\Admin\Admin_1.shp"
   params:
         output_directory = "Results/Africa/{scenario}/{restriction}",
         countries = COUNTRIES
   output:
         results = "Results/Africa/{scenario}/{restriction}/results.pkl"
   script:
         "scripts/merge_results.py"
```

After this workflow has completed successfully, then we run another workflow that generates all the
results visualizations. We will not cover that script in here but it is available in our
[GitHub repository](https://github.com/Open-Source-Spatial-Clean-Cooking-Tool/OnStove).

## Conclusion <a name="conclusion"></a>
This post has provided a comprehensive overview of how an automated workflow,
powered by Snakemake, is effectively applied to the open-source spatial clean cooking tool `OnStove`.
One notable feature of Snakemake is its ability to execute rules in parallel for the different countries,
this optimizes workflow efficiency by leveraging available CPU cores and RAM resources.

In summary, this workflow not only streamlines the entire process of assessing clean cooking
solutions but also ensures reproducibility, scalability, and ease of collaboration. By integrating
Snakemake and OnStove, we can analyse and visualize the impact of clean cooking transitions
across sub-Saharan Africa efficiently and comprehensively.

[1]: https://doi.org/10.1038/s41893-022-01039-8 "Khavari, B., Ramirez, C., Jeuland, M., & Fuso Nerini, F. (2023). A geospatial approach to understanding clean cooking challenges in sub-Saharan Africa. Nature Sustainability. https://doi.org/10.1038/s41893-022-01039-8."

