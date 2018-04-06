# Arm-wavers Anonymous
Have you ever been in the field with geologists? They have a knack for standing at the base of an outcrop, swinging their arms wildly and postulating that the strata you are looking at is similar to a model they once wrote in Fortran because “they look the same”. Granted humans are rather good at visually comparing things, but there has to be a more scientific way to compare the geologists arm waving with quantitative models. Enter quantitative stratigraphy.

Quantitative stratigraphy is the study of sedimentary systems and stratigraphy using numerical data collected from strata in either outcrop, wells, seismic, or even modern systems. Quantitative stratigraphy has been around since the 1960’s with the work from people like John R. L. Allen, John S. Bridge, and Mike R. Leeder to name a few.
Since quantitative stratigraphy has been around for such a long time that means todays geologists must be collecting different data those a decade ago right? Now we use drones and laser rangefinders, but the types of data collected from outcrops hasn’t changed much. Stratigraphers still measure things such as lengths, thicknesses, grain size, and orientations. Modern tools make data collection faster, so geologists can collect more data than ever before. Although limited in variety, the volume of modern field measurements can be used to calculate geomorphologic parameters of depositional environments (slope, flow velocity, etc.).

Geomorphic measurements are a great way to compare the ancient and modern systems with models. In earth surface processes modelling there are numerical, geometric, rule-based, and physical models. Numerical models use mass balance to approximate how systems change with each time step (e.g. sediment flux). Geometric models use angles and boundary conditions to approximate the shape of systems (e.g. fluvial meanders). Rule-based models follow rules of how systems should react to changes in conditions within the model (e.g. deep water lobes).  Physical models are miniature versions of real world phenomena that fit inside a lab and run under known boundary conditions (e.g. deltas). The three computational methods of modelling are easy to get started with in Python. An example of numerical modelling of carbonate reef growth from Galewsky (1998) only takes X lines.

```
import numpy as np
import matplotlib.pyplot as plt
from IPython import display

x=np.arange(0,2500,1)
y=np.arange(-125,125,0.1)

Gm=0.015
k=0.16
I0=2250
Ik=450
zerogrowth=Gm*np.tanh((I0*np.exp(-k*0))/Ik)

for t in range (0,100000,1000):
    sl=np.zeros(len(y))
    z=sl-y
    z=np.where(z<0.,0.,z)
    G=Gm*np.tanh((I0*np.exp(-k*z))/Ik)
    G=np.where(G>=zerogrowth,0.,G)
    y=np.add(y, G*1000)
    y=np.add(y,-0.25)
    plt.plot(x,y)
    plt.plot(x,sl)
    display.clear_output(wait=True)
    plt.show()
```

The code above creates stratigraphy by updating topography based on carbonate growth at each time step. Run the model for a few thousand time steps and the topography becomes preserved stratigraphy. A few thousand to million time steps is enough to generate stratigraphy. In the computational models we save values such as topography to arrays that are later analyzed.

In physical models scaling things such as sediment caliber and boundary conditions (sea level, sediment and water flux, etc.) to the size of the basin means increased deposition. This in turn means geomorphology becomes stratigraphy in a matter of days rather than thousands of years. The data generated from topographic laser scans and overhead images of these experiments provide a way to measure how surface processes translate to the subsurface.

How do geologists know these models represent stratigraphy with no arm waving allowed? There needs to be a way to compare models to outcrop and the subsurface. To compare models with the rocks we need metrics based on measurable quantities from subsurface or outcrop. Examples of measurements that scale from models to the rocks include things like the bed thicknesses, clustering metrics, grain size proportions, and connectivity metrics. With these metrics geologists tune forward models to match measurements in stratigraphy and gain further insight.

In conclusion, what you need to know about quantitative stratigraphy and geocomputing is that modelling is only half the battle. The other half is using quantitative methods to compare models to real world measurements to test your models.

Welcome to arm-wavers anonymous.

## References
Galewsky, J., 1998, The Dynamics of Foreland Basin Carbonate Platforms: Tectonic and Eustatic Controls. Basin Research, v.10, p. 409-416.
