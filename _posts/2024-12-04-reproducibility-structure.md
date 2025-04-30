---
layout: post
title: Setting up a reproducible and reusable workflow using GitHub
date: 2024-12-04
author: Emir Fejzić
category: knowledge
tags: reusability reproducibility
---

Setting up a reproducible and reusable workflow using GitHub after creating an energy model and publishing an article makes it challenging to understand how others, unfamiliar with your model, perceive the repository's reproducibility.

In this post, Emir Fejzić offers insights on handling the reproducibility of model workflows stored in GitHub repositories. The answers come from an interview with Muhammad Eliasinul Islam, who recreated the workflow of the DRB-OSeMOSYS-model repository [1] on his computer and answered three selected questions.

# To what extent did you find the repository to be reproducible? Did you identify any data gaps needed to reproduce the work?

Although the repository shows some reproducibility, several areas need improvement to enhance it further. Users must follow detailed steps to reproduce the work, especially those unfamiliar with the data sources and tools, as they might struggle with troubleshooting. We need to modularize the code to allow users to upgrade specific parts to improve it. Additionally, we should standardize the directory structure, as even minor inconsistencies can be noticeable. Furthermore, we should separate reusable functions from the main workflow and central functions and repackage these reusable functions as a local package that can be installed via pip (pip install .), which would significantly aid in achieving a higher level of reproducibility.

# How can we improve the repository to increase the reproducibility of the work?

To enhance the reproducibility of the repository, we should start by providing comprehensive instructions on setting up Windows Subsystem for Linux (WSL). Follow this with a detailed guide on setting up the environment using Docker to ensure a consistent and isolated setup across different systems. Additionally, illustrating the workflow at both a high level and script level will help users understand the processes involved and how to execute them effectively. Finally, we should extend community outreach through thorough documentation on how users can apply and modify the model for their regions, which will improve reproducibility and foster a collaborative environment where shared knowledge and user contributions enhance the overall quality and applicability of the work.

# Recognizing that energy modelling is a complex field, what are the most common mistakes researchers make that diminish reproducibility when setting up GitHub repositories or Zenodo deposits for their work?

Energy modelling's complexity often leads to several common mistakes that diminish reproducibility when setting up GitHub repositories or Zenodo deposits. Researchers often create ambiguous and poorly documented data supply chains, which are not automated and lack clear instructions, making it difficult for others to replicate the work. Additionally, they frequently fail to streamline, standardize, or modularize the transformation of raw or downloaded data into model-ready data, relying on one-time-use codes that are not easily adaptable or reusable. Furthermore, insufficient documentation of simplification choices made during the modelling process, their impact on the model, and guidance on upgrading parts of the code for improvements hamper understanding of the model's scalability and modularity. Lastly, the lack of comprehensive troubleshooting documentation for environment setup often frustrates non-experts and enthusiasts, as they struggle to resolve issues and mimic model runs from GitHub, further impeding reproducibility.

# Conclusions

The reproducibility attempt reveals that while the energy model repository demonstrates some level of reproducibility, it requires several enhancements to improve further. Key aspects needing attention include:
**Detailed Documentation:** Providing comprehensive setup instructions for Windows Subsystem for Linux (WSL) and Docker to ensure users can create a consistent and isolated environment.
**Modularization of Code:** Reorganizing the code into modular components to allow users to upgrade specific parts easily and to package reusable functions as installable modules.
**Standardizing Directory Structure:** Ensuring a consistent directory structure to minimize confusion and improve workflow clarity.
**Enhanced Workflow Illustration:** Offering both high-level and script-level overviews of the workflow to aid user understanding and execution.
**Community Outreach and Documentation:** Extending documentation on applying and modifying the model for various regions to promote community engagement and collaborative improvements.

[1]: <https://github.com/EmiFej/DRB-OSeMOSYS-model.git>
