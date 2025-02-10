---
layout: post
title:  "Software choice"
date:   2025-01-21
author: Alva Sarby
category: practice
tags: repeatability reusability 
---
## Software choice: weighting practicality against openness
How do I choose the right software for my upcoming research project? This is a question that I, like many others before me, had to ask today. In the project description for my PhD thesis, Aspen Plus was listed as the modeling tool to use and my supervisors and colleagues all use Aspen Plus. But Aspen Plus is not an open access software and an Aspen Plus license is very expensive. Hence, I am currently in a position where I must carefully think through which software is the most appropriate for my project.

[Aspen Plus][4] is a process modeling tool used to build and simulate processes. As mentioned, it is not an open software and alternative open access tools exist, for example, [DWSIM][5] and [COCO Simulator][6]. As I need to choose one of these software to use, I will discuss the advantages and disadvantages of using Aspen Plus and compare them to DWSIM and COCO Simulator's advantages and disadvantages. As I document this process, I hope I can help future researchers in how to think around this problem.   

### Advantages of using Aspen Plus
One of the biggest advantages of using Aspen Plus is the support available in my vicinity, my supervisor and colleagues all know Aspen Plus. Additionally, Aspen Plus provides extensive "Help" documentation and since so many uses Aspen Plus, a lot of information can be found online. Furthermore, I already know the basics of the software, meaning I don't have to spend additional time on learning an unfamiliar software. Another considerable advantage of Aspen Plus is its extensive property data bank ([Ortega, n.d.-b][8]) which makes modeling much faster and more accurate. Finding correct data about the chemicals used in a simulation can be tedious and sometimes almost impossible. Furthermore, Aspen Plus supports a wide range of operations and is the leading chemical process simulator on the market for chemical engineers ([Ortega, n.d.-b][8]). It is frequently used in industry and research, hence, learning Aspen Plus may give me important knowledge for future jobs or research positions.   

Both COCO simulator and DWSIM are not as powerful as Aspen Plus and has no support center ([Ortega, n.d.-a][7]). Furthermore, COCO Simulator requires advanced users ([Ortega, n.d.-a][7]). 

### Disadvantages of using Aspen Plus
The biggest disadvantages with Aspen Plus is that it isn't an open access software and has a very expensive license. Moreover, version control cannot be used with Aspen Plus, reducing my research's potential to follow the [CCG Good Enough Practices][9] for open science. As mentioned, COCO Simulator and DWSIM are open access alternatives for Aspen Plus. Their openness and interoperability are their largest advantages over Aspen Plus. Moreover, COCO Simulator has a user-friendly interface and plenty of unit operations already in place. DWSIM can be integrated with python and contains optimizers and sensitivity analysis tools. 

### Discussion and Conclusion
When looking at the advantages and disadvantages, using Aspen Plus seems to be the right choice. The support from colleagues, online, and the "Help" documentation, as well as Aspen Plus's extensive properties database really favours using Aspen Plus. While COCO Simulator and DWSIM have the big advantages of openness, one must consider if the extra time making the research more open is worth spending. In this case, I unfortunately don't think it is.



 ### Useful resources

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

