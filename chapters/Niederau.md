# Teaching geoscience students to code

*By Jan Niederau*

I'm a self-taught coder, but a geologist by education. So there were people who taught me how to analyse rocks, how to interpret seismics (or an XRD difractogram), how to use GIS. But during my studies, everything with programming, all _quantitative_ lectures were done in Excel. It was until I studied abroad in France, that I learned
about [Scilab](http://www.scilab.org/) and programming. And that really got me into coding. Since then, I moved from Scilab to Matlab (as my university has free licenses for students), to Python.  

I started teaching courses in geothermics, and realized that most of the students in my exercise courses had little to no experience with programming, even though they had a mandatory lecture about programming and statistics, taught in Matlab instead of Excel. 
Still, that course is given in a frontal lecture style, where students are passive consumers. They follow the lecturer's code displayed on the beamer, often step-by-step. 

That's the traditional way, the way they're used to. But it has been shown, that it is also one of the least efficient ways of teaching students to code [1]. So for improving a student's skills in programming efficiently, they have to actively solve problems in a self-determined way.

Achieving this in my courses turned out to be way more difficult than previously thought. When confronted with a problem and the IDE's _white wall editor_, many students were lost. One key conclusion for me is, that the initial obstacle for students to start coding and learn programming is really high. Then I got the chance to work together with Florian Wellmann on a project supported by the [Exploratory Teaching Space Program](https://goo.gl/C5yry9) of our university. 
In this project, we created concepts of teaching code interactively using Jupyter Notebooks.

They enable to combine code, formatable text, and images/plots in one single document format, making them the ideal tool for teaching. However, they work smoother with Python than with Matlab. But considering Python's ever growing popularity, teaching students to code in Python instead in Matlab, might even be better. Especially, because basic coding skills become more and more prerequisite, and Python gets really popular in the geosciences [2].  

In professor Wellmann's lecture "Numerical Reservoir Engineering", we tested combining task-definition together with predefined solution cells in a Jupyter Notebook instead handing out a single PDF file with the task-definition. The passively spent presence time during the exercise evolved to an active working session.    
The perception by the students was great, so we increased the use of Notebooks, also for graded assignments.  
Due to the flourishing community of Jupyter-developers, there exists a tool called [nbgrader](https://github.com/jupyter/nbgrader) which perfectly fitted our needs. Notebooks could now be autograded (with the occasional manual grading step)!

Next to assignment notebooks equiped with autograding, we created a number of notebooks accompanying the content of the lecture as a opportunity of self-assessment for the students. In my opinion, a lot of geoscience students are _haptic_ people (just think of rock-identification courses) appreciating visual input. Geological processes are often taught using analogue models, e.g. folding with modeling clay. Crystal systems are taught by using geometrical bodies made
out of wood.  

Jupyter Notebooks enable haptic ways of teaching programming by using widgets. For example, we created [notebooks in structural geology](https://github.com/Japhiolite/stress-and-strain) with sliders and boxes, so students can e.g. directly experience the response of a strain ellipse, when they changed the deformation tensor. One key take-away message for me was: Students had fun experimenting with these notebooks, from altering functions to trying to break them. And connecting the lecture content with a (strong) emotion, increases the
learning effect demonstrably [3]. 

During the last couple of years, we've come a long way in terms of teaching geoscience-students to code. Programming tools changed from Excel, over a Matlab IDE to Notebooks. Notebooks are used for different purposes, from lecture-accompanying notebooks, to (auto-)graded assignment notebooks. The influx of Python in our faculty is remarkable.  
Oh, and the programming and statistics course is now taught in Python, using Jupyter Notebooks which I can highly recommend for every practical programming course.
 

## References  

[1] Jacobs, C.T., Gorman, G.J., Rees, H.E. and Craig, L.E., 2016. Experiences with efficient methodologies for teaching computer programming to geoscientists. _Journal of Geoscience Education, 64_(3), pp.183-198.  
[2] Lin, J.W.B., 2012. Why Python is the next wave in earth sciences computing. _Bulletin of the American Meteorological Society, 93_(12), pp.1823-1824.
[3]Christianson, S.A., 2014. The handbook of emotion and memory: Research and theory. _Psychology Press_.
