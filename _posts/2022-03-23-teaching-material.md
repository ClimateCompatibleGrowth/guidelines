---
layout: post
title:  "Teaching material"
date:   2022-03-23
author: Francesco Gardumi
category: Teaching
tags: teaching kit, teaching material, training, learning, open access
---

 
## Context

The education landscape is changing dramatically. Focus in the pedagogical practice is rapidly shifting towards active and [deep-learning] [1]. The importance of active learning is underlined by [UNESCO] [2], which highlights that only active learning can lead to the development of skills and competencies. Competencies include: system thinking, anticipatory, normative, strategic, collaboration, critical thinking, self-awareness and integrated problem-solving [2]. 

In the teaching practice, therefore, attention is given to 'what the student does', rather than 'what the teacher does', as in [Biggs] [3]. Teaching and learning are not seen in isolation, but rather as a teaching-learning binomium. A 'class' becomes a teaaching-learning occasion. The teacher becomes a facilitator, who must ensure there is 1) teacher's, 2) social and 3) cognitive presence in the learning practice, as in [Hrastinski] [4].

With the proliferation of digital means, there is a huge opportunity for online and hybrid education to enable the development of skills and competences as intended by UNESCO. Such development, importantly, will not happen only in traditional educational settings (e.g. academia), but also beyond, leading to so-called lifelong learning.

### E-learning

There are several examples of e-learning environments, such as Coursera or OpenLearn Create by the Open University (the latter based on Moodle learning environment). The courses consist of theory (in the form of written material and/or videos) and practice (hands-on exercises, quizzes, self-evaluation practices). The students can take the courses at their own pace and obtain certificates upon completion. There is normally no interaction with the teachers. The way the learning material for the courses has been created can vary. Some key common features in e-learning material are:
* Modularity;
* Presence of info-graphics;
* Short videos;
* Exercises (with ex-post correct answers and explanations for self-evaluation)
* Multi-language.

### E-teaching

There are good examples of open-licensed courses and lectures, but these are normally made available by well-meaning and enthusiastic individuals, rather than cross-institutional teams. 
Fully open and collaborative environments for the development of courses, such as [Wikiversity] [5], do exist, though they do not provide a learning environment similar to that of Moodle, on which OpenLearn Create is built.
The heavily curated teaching materials provided by Software Carpentry provide an example of best practice of Open Teaching Material. Software Carpentry designs numerous interactive and hands-on courses that are designed for self-learning and in-classroom or hybrid teaching. Software Carpentry also offers the service of workshops upon request, online or hybrid. 
The material is freely accessible, fully documented and continuously updated and structured in a way that allows gradual upgrade of skills at own pace (i.e. designed for lifelong learning). Due to the open license [] of the material, others are free to make use of the learning material in their own right. For example, the Nordic-based CodeRefinery has based its own courses on the Software Carpentry material.
The material is developed and prepared in GitHub following precise workflows [], but it is rendered as webpages for learners. Full references [] and instructor notes are available for each lesson. The development of a lesson is conducted collaboratively using the features available through the git version control software [], and social tools on Github. The Github issue tracker is used to record ideas and suggestions and receive feedback from learners. Pull requests are used to discuss and review new contributions. Releases [] are used to publish completed versions of the lesson to the webpage, including metadata [] and attributions [].

## Collaborative development of teaching material

By collaborative development of teaching material we mean the creation or update of text, lecture modules, lectures, courses, hands on exercises etc. online, in a shared and collaborative fashion, by teachers from any institution worldwide. Any trainer or teacher shall be able to create and upload to a common repository teaching material, modify existing teaching material, or download existing teaching material for use in own courses. Access is meant to be public and former students may take on the role of teachers, too.
The material shall preferably sit outside of the learning management system of one specific institution, but it must be licensed and attributed at any instance of its use. The update and upload of material does not need to be dynamic and/or live, but it does need to be version-controlled. That means that teachers may not have the possibility to work live, in parallel, on the same document, but their respective documents are versioned and can be compared/merged once uploaded. The teaching material shall be community-based, retrievable and reusable (that is, compliant with [U4RIA-goals] [6]). 
Key for enabling the collaborative development of teaching material is that it has at least (but not necessarily only) the following attributes:
* Open-access-licensed;
* Available online;
* Editable;
* Modular;
* Versioned;
Other characteristics that are highly desirable are:
* Availability in several languages;
* Availability of metadata including authorship and attribution; acknowledgments of funding, collaboration and review; license; metadata associated to all media and info-graphics;
* Availability as plain text + collection of media and metadata (with no template);

## Example of teaching-learning material from an OpenLearn Create Collection

Partners in the Climate [Compatible Growth program](https://climatecompatiblegrowth.com/) have created a collection of free and open access courses on Modelling Tools for Sustainable Development. These courses apply best practices for e-learning material and practices that allow for collaborative course development as follows:

* Open access license: [CC BY 4.0 license](https://creativecommons.org/licenses/by/4.0/) on all the course material; every piece of media (figure, graph, or video) is also licensed with CC BY 4.0 license or more permissive ones and attributed;
* Available online: the source material is gradually being made available on a public [GitHub repository](https://github.com/ClimateCompatibleGrowth);
* Editable: the source material is editable through the GitHub repository, to different degrees (e.g. by submitting issues or directly by submitting pull requests);
* Modular: each course is divided into lectures; each lecture is constituted of 4 modules; each module presents 5 concepts of 150-300 words each and a list of references; at the end of each lecture, a multiple-choice quiz with automatic proofing tests the understanding of the student and gives feedback when the questions are answered;
* Versioned: GitHub provides automatic version control; under development: twice a year, an instance of the course, corresponding to a certain commit, is going to be published on Open University's [OpenLearn Create platform](https://www.open.edu/openlearncreate/course/index.php?categoryid=541);
* Availability as plain text + collection of media and metadata: for new courses, especially, the lecture modules are created as collections of Markdown files (for the text), folders with the media, and files with all metadata. These are then to be automatically rendered into other formats as needed. This is done to allow easier storing of the material, tracking of changes, versioning, and automatic bundling of different contents without having to deal with multiple versions of .pptx or .docx files. 


## Further reading

You may read more about best practices employed in the production of open access teaching material, as well as other knowledge outputs, in the following blog posts:
* Licensing;
* Worflows;
* Version control;
* Metadata;
* References;
* Attributions;
* Release;

## References

[1] Angelo, T. Designing subjects for learning: Practical research-based principles and guidelines. in University teaching in focus: a learning-centred approach 93–111 (2012).
[2] UNESCO, Education for Sustainable Development Goals: Learning Objectives. UNESCO, 2017. ISBN: 978-92-3-100209-0.
[3] John Biggs (1999) What the Student Does: teaching for enhanced learning, Higher Education Research & Development, 18:1, 57-75, DOI: 10.1080/0729436990180105.
[4] Hrastinski, S., 2019. What do we mean by blended learning?. TechTrends, 63(5), pp.564-569. https://link.springer.com/article/10.1007/s11528-019-00375-5.
[5] ‘Wikiversity’. https://en.wikiversity.org/wiki/Wikiversity:Main_Page (accessed Dec. 1225 09, 2021).
[6] Howells, M., Quiros-Tortos, J., Morrison, R., Rogner, H., Niet, T., Petrarulo, L., Usher, W., Blyth, W., Godínez, G., Victor, L.F. and Angulo, J., 2021. Energy system analytics and good governance-U4RIA goals of Energy Modelling for Policy Support. https://www.researchsquare.com/article/rs-311311/v1.
