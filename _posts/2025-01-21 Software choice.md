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
One of the biggest advantages of using Aspen Plus is the support available in my vicinity, my supervisor and colleagues all know Aspen Plus. Additionally, Aspen Plus provides extensive "Help" documentation and since so many uses Aspen Plus, a lot of information, tutorials, and help can be found online. Furthermore, I already have a basic understanding of the software, making the time to learn the software shorter than if I would start from the beginning with a new software. Another considerable advantage of Aspen Plus is its extensive property data bank ([Ortega, n.d.-b][8]) which makes modeling much faster and more accurate as finding accurate data about all chemicals used in a simulation can be tedious and sometimes almost impossible. Furthermore, Aspen Plus supports a wide range of applications and is the leading chemical process simulator on the market for chemical engineers. It is frequently used in industry and research, hence, learning Aspen Plus may give me important knowledge for future jobs or research positions.   

Both COCO simulator and DWSIM are not as powerful as Aspen Plus and has no support center ([Ortega, n.d.-a][7]). Furthermore, COCO Simulator requires advanced users ([Ortega, n.d.-a][7]). 

## Disadvantages of using Aspen Plus
The biggest disadvantages with using Aspen Plus are the fact that it isn't an open access software and has a very expensive license. This makes it harder for me and others to reuse and build upon my work. Moreover, it is not possible to use version control with Aspen Plus, reducing my research potential to follow the CCG [Good Enough Practices][9] for open science. As mentioned, COCO Simulator and DWSIM are open access alternatives for Aspen Plus. Their openness and interoperability are their largest advantages over Aspen Plus. COCO Simulator has a user-friendly interface and plenty of unit operations already in place. DWSIM can be integrated with python and contains optimizers and sensitivity analysis tools. 

## Discussion and Conclusion
When looking at the advantages and disadvantages, it seems clear to me that using Aspen Plus is the clear choice. The support from colleagues, the help documentation, and online, as well as Aspen Plus's extensive properties database really tips the scale towards Aspen Plus. While COCO Simulator and DWSIM have the big advantages of openness, one must consider if the extra time requirement for making the research further open is worth it. Furthermore, everything except openness and interoperability that COCO Simulator and DWSIM brings, Aspen Plus does better. Hence, I unfortunately don't think it is worth it to use an open software instead of Aspen Plus this time.   



## Useful resources

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

