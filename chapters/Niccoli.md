# Prototype colormaps for fault interpretation

Matteo Niccoli

> This manuscript is not ready for review yet: the notebooks are blank at the moment; the IPywidget functionality has changed and needs to be updated. &mdash; MN

This article describes the ongoing process of building an interactive colormap web app to generate a modified gray scale for fault interpretation in seismic sections. The standard gray scale is already quite effective because it highlights low amplitude events and aids in the recognition of subtle terminations [1]; however, one way to further enhance it is to dynamically vary the Lightness contrast (intended as the Lightness profile gradient) to be high in the central portion of the colormap and low at the ends. This can be accomplished in Hue-Saturation-Lightness color space using a logistic sigmoid curve [2] for Lightness, setting Hue and Saturation to zero, and then converting from HSL to RGB. 

There are two stages in the app creation process: developing the individual elements separately (the sigmoid function, plotting routines, et cetera), and assembling them into a user interface. The code below shows the function that creates the sigmoid Lightness curve and how it is called.

    def sigmoid(x,c,w):
    sgm = 1/(1+np.exp(-(x-c)/w))
    return (sgm-min(sgm))/(max(sgm)-min(sgm))

    x = np.linspace(0,10,256)
    l_sigm = sigmoid(x,5,1)

    h_sigm = np.zeros(256)
    s_sigm = np.zeros(256)

The shape of the sigmoid is controlled by the equation in line 02 using two parameters: c, the position of the central ramp, and w, its width (which in turn determines the contrast); x is the sample number, defined in line 04 prior to calling the function. The resulting curve is normalized in line 03 to the range 0-1 (Lightness range for Matplotlib colormaps). The function is called in line 05 to create a 256x1 Lightness array. The commands in lines 06 and 07 create two 256x1 arrays of zeros for Hue and Saturation. The full to develop all the individual elements is available in the accompanying IPython notebook Sigmoid_app_blocks.ipynb (http://nbviewer.ipython.org/github/mycarta/Sigmoid_app/blob/master/Sigmoid_app_blocks.ipynb). A second notebook, Sigmoid_app_experiments.ipynb, explores the effects of varying parameters c and w, and is available at https://github.com/mycarta/Sigmoid_app/blob/master/Sigmoid_app_experiments.ipynb.

An app prototype, built using a third IPython notebook (Sigmoid_app.ipynb at http://nbviewer.ipython.org/github/mycarta/Sigmoid_app/blob/master/Sigmoid_app.ipynb) and IPy-widgets (https://github.com/jakevdp/ipywidgets), is shown in Figure 1. The sigmoid Lightness curve is plotted in 1 and the resulting colormap, created using tools described in [3], in 2. Panel 3 is a demo seismic section with faults, cross line 1155 from the Penobscot F3 3D (the same used in [4]). The Lightness contrast per sample in the central portion of the colormap is given in 4, and it is calculated as:

    (l_sigm [128]- l_sigm[127])*100

In this example the contrast is negative 1.31 since Lightness decreases with increasing sample number. As a reference, the contrast in the standard gray scale is about 0.4. 
To make the interface work, the elements 1 to 4 are grouped together in a single function, called sigmoid_demo in the notebook. The last element in the prototype, 5 in the Figure, is an interactive JavaScript slider created with IPy-widgets with this line at the end of the notebook:

    StaticInteract(sigmoid_demo, w=RangeWidget(-2.75,2.75,0.25))

The command calls the sigmoid_demo function specifying a range for parameter w (in this example between the values of -2.75 and 2.75, in steps of 0.25; parameter c ins held constant since we want an antisymmetric colormap), which pre-generates all the results at once and activates the slider, allowing users to interact with these results. When the notebook is saved, all the pre-generated outputs are saved with it so that if it is viewed using the IPython Notebook Viewer (http://nbviewer.ipython.org), or included in a webpage, the interactivity is available without having to have either IPython Notebook or Python running. Please give the app a try at (http://nbviewer.ipython.org/github/mycarta/Sigmoid_app/blob/master/Sigmoid_app.ipynb).

The final version of the app, which I am planning to build using D3.js (http://d3js.org/), will include the ability to save the colormap in a variety of formats, and also to import a 2D seismic section in either SEGY or ASCII format.

_Figure 1 – Sigmoid gray scale app prototype._

References

Brown, A. (2012). Interpretation of Three-Dimensional Seismic Data. SEG Investigations in Geophysics, no. 9, 7th edition.

Sigmoid Function, Wolfram Mathworld. http://mathworld.wolfram.com/SigmoidFunction.html

Niccoli, M. (2014) Evaluate and compare colormaps. The Leading Edge 33, no. 8, 910–912. Open access at: https://github.com/seg/tutorials#august-2014

Bianco, E. (2014) Well tie calculus. The Leading Edge 33, no. 6, 674-677. Open access at: https://github.com/seg/tutorials#june-2014
