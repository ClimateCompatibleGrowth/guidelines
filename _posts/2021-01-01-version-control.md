---
layout: post
title: Version Control
date: 2021-01-01
comments: true
author: Will Usher
category: practice
tags: ubuntu retrievability repeatability reusability reconstructability auditability
---

Version Control Systems record a history of changes to source code, data, or other text-based material
enabling collaboration between distributed teams of researchers.

Version control systems, such as Git, Mercurial and Subversion,
allow researchers to switch between these points in the development history
of the material that is being tracked,
view the differences between these points,
and create new modifications from any point in the history.
In short, version control provides "infinite levels of undo".

The history of changes is stored in a "repository".
A repository can be navigated using a command-line tool,
or a graphical-user interface.

Version control enables collaborative workflows
in either a centralised or distributed fashion,
which can effectively support scientific work.
Conflicts between changes can be resolved in a systematic fashion
because each change (or "commit") to content tracked by the version control system is recorded
with associated metadata that records the time, date, author, and a commit message.
This gives collaborators the freedom to work in parallel to one another,
make changes as they want and then merge their changes when they are ready.

The use of version control supports reproducibility and transparency
through the consistent and structured workflow necessary
for working with a VCS.
For example, messages associated with changes to the code ["commits"]
provide a running commentary on the development of the work itself.
Version control allows entire repositories to be easily shared,
facilitating the publishing of the work online,
through websites such as Github and Gitlab.

# Applying version control to software

Version Control is now seen as a cornerstone of reproducible computational research.
Recognising that even small changes to computer code
can have large unintended consequences
on the output of scientific software,
version control provides a structured and convenient means
to record which version of scientific software was used for a study.
The ability to easily switch between code versions
supports systematic approaches to debugging,
and the reproduction of results from different points in the project
[(Sandve et al., 2013)][3].

# Applying version control to data

Most version control systems are designed for management of source code,
which is text-based.

If data is stored as text,
for example in comma-separated value files (csv),
or as a [Frictionless Data Package][4],
then that data can be placed under version control.
This provides all the benefits listed above,
in terms of enabling collaboration
and providing a systematic process for updating and versioning the data.
Applying version control to data contributes to the findable,
accessible and reproducible aspects of the [FAIR principles][11].

There are also a number of tools that allow binary data to be placed
under version control including [Git-LFS][5],
which replaces large files with text pointers to the files stored on a server,
and [DVC][6], which was built for data scientists and machine learning projects.

# Applying version control to other material

Version control can be applied to any text-based material.
A version control *repository* can contain a mixture of text-based material
including computer code, data and documentation.
For example, some researchers use version control to facilitate collaboration on journal articles.
[Software Carpentry][9] use Github to host all of their teaching material.
Contributors use the collaboration features provided by the Git version control system,
and Github website to develop, organise and update teaching material.
The online teaching material "source code" is written in Markdown,
a mark-up language that allows contributors to style a web-page using simple syntax.
New ideas are submitted using the issue tracker where they are discussed and prioritised.
Contributions are submitted via a pull-request and reviewed by the administration team,
and finally merged into the main branch which holds the latest version of the material.
This material is then rendered on the respective course website.

# Further Reading and Next Steps

[The Turing Way](https://the-turing-way.netlify.app/welcome.html) has a section on version control.
To learn version control, there are many online courses available.
[Coderefinery][7] provide an ["Intro to Git"][8].
[Software Carpentry][9] also have a similar course ["Version Control with Git"][10].
Their materials are free to view and use, and they also run in-person and remote training.

---

This material is derived from the [CCG review of good enough practices][1]
which is released under a [CC-BY 4.0 license][2].

[1]: https://doi.org/10.5281/zenodo.5911546 "Usher, William, Beltramo, Agnese, Gardumi, Francesco, Martin, Viktoria, & Petrarulo, Luca. (2022). CCG Platform - Body of Knowledge: Review of Good Practice (1.3). Zenodo. https://doi.org/10.5281/zenodo.5911546"

[2]: https://creativecommons.org/licenses/by/4.0/legalcode

[3]: https://doi.org/10.1371/journal.pcbi.1003285 "G. K. Sandve, A. Nekrutenko, J. Taylor, and E. Hovig, ‘Ten Simple Rules for Reproducible Computational Research’, PLOS Computational Biology, vol. 9, no. 10, p. e1003285, Oct. 2013, doi: 10.1371/journal.pcbi.1003285."

[4]: https://specs.frictionlessdata.io/data-package/ "Frictionless Data Package"

[5]: https://git-lfs.github.com/ "Git Large-File-System"

[6]: https://dvc.org/ "DVC"

[7]: https://coderefinery.org "CodeRefinery"

[8]: https://coderefinery.org/git-intro/ "Intro to Git"

[9]: https://software-carpentry.org/ "Software Carpentry"

[10]: http://swcarpentry.github.io/git-novice "Version Control with Git"

[11]: http://doi.org/10.1038/sdata.2016.18 "M. D. Wilkinson et al., ‘The FAIR Guiding Principles for scientific data management and stewardship’, Sci Data, vol. 3, no. 1, p. 160018, Mar. 2016, doi: 10.1038/sdata.2016.18."