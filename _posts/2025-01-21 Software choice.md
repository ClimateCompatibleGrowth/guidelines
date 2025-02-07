---
layout: post
title:  "Software choice"
date:   2025-01-21
author: Alva Sarby
category: practice
tags: repeatability reusability 
---

How do I choose the right software for my upcoming research project? This is a question that I, like many others before me, had to ask today. In the project description for my PhD thesis, Aspen Plus was listed as the modeling tool to use and my supervisors and colleagues all use Aspen Plus. But Aspen Plus is not an open access software and an Aspen Plus license is very expensive. Hence, I am currently in a position where I must carefully think through which software is the most appropriate for my project. I have to weigh the advantages and disadvantages of using commercial or open software.

[Aspen Plus][4] is a process modeling tool used to build and simulate processes. As mentioned, it is not an open software, but alternative open access tools exist, for example, [DWSIM][5] and [COCO Simulator][6]. As I need to choose one of these software to use, I will discuss the advantages and disadvantages of using Aspen Plus and compare them to DWSIM and COCO Simulator's advantages and disadvantages.   

## Advantages of using Aspen Plus
- Knowledge and support available from supervisor and collegues. Also a broad user base online in many forums available to help me. 
- My own existing knowledge: I don't have to completely learn a new coding language or software
- Often used in industry
    - Valuable knowledge to have for me (on my CV)
- My research field often (a majority of the time?) use Aspen Plus (especially compared to an open software)
- Wide range of applications
- A lot of documentation, help, etc available for users
- COCO instead of Aspen: 
    - much smaller property data bank. It is hard work to enter and properly define components
    - not as powerful, some processes will not be modelled ([Ortega, n.d.-a][7])
    - Advanced users required ([Ortega, n.d.-a][7])
- DWSIM instead of Aspen:
    - not as powerful, no support center, 

From this source: ([Ortega, n.d.-b][8]) 
- "Aspen Plus (AP for short) is the leading Chemical Process Simulator in the market (or at least in the Chemical Engineering World)" ([Ortega, n.d.-b][8])
    - "One of the best advantages is that Aspen Plus has already an existing data base of of species and their pure/binary regressed parameters. It can also handle very complex processes "
- A good and intuative interface

One of the biggest advantages of using Aspen Plus is the support available in my vicinity, my supervisor and colleagues all know Aspen Plus. Additionally, Aspen Plus provides extensive "Help" documentation and since so many uses Aspen Plus, a lot of information, tutorials, and help can be found online. Furthermore, I already have a basic understanding of the software, making the time to learn the software shorter than if I would start from the beginning with a new software. Another considerable advantage of Aspen Plus is its extensive property data bank ([Ortega, n.d.-b][8]) which makes modeling much faster and more accurate as finding accurate data about all chemicals used in a simulation can be tedious and sometimes even impossible. Furthermore, Aspen Plus supports a wide range of applications and is the leading chemical process simulator on the market for chemical engineers. It is frequently used in industry and research, hence, learning Aspen Plus may give me important knowledge for future jobs or research positions.   

Both COCO simulator and DWSIM are not as powerful as Aspen Plus with COCO Simulator having a small property database and requiring advanced users, and DWSIM lacking a support center. 

## Disadvantages to using Aspen Plus
- Not an open software - harder for others to reuse my findings
- Expensive license: "Unfortunately, the cost of a single license varies from 30K to more than 100K depending on the industry and market" ([Ortega, n.d.-b][8])
- What if I want to use parts of my project after I am done with my PhD?
- Can I use version control with Aspen? I believe no
- Possible other open software: COCO and DWSIM
- COCO
    - Free, friendly userface, has pleny of pre-existing unit operations and simulations available ([Ortega, n.d.-a][7])
    - Interoperable
- DWSIM
    - open source, free, may integrate python scrips, Sensitivity Analysis & Optimizers! ([Ortega, n.d.-a][7])
    - interoperable

The biggest disadvantages with using Aspen Plus are the fact that it isn't an open access software and has a very expensive license. This makes it harder for me and others to reuse and build upon my work. Moreover, it is not possible to use version control with Aspen Plus, reducing my research potential to follow the CCG [Good Enough Practices][9] for open science. As mentioned, COC Simulator and DWSIM are open access alternatives for Aspen Plus. Their openness and interoperability are their largest advantages over Aspen Plus. COCO Simulator has a user-friendly interface and plenty of unit operations already in place. DWSIM can be integrated with python and contains optimizers and sensitivity analysis tools. 

## Discussion


Everything beneath: delete?
## Useful resources
?


 ([Gobel et al (2020)][1])

------------
*This material is derived from the [CCG review of good enough practices][2], released under a [CC-BY 4.0 license][3].*

[1]: <https://direct.mit.edu/dint/article/2/1-2/108/10003/FAIR-Computational-Workflows> "Goble, C., Cohen-Boulakia, S., Soiland-Reyes, S., Garijo, D., Gil, Y., Crusoe, M.R., Peters, K., Schober, D., 2020. FAIR Computational Workflows, *Data Intelligence*, vol. 2, no. 1–2, 1135 pp. 108–121. DOI: 10.1162/dint_a_00033."
[2]: https://doi.org/10.5281/zenodo.5911546 "Usher, William, Beltramo, Agnese, Gardumi, Francesco, Martin, Viktoria, & Petrarulo, Luca. (2022). CCG Platform - Body of Knowledge: Review of Good Practice (1.3). Zenodo. https://doi.org/10.5281/zenodo.5911546"
[3]: https://creativecommons.org/licenses/by/4.0/legalcode
[4]: https://www.aspentech.com/en/products/engineering/aspen-plus 
[5]: https://dwsim.org/ 
[6]: https://www.cocosimulator.org/ 
[7]: <https://chemicalengineeringguy.com/the-blog/process-simulation/free-alternatives-to-aspen-plus-hysys/>  "Ortega, E. (n.d.-a). Free alternatives to Aspen Plus & HYSYS? ChemEngGuy. Retrieved February 7, 2025, from https://chemicalengineeringguy.com/the-blog/process-simulation/free-alternatives-to-aspen-plus-hysys/ " 
[8]:<https://chemicalengineeringguy.com/the-blog/process-simulation/what-is-aspen-plus/> "Ortega, E. (n.d.-b). What is Aspen Plus? ChemEngGuy. Retrieved February 7, 2025, from https://chemicalengineeringguy.com/the-blog/process-simulation/what-is-aspen-plus/"
[9]: https://climatecompatiblegrowth.github.io/guidelines/ 

