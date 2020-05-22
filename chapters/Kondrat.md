# Getting started in Geocomputing can seem daunting but it doesn’t need to be!

Darren Kondrat

It is best to start your geocomputing adventure with a project in mind. Is there something that you would like to be able to do but can’t with your existing tools? Charting data and basic well log math were some of the issues that caused me to get started.  I wanted to be able to add more dimensions in charts with color, shapes, and sizes, which are difficult to do within spreadsheets. Basic well log data math was another task that I wanted to be able to do. Loading LAS into a spreadsheet and manipulating the data can be done but was there an easier way?

Here is code and chart of one of my first projects, figure 1, to demonstrate how easy it to create a figure with Python. It requires only 3 libraries to handle loading, calculations and plotting. Welly, from Agile Scientific, loads the data right from a .las file to a well object with a lot of things for free (tutorial here: https://github.com/agile-geoscience/welly/blob/master/tutorial/Well.ipynb) Numpy, likely the most essential library, makes math with curves easy. Matplotlib, probably one of the most documented libraries of all, gets you the figure in a few lines of code.

    # import libraries
    import numpy as np
    import matplotlib.pyplot as plt
    from welly import Well

    #load data from filename.las
    w = Well.from_las(‘filename.las’)

    # setup color
    c = np.array(w.data['GRGM'].values)
    c[c>150] = 150

    #Calc Porosity
    p = (2650 - w.data['DEN'].values)/(2650-1000)
    #clean up values for plot
    p[p<0]=0
    p[p>.3]=.3
    p = p * 100 #scale for plot

    #plot figure
    fig, ax = plt.subplots(figsize=(12,10))
    scatter = plt.scatter(w.data['DTP'].values[-1000:],w.data['DTS'].values[-1000:],c=c[-1000:],
    cmap=plt.cm.cubehelix,s=p[-1000:])
    handles, labels = scatter.legend_elements(prop="sizes", alpha=0.6)
    legend = ax.legend(handles, labels, loc="upper left", title="Porosity")
    ax.set_xlabel('DTSonic')
    ax.set_ylabel('DTShear')
    cbar = plt.colorbar()
    cbar.set_label("Gamma Ray")
    plt.title('Simple Crossplot').

[Figure 1](https://github.com/softwareunderground/52things/blob/master/figures/Kondrat_fig1.pdf). Scatterplot of a DTSonic vs DTShear values colored by gamma ray and symbol size set by porosity. For a complete example using an open well see the notebook in my [52things_example repo](https://github.com/dkon99/52things_example).

Of course, learning to code is essential and there are many ways to make it easy. There are a ton of great books for beginners to professionals. Look at a few and pick one that you like, some people like simplified guides, others like technical references. I know everything is online but there is nothing like having a book that you can highlight and dogear pages for quick and easy referencing next to your keyboard. Interactive learning is amazing too, download an app and quickly walk through the tutorials. I used Sololearn to learn the basics of python. It explains what you need to do and quickly has you practicing writing code within minutes. You can even do this on your phone. As well, there are a plethora of online courses. I found a free one through the public library. It was great and I focussed as many assignments on my projects as I could. If you’re in a hurry or prefer a classroom environment, you can pay for a course or two. It’s great to get face to face with an instructor and peers to ask questions and gain some contacts for future help.

The books and courses for beginners will walk you through how to install python. I recommend starting with installing Anaconda and using Jupyter Notebooks to write and run your code. If you get stuck with some coding, docs.python.org is the place to go to a description of each function and how it used. Stackoverflow is an online community for developers to share knowledge. Developers post and answer questions and the discussions are all searchable. There doesn’t seem to be an issue that isn’t discussed there.

Once you have some basic coding knowledge and a project in mind, start surfing the web! It is likely something similar is out there that will help you get started, there seems to be an infinite number of examples.  Github (Github.com) is a developer’s toolbox to host their code. There are examples of code there from loading SEGY data to Machine Learning.  SEG has some tutorials (https://github.com/seg)  that would be a great place to start. Since 2014, Matt Hall has been leading this initiative. There are code examples for inversion, colorbars, synthetics, modeling, and even facies classification.

Time to get going! Looking forward to seeing what you can create. Enjoy the experience, try attending a hackathon or go to a conference for a ton of fun and the opportunity to tap into some amazing projects.
