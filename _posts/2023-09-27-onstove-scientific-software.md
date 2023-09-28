---
layout: post
title: The OnStove scientific software
date: 2023-09-27
author: Camilo Ramirez
category: output
---

In this post, I will describe how different practices of Open Science are applied
to the open-source spatial clean cooking tool [OnStove](https://github.com/Open-Source-Spatial-Clean-Cooking-Tool/OnStove). 

## Content
1. [Version control and Github](#Version-control-and-Github)
2. [Automated workflows](#Automated-workflows)
3. [Documentation](#Documentation)
   1. [Writting proper docstrings](#Writting-proper-docstrings)
   2. [Generating documentation with Sphinx](#Generating-documentation-with-Sphinx)
   3. [Publishing on ReadTheDocs](#Publishing-on-ReadTheDocs)
4. [Testing](#Testing)
   1. [Unitary tests](#Unitary-tests)
   2. [Automated testing workflows](#Automated-testing-workflows)
5. [Data availability](#Data-availability)
6. [Code availability](#Code-availability)
7. [Making a release in conda-forge](#Making-a-release-in-conda-forge)

OnStove is written in an open-source language (Python) with 
thorough use of version control, and published in Github under an open license. It 
uses automated workflows that are runned using Snakemake. It is thoroughly documented with automated
documentation generated using Sphinx and published openly in ReadTheDocs. Moreover, it uses automated 
unitary tests that enhance the software's stability and allow for more robust collaboration. 

To date, the tool has been launched in a [major publication][1] for sub-Saharan Africa, published in
the Nature Sustainability journal. Moreover, several publications are forthcomming analysing country 
cases clean cooking transitions (e.g. Nepal and Kenya).

## Version control and Github 

Version control is an indispensable asset in OnStove's development. It enables 
us to preserve our work, collaborate seamlessly among researchers, troubleshoot errors 
effectively, and continuously improve our model. This way, we foster transparent and open science by 
facilitating code sharing and reproducibility while keeping research organized and efficient. 
To learn more, read this related post about [version control]({% post_url 2021-01-01-version-control %}).

In OnStove, we use Git as version control system and Github as version control platform to host 
the code of the model. With Git we track all changes and new additions to the model safely, keeping 
the entire history of our code at hand and available to everyone. This brings transparency to our work 
and forsters collaboration. We normally make use of branches to develop different functionalities of 
the model, keeping everything contained and organized. This also minimizes conflics when mergin changes 
to the main branch of the code. 

![network]({{ site.baseurl }}/assets/img/network.png)

GitHub, a leading platform for version control, plays a pivotal role in the scientific community's 
embrace of this essential practice. Its user-friendly interface and collaborative features make it 
a hub for researchers to store, manage, and share their scientific software projects with ease. 
GitHub's branching and merging capabilities enable concurrent work on projects, fostering 
collaboration among scientists worldwide. Moreover, its issue tracking system simplifies debugging 
and project management. By leveraging GitHub, researchers not only ensure the longevity and 
reproducibility of their work but also contribute to the ethos of open science by making their 
code accessible to the broader scientific community. This integration of version control via GitHub 
empowers scientists to efficiently navigate the ever-evolving landscape of scientific research 
while promoting transparency and innovation. 

![project]({{ site.baseurl }}/assets/img/project.png)

## Automated workflows

Snakemake simplifies and streamlines complex data analysis pipelines by allowing researchers to define, 
execute, and manage workflows with ease. This powerful framework ensures reproducibility by specifying 
all dependencies and parameters explicitly. Researchers can effortlessly integrate software tools, 
data sources, and analysis steps into a unified pipeline, reducing the risk of errors and saving 
valuable time

## Documentation

Thorough documentation is the compass that guides researchers through the labyrinth of scientific 
software, ensuring clarity, reproducibility, and the sharing of knowledge.

### Writting proper docstrings

### Generating documentation with Sphinx

### Publishing on ReadTheDocs

## Testing

### Unitary tests

### Automated testing workflows

## Data availability

## Code availability

## Making a release in conda-forge


[1]: https://doi.org/10.1038/s41893-022-01039-8 "Khavari, B., Ramirez, C., Jeuland, M., & Fuso Nerini, F. (2023). A geospatial approach to understanding clean cooking challenges in sub-Saharan Africa. Nature Sustainability. https://doi.org/10.1038/s41893-022-01039-8."
