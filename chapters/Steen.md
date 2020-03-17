---
Title: "How to teach geoscience students to code"
Author: Drew Steen
Date: 06-23-2017
---
Some years ago, I met with a computer scientist about creating a coding class for geoscientists. The CS instructor said that "we need to take these geoscientists, and turn them into programmers!" I totally disagree: the goal of a coding class for geoscientists is **not** to change students' disciplinary orientation. Rather, it is to give discipline scientists an additional set of tools they can use to create excellent science. If a computer science degree is like a master carpentry course, a coding class for geosciences should be like an entry-level job on a construction site. 

To extend the metaphor, geoscience students will end up needing a vastly different set of tools depending on their discipline and their specific project: the geophysicst who is working accessing seismology datasets through APIs will likely use differen languages, and rely on different skills, than the geomicrobiologist who is running new-but-buggy software to handle genomic datasets or the palentologist who needs high-performance computing to create 3-D visualizations.

I'm convinced, therefore, that geoscience students are not best served by general-purpose introductory CS classes, or even language-specific general purpose classes (e.g. Basics of Python). Rather, geoscience departments should all (ALL!) offer an upper-level undergrad/graduate class that is tailored to the specific needs and circumstances of geoscience students. The goals of such a course should be to give students some basic skills that are relevant to all geoscientists (e.g., how to process data in a reproducible fashion) and to give studnets the vocabulary and some basic skills they can use to build on once they have identified their own specific needs. 

Here, I draw on my experience teaching several such classes as a more-or-less self-taught coder to describe some of what I believe are best practices in teaching coding to geoscientsts.

## Coding for geoscientists: a practical approach

A number of constraints emerge from the idea that coding should be taught to geoscientsts as a set of practical tools. First, students should be taught at the beginning of their research career, once they have begun to gather data: this means upper-level undergraduates and early-career graduate students. Before this point, students need to focus on learning geosciences, and after this point is too late: late career graduate students will have come to rely on unwieldy workarounds (as a Ph.D. student, I didn't see anything wrong with storing my data in 1800 individual Excel worksheets) and may have come to unconsciously factor in their limitations in data analysis abilities when designing new projects.  Second, the course should be tailored as much as possible to be synergystic with the student's research. Grad students' primary job is to do research; a coding class is valuable only to the extent that it facilitates that research. Finally, a class should teach students practical tasks quickly, rather than bogging them down in theory early, in order to keep motivation high (Fig. 1). A good coding class for geoscientists should aim to meet the following goals:

### Meet students where they are

Some students will have very little understanding of some important basics: how directory structures work, the basic harware coponents of a computer, the difference between a script, a computer language, and executable file, and an operating system. This problem is particularly acute in students born after the mid-1990s. These students will have grown up in the age of the mobile OS, which go to great lengths to hide directory stuctures and other "internals". Begin classes with a fairly detailed discussion of these points. It is a good idea to mandate the directory structure that students will use for their class work, in order to ease troubleshooting by the instructor, and depending on class infrastructure it may make sense to insist that all students install Linux on their personal laptops to do their coursework. 

### Teach a single language

A class needs to be taught as simply as possible, in a single language. I consistently find that concepts which seem self-evident to me confuse my students. This is not to insult my students - I'm actually amazed at how quickly many of them learn - but to say that it is easy forget what I found confusing when I first started to learn to code. Lectures need a great many specific examples, in a single language. Thus, the goal of a class should be some level of proficiency in a specified language, even when you know that langauge will not be used my some or even most of your students.

### Teach a good teaching language

The great value of interpreted languages such as R and Python is that they allow students to get immediate results by working interactively. Students will be motivated to push through the early, steep part of the learning curve when they can immediately do something practical (even if it is trivial, like taking an average of numbers). Later, students will seamlessly build out from simple concepts such as objects, operators, and functions to write their own funcitons, packages, etc.

### Teach students to be good at any language

Many students inevitably will need to use a different langauge in their research than what is taught in class. Thus, it is essential to teach students coding meta-skills, or skills to gain skills. These include skills like learning how to read documentation, where to look for help on the internet, effective commenting and documentation, code profiling, and defensive programming. Auxiliary skills are important, too: for instance some basic bash commands, text editors, version control (I think git and github are particularly relevant) and database basics. 

### Use student resources effectively

A class of any significant size is likely to contain some students who know almost nothing about how computers work, and others who are already operating at an advanced level. This variety can be an asset, if the advanced students are used as resources. I have done this by grouping students into small groups (4 seems to be the ideal number) making sure that each group contains some more advanced students and some less advanced ones. Each student turns in their own homework, but they're not allowed to turn it in until every group member certifies that every other group member has finished their task. This incentivizes students to help each other, and to keep anyone from falling behind. 

### Remember that your students need to know Excel

Finally, an important point: the vast majority of business environments (and probably academic labs) rely on Microsoft Excel for most data analysis. To the extent that geoscience education is preparation for the working world, a student who codes beautifully and can't use Excel is badly prepared. Excel skills inlcude an introduction to Excel's advanced functions (e.g. pivot tables and conditional formatting) as well as the design skills necessary to create an easily-interpretable spreadsheet. For all of Excel's well-documented failings, good Excel hygiene may be many geoscientist's most frequently-used job skill.

# Conclusions

Coding skills are now useful in virtually every technical profession, and teaching them is an important component of undergraduate and graduate geoscience education. However, geoscience students have a distinct set of motivations and needs for learning to code. Coding classes for geoscientists should therefore be designed to yield practical results as soon as possible, should focus on geoscience domain-related skills, and should provide students with the skills required to learn on their own the skills they need to do their own work.

