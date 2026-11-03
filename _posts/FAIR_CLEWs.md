---
layout: post
title:  "How FAIR is CLEWs?"
date:   2026-11-03
author: Camilla Lo Giudice
category: open-access
tags: models, clews, FAIR
---

# How FAIR is CLEWs?

Modelling has traditionally been a closed process, preventing users from validating the data, assumptions, and code underpinning modelling results. The introduction of open-source models has helped democratise access to modelling, allowing anyone to “open” the modelling black box. To ensure that models and scientific software are accessible to the wider public, they should follow the FAIR principles (Wilkinson et al., 2016): Findable, Accessible, Interoperable, and Reusable. This blog post briefly discusses the Open Science practices adopted within the Climate-Land-Energy-Water Systems (CLEWs) framework, developed using the energy system model OSeMOSYS, by examining the extent to which publicly available models follow the FAIR principles.

## Findable
To be findable, data must be accurately described, documented, and indexed in searchable resources. CLEWs modellers commonly use open documentation platforms, such as Read the Docs (Shivakumar, 2020), open-access research repositories, such as Zenodo (Lo Giudice, 2026), to share input datasets and references used to develop their models, and open-source code hosting platforms, such as GitHub (Heredia-Fonseca et al., 2025).

## Accessible

Accessibility refers to the retrievability of data and metadata, which should remain accessible even when the original data are no longer available. The previously mentioned platforms and repositories help strengthen accessibility in this regard. By making code publicly available, they ensure that the links and references used to develop a model remain accessible, even if the original reference data are no longer available. Moreover, the latest updates to the Modelling User Interface (MUIO), widely used for model development (Alexander et al., 2025), allow developers to store code, input data files, and results in a single .zip folder, which can be easily imported and analysed by other users. This practice further increases transparency by allowing entire models to be shared through open-access repositories.

## Interoperable
Interoperability means that CLEWs modellers use a formal, accessible, and shared language across the modelling community. While the practices described above are widely adopted, the community is still struggling to establish a commonly agreed language for representing modelling technologies and commodities. For instance, Shivakumar (2020) and the CLEWs open learning course (The Open University, 2026) use numerical codes to identify crops, whereas more recent studies, such as Lo Giudice (2026), and UNDESA training materials (UNDESA, n.d.) follow the naming conventions adopted by the Global Agro-Ecological Zoning framework (FAO & IIASA, 2025). Furthermore, these conventions differ from those adopted by Integrated Assessment Models (IAMs), potentially limiting the integration of CLEWs models into broader assessment studies, such as those informing the IPCC.

## Reusable 

Models are reusable when they are released under an accessible licence and can be easily reproduced. CLEWs models are often shared under the Creative Commons Attribution 4.0 International (CC BY 4.0) licence, which allows anyone to copy and redistribute the material in any medium or format, as well as transform and build upon it, including for commercial purposes. Moreover, the accessible user interface reduces coding barriers and facilitates reproducibility by allowing users to import and work with shared model folders.

### References 

Alexander, K., Tan, N., Gardumi, F., Plazas-Nino, F., Kuling, K., Ramos, E., Martindale, L., & Foster, V. (2025). Analysing the development of the climate, land, energy, and water systems (CLEWs) modelling framework: A state-of-the-art review. Environmental Research: Climate, 4(3), 032001. https://doi.org/10.1088/2752-5295/adf504

FAO & IIASA. (2025). Global Agro-ecological Zoning version 5 (GAEZ v5) Model Documentation. GitHub. https://github.com/un-fao/gaezv5/wiki

Heredia-Fonseca, R., Gardumi, F., & Usher, W. (2025). Exploring interlinkages in land, energy, and water in cooking and agriculture sectors: A case study in Kenya. Energy Nexus, 17, 100366. https://doi.org/10.1016/j.nexus.2025.100366

Lo Giudice, C. (2026). Exploring the impact of seasonal water variability on agricultural planning: A water-energy-food nexus perspective - OSeMOSYS models. https://doi.org/10.5281/zenodo.21869230

Shivakumar, A. (2020). CLEWS Ethiopia Model documentation. CLEWS Ethiopia Model. https://clews-ethiopia-model.readthedocs.io/en/latest/

The Open University. (2026). Introduction to CLEWs. OpenLearn Create. https://www.open.edu/openlearncreate/course/view.php?id=17727

UNDESA. (n.d.). Introduction to CLEWs | Department of Economic and Social Affairs. Retrieved 3 November 2026, from https://capacity.desa.un.org/article/introduction-clews

Wilkinson, M. D., Dumontier, M., Aalbersberg, Ij. J., Appleton, G., Axton, M., Baak, A., Blomberg, N., Boiten, J.-W., da Silva Santos, L. B., Bourne, P. E., Bouwman, J., Brookes, A. J., Clark, T., Crosas, M., Dillo, I., Dumon, O., Edmunds, S., Evelo, C. T., Finkers, R., … Mons, B. (2016). The FAIR Guiding Principles for scientific data management and stewardship. Scientific Data, 3(1), 160018. https://doi.org/10.1038/sdata.2016.18

