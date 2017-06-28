---
Title: "How to teach geoscientists to code"
Author: Drew Steen
Date: 06-23-2017
---

Some years ago, I met with a computer scientist about creating a coding class for geoscientists. The CS instructor said that "we need to take these geoscientists, and turn them into programmers!" I totally disagree: the goal of a coding class for geoscientists is **not** to change students' disciplinary orientation. Rather, it is to give discipline scientists an additional set of tools they can use to create excellent science. If a computer science degree is like a master carpentry course, a coding class for geosciences should be like an entry-level job on a construction site. 

(I don't konw where to put this sentence:) To extend the metaphor, geoscience students will end up needing a vastly different set of tools depending on their discipline and their specific project: the geophysicst who is working accessing seismology datasets through APIs requires a very different set of tools from the geomicrobiologist who is running new-but-buggy software to handle genomic datasets.

I'm convinced, therefore, that geoscience students are not best served by general-purpose introductory CS classes, or even language-specific general purpose classes (e.g. Basics of Python). Rather, geoscience departments should all (ALL!) offer an upper-level undergrad/graduate class that are tailored to the specific needs and circumstances of geoscience students. The goals of such a course should be to give students some basic skills that are relevant to all geoscientists (e.g., how to process data in a reproducible fashion) and to give studnets the vocabulary and some basic skills they can use to build on once they have identified their own specific needs. 

Here, I draw on my experience teaching several such classes as a more-or-less self-taught coder to describe some of what I believe are best practices in teaching coding to geoscientsts.

## Coding for geoscientists: a practical approach

A number of constraints emerge from the idea that coding should be taught to geoscientsts as a set of practical tools. First, students should be taught at the beginning of their research career, once they have begun to gather data: this means upper-level undergraduates and early-career graduate students. Before this point, students need to focus on learning geosciences, and after this point is too late: late career graduate students will have come to rely on unwieldy workarounds (as a Ph.D. student, I didn't see anything wrong with storing my data in 1800 individual Excel worksheets) and may have come to unconsciously factor in their limitations in data analysis abilities when designing new projects.  Second, the course should be tailored as much as possible to be synergystic with the student's research. Grad students' primary job is to do research; a coding class is valuable only to the extent that it facilitates that research. A good coding class for geoscientists should aim to meet the following goals:

### Meet students where they are

Some students will have very little understanding of some important basics: how directory structures work, the basic harware coponents of a computer, the difference between a script, a computer language, and executable file, and an operating system. This problem is particularly acute in students born after the mid-1990s. These students will have grown up in the age of the mobile OS, which go to great lengths to hide directory stuctures and other "internals". Begin classes with a fairly detailed discussion of these points. It is also a good idea to mandate the directory structure that students will use for their class work. 

### Teach a single language

A class needs to be taught as simply as possible, in a single language. I consistently find that concepts which seem self-evident to me confuse my students. This is not to insult my students - I'm actually amazed at how quickly many of them learn - but to say that it is easy forget what I found confusing when I first started to learn to code. Lectures need a great many specific examples, in a single language. Thus, the goal of a class should be some level of proficiency in a specified language, even when you know that langauge will not be used my some or even most of your students.

### Teach a good teaching language

The great value of R, and python via Jupyter Notebooks, is that it allows students to start working interactively so that useful results can be gained with a single line of code. Students can seamlessly build out from simple concepts such as objects, operators, and functions to write their own funcitons, packages, etc.

### Teach students to be good at any language

Many students inevitably will need to use a different langauge in their research than what is taught in class. Thus, it is essential to teach students coding meta-skills, or skills to gain skills. These include skills like learning how to read documentation, where to look for help on the internet, effective commenting and documentation, code profiling and *(other code efficiency stuff)*. Auxiliary skills are important, too: for instance some basic bash shell (CHECK) commands, text editors, version control (I think git and github are particularly relevant) and perhaps some database basics. 

### Use student resources effectively

A class of any significant size is likely to contain some students who know almost nothing about how computers work, and others who are already operating near the level (that represents the goal for the end of class). This variety can be an asset, if the advanced students are used as resources. I have done this by grouping students into small groups (4 seems to be the ideal number) making sure that each group contains some more advanced students and some less advanced ones. Each student turns in their own homework, but they're not allowed to turn it in until the entire group is ready (MAKE BETTER). I also encouraged each group to choose a weekly group meeting time outside of class to use as a help session. This gives students an incentive to help each other, and gives the more advanced students practice in teaching (WHICH IS A GREAT WAY TO LEARN BUT WRITE BETTER).


### Remember that your students need to know Excel

Finally, an important point: the vast majority of business environments (and probably academic labs) rely on Microsoft Excel for most data analysis. To the extent that geoscience education is preparation for the working world, a student who codes beautifully and can't use Excel is badly prepared. Depending on the department's broader curriculum, a coding class might not be the best place to teach Excel, but neither should students be expected to pick up good Excel habits from thin air. (Conclusion sentence). 

# Conclusions

Some kind of brief conclusion, maybe.


<<Blah blah blah: Visual Basic and other programming interfaces for Excel (there are Python, R, and MATLAB ones) are great, but really students need to learn how to put together a comprehensible, powerful, and attractive Excel sheet. THe upside is that these skills are a part of reproducible science: a student who has thought about how to write code that is easy to read, will be better at creating a legible Excel sheet, and vice versa.







## A practical approach

Geoscience students often (not always!) tend to be relatively concrete thinkers. For that reason it is massively easier for us to learn coding in the context of real, useful geoscience data analysis tasks (or at least tasks that are plausibly connected to real-world tasks). This means that:

a. It makes sense to teach students who already have some data: upper level undergraduate and early-career graduate students
b. It helps to use data sets and tasks that are connected to geoscience, rather than generic data analysis data sets and tasks.

This puts constraits on students, however: undergraduate students only have a limited amount of time to work on a class, and the prime responsibility of graduate students is to produce research, not to work on classes. This means that **the goal of a coding class for geoscientists should be to give students the tools to 

The ideal class therefore would have students work entirely with their own data sets, thereby do

... I don't know how to connect this to the next thought...




### Spatial orientation


### Visualization and unique challenges



## Unusual points

* Students are goal-oriented: Don't ahve time to learn a new field (We're not creating computer scientists, we're creating geoscientists who have an extra skill set)
* Students are time-constrained. Easy to imagine that they need to learn coding from the ground up (CS approach) but really they need to be working on their science while they're learning to code - just purely from a time management standpoint
* Many (not all!) students are somewhat concrete. THey would have gone into CS if they wanted to go into CS. 


## Key skills

Note: instructors, mainly, are from a generation where OS were more visible/transparent than "kids these days", who are used to mobile OS that conceal directory structure etc

* PRoper file management (i.e., don't dump everything on your desktop!)
* Understanding file structures and text file formats
* Understanding a little bit about hardware (i.e., hard drive, processor, RAM, roughly what those all do)
* Understanding the difference between IDE, source code, compiler/interpreter, OS
* Roughly how to use git/GitHub. (For me, just commit/branch/push-pull/fork.) Mainly useful because 

# Final recommendations

* Teach coding, not a specific language (but teach in a specific language). 
* Teach in an interactive language, which is relevant to students' research. In practice this means R, Python, or (ugh, if you must) MATLAB.
* Force students to solve each others' problems, e.g. by grading on the principle of collective responsibility [n.b.: I am looking for a less historically-charged term!].
* Be sure to cover geoscience-relevant tasks, including timeseries, spatial analysis, and data visualization.


-----
Footnotes:
* Mostly. This chapter assumes students who need to learn some coding for their data analysis, but fundamentally are trying to make new discoveries about geoscience. There's another class of geoscientists who have a foot in computer science or software design: people trying to develop new algorithms for GIS, for instance. Those people really do need to learn CS qua CS, and the advice presented here doesn't apply.


---
cut text:

As an undergraduate, I had a brief career as a computer science major. Teaching computer science students to code is relatively straightforward, for two reasons:
* computer science students want to learn to code
* they have four years to learn it.

The second point here is underrated: computer science is a broad discipline. The basic tool of CS is coding, but coding is to computer science as hammering is to craft carpentry. This makes teaching coding to geoscientists* a fundamentally different exercise than teaching CS to CS students. 


