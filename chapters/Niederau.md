# Teaching geoscience students to code

*By Jan Niederau*

I'm a self-taught coder, but a geologist by education. So there were people who taught me how to analyse rocks, how to use GIS, how to interpret seismics (or a thin section, or an XRD difractogram). But during my studies, everything with programming, all _quantitative_ lectures were done in Excel. It wasn't until I studied abroad in France, that I learned about [Scilab](http://www.scilab.org/) [0] and programming. And that really got me into coding. Since then, I moved from Scilab to Matlab (as my university had free licenses for students), to Python.  

I started teaching courses in geothermics, and realized that most of the students in my exercise courses had little to no experience with programming, even though they had mandatory introduction courses about programming, now taught in Matlab instead of Excel. 
Still, that course was given in a frontal lecture style, where students are passive consumers, and follow the lecturer's code displayed on the projector, often step-by-step. So similar to a math lecture, where students try to not fall behind copying the professor's hand-written lemmas and derivations. 

That's the traditional way, the way they're used to. But it has been shown, that it is also one of the least efficient ways of teaching students to code [1]. So for improving a student's skills in programming efficiently, they have to actively solve problems in a self-determined way.

Achieving this in my courses turned out to be way more difficult than previously thought. When confronted with a problem and the IDE's _white wall editor_, many students were lost. One key conclusion for me is, that the initial obstacle for students to start coding and learn programming is really high. Then I got the chance to work together with Professor Wellmann from RWTH-Aachen University on projects supported by the [Exploratory Teaching Space Program](https://goo.gl/C5yry9) and the
[Stifterverband](https://www.stifterverband.org/digital-lehrfellows/2017/wellmann)(in German) [2]. 
In these projects, we created concepts of teaching code interactively using Jupyter Notebooks, and to generally lower *teething troubles* when it comes to coding.

Jupyter notebooks combine code, formatable text, and images/plots in one single document format, making them the ideal tool for teaching. However, they work smoother with Python than with Matlab. But considering Python's ever growing popularity, teaching students to code in Python instead in Matlab, might even be better. Especially, because basic coding skills become more and more prerequisite, Python is becoming more and more popular in the geosciences [3], and finally, because it is - in contrast to Matlab - free.  

In our projects, we tested combining task-definition together with predefined solution cells in a Jupyter Notebook instead handing out a single PDF file with the task-definition. 
The passively spent presence time during the exercise evolved to active working sessions. By using some of the many great notebook-extensions, such as [exercise, and exercise2](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/nbextensions/exercise/readme.html), solutions to exercises could be shipped with the notebook.   
This is particularly useful for creating a notebook with increasing level of difficulty. Imagine the concept/topic/process to be taught is broken down in three stages. 
First, it is presented in a simple working example, where students can follow **at their own speed**. Based on this, they're presented with a further example, where they have to code the answer, but a solution is provided, yet hidden until shown. The third stage, would then be a bit more complex example building on the
previous learned content. Due to the linear structure of notebooks, such a concept can easily be implemented.  

The feedback by the students to using notebooks was great, so we increased their use, also for graded assignments.  
Due to the flourishing community of Jupyter-developers, there exists a tool called [nbgrader](https://github.com/jupyter/nbgrader) [4] which perfectly fitted our needs. Notebooks could now be autograded (with the occasional manual grading step)! To ensure that students are working under the same conditions for these graded assignments, we set up a server with [jupyterhub](https://jupyter.org/hub). Students then just had to log in and could start their assignments, which could be distributed
and collected remotely by the advisor. 

Next to assignment notebooks equiped with autograding, we created a number of notebooks accompanying the content of the lecture as a opportunity of self-assessment for the students. In my opinion, a lot of geoscience students are _haptic_ people (just think of rock-identification courses) appreciating visual input. Geological processes are often taught using analogue models, e.g. folding with modeling clay. Crystal systems are taught by using geometrical bodies made
out of wood.  

Jupyter Notebooks enable haptic ways of teaching programming by using widgets. For example, we created [notebooks in structural geology](https://github.com/Japhiolite/stress-and-strain) [5] with sliders and boxes, so students can e.g. directly experience the response of a strain ellipse, when they changed the deformation tensor. 
Since this all started, I transferred some exercises from my [geothermics course to notebooks](https://github.com/Japhiolite/geothermics) [6]. And I am quite late with this move. 
There is a constantly growing amount of teaching resources, such as [python for geosciences](https://github.com/koldunovn/python_for_geosciences)[7], [Geo Python](https://geo-python.github.io/site/) [8], and above all the great course [12 steps to Navier-Stokes by Lorena Barba](https://lorenabarba.com/blog/cfd-python-12-steps-to-navier-stokes/) [9]. Lorena Barba and some co-authors even wrote a book about [Teaching and Learning with
Jupyter](https://jupyter4edu.github.io/jupyter-edu-book/) [10], which is an excellent read and resource, if you want to *jupyter-up your teaching*.

One key take-away message for me was: Students had fun experimenting with these notebooks, from altering functions to trying to break them. And connecting the lecture content with a (strong) emotion, increases the
learning effect demonstrably [11]. 

During the last couple of years, we've come a long way in terms of teaching geoscience-students to code. Programming tools changed from Excel, over a Matlab IDE to Notebooks. Notebooks are used for different purposes, from lecture-accompanying notebooks, to (auto-)graded assignment notebooks. The influx of Python in our faculty is remarkable.  
Oh, and the programming and statistics course is now taught in Python, using Jupyter Notebooks.
 

## References  

[0] https://www.scilab.org/
[1] Jacobs, C.T., Gorman, G.J., Rees, H.E. and Craig, L.E., 2016. Experiences with efficient methodologies for teaching computer programming to geoscientists. _Journal of Geoscience Education, 64_(3), pp.183-198.  
[2] https://www.stifterverband.org/digital-lehrfellows/2017/wellmann, retrieved: 2020-03-23.  
[3] Lin, J.W.B., 2012. Why Python is the next wave in earth sciences computing. _Bulletin of the American Meteorological Society, 93_(12), pp.1823-1824.  
[4] https://github.com/jupyter/nbgrader/, retrieved: 2020-03-23.   
[5] https://github.com/Japhiolite/stress-and-strain, retrieved: 2020-03-23.  
[6] https://github.com/Japhiolite/geothermics, retrieved: 2020-03-23.  
[7] Koldunov, N. Python for geosciences, https://github.com/koldunovn/python_for_geosciences, retrieved: 2020-03-23.  
[8] Department of Geosciences and Geography, University of Helsinki: Geo Pyhon, https://geo-python.github.io/site/, retrieved: 2020-03-23.
[9] Barba, Lorena A., and Forsyth, Gilbert F. (2018). CFD Python: the 12 steps to Navier-Stokes equations. Journal of Open Source Education, 1(9), 21, https://doi.org/10.21105/jose.00021  
[10] Barba, Lorena A., Barker, Lecia J., Blank, Douglas S., Downey, Allen B., George, Timothy, Heagy, Lindsey J., Mandli, Kyle T., Moore, Jason K., Lippert, David, Niemeyer, Kyle E., Watkins, Ryan R., West, Richard H., Wickes, Elizabeth, Willing, Carol, and Zingale, Michael, 2019. Teaching and Learning with Jupyter, https://jupyter4edu.github.io/jupyter-edu-book/, retrieved: 2020-03-23.  
[11] Christianson, S.A., 2014. The handbook of emotion and memory: Research and theory. _Psychology Press_.  
