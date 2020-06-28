# Is Geology Cartesian? 

## Guillaume Caumon and Bruno Levy

Geocomputing is about processing and interpreting geo-data, realizing physical simulations 
and solving inverse problems. All these tasks somehow call for approximating time and space 
by discrete points, some associated values, and their neighborhood relationships used to 
connect the points. 
 
Grids typically implement these principles, but which grids should be 
used in geocomputing (*Fig. 1*)? Cartesian grids have many qualities, owing to their
structure and regularity. Neighborhoods are trivially defined. 
Many great image processing algorithms, geophysical methods, geostatistical 
algorithms, and other useful numerical techniques directly apply to 
Cartesian grids. A computer screen is a grid. Most computations in 
reflection geophysics use Cartesian grids, and produce excellent 
images of the subsurface. 

Yet, a vast community of geoscientists and physicists, not only in the academic
world, has spent much effort to develop codes on **irregular** and **unstructured grids**.
For example, reservoir engineers and hydrogeologists use deformed Cartesian grids 
(also called corner-point or geocellular grids, see for instance [DuMux][]). 
The bravest use fully unstructured 
grids (made of tetrahedra, prisms or even arbitrary polyhedra). From a programming 
standpoint, these grids are scary. Many of the efficient algorithms designed for 
Cartesian grids fall apart when considering irregular geometry and arbitrary 
connectivity. Parallelization remains possible, but is more difficult to implement. 	
Still, in addition to commercial software, several open-source packages exist 
nowadays to work effectively with unstructured grids, for example: 
 * Generic meshing and geometric libraries: [TetGen][], [GMSH][], [Geogram][], [MMG][], [CGAL][].
 * Numerical simulation packages: either generic ([Moose][], [FreeFEM][], [MFEM][]) or specialized ([OpenFOAM][], [SeisSol][]). 
 * Integrated geocomputing platforms: [OpenGeoSys][] , [RINGMesh][], [OpenGeode][].

[TetGen]: http://wias-berlin.de/software/tetgen
[GMSH]: http://gmsh.info
[Geogram]: http://alice.loria.fr/software/geogram/doc/html/index.html
[MMG]: http://www.mmgtools.org
[CGAL]: https://www.cgal.org
[DuMux]: http://www.dumux.org
[Moose]: https://mooseframework.org
[FreeFEM]: http://www.freefem.org
[MFEM]: http://mfem.org
[OpenFOAM]: http://www.openfoam.com
[SeisSol]: http://www.seissol.org/
[OpenGeoSys]: http://www.opengeosys.org/project/publications
[RINGMesh]: http://ring.georessources.univ-lorraine.fr/software/ringmesh
[OpenGeode]: https://github.com/Geode-solutions/OpenGeode

![Fig. 1](../figures/Caumon.png "Four possible meshes representing the same geological structure (a thrust fold in Corbieres). Courtesy of Arnaud Botella.")
*Figure 1*: Four possible meshes representing the same geological structure (a thrust fold in Corbieres). Courtesy of Arnaud Botella.

Why did unstructured grids come up? This may be explained by some 
fascination for pretty pictures and a form of mathematical beauty of these meshes. 
But there has to be something else to justify investment in the business and 
engineering world.

We suggest that a stronger reason holds in the classical quote attributed to Albert 
Einstein: "Everything should be made as simple as possible, but not simpler". 
 
* **Geometry / discontinuities.** 
  Geological processes are a tremendous engine to create geometrically complex 
  changes of physical parameter fields; these changes can be quite abrupt, as two 
  rock samples 1cm away one from another may have been formed million years apart.  
  Such sharp geological features may have arbitrary geometries, which is generally 
  approximated in Cartesian grids as stair-steps. This may (or may not) be 
  a problem, depending on the application at hand. Explicit representation of 
  geological objects can be essential to focus on geological details deemed important 
  for a particular purpose. This is exemplified for instance in the area of fracture 
  modeling. Studying  fracture growth, quantifying fault reactivation and displacement 
  needs an acurate geometric representation. The connectivity of fractures is also a very important 
  point when it comes to understand subsurface flow. As fractures seldom align on 
  orthogonal directions, their explicit representation is very useful at some point
  (e.g., [Matthai2009], [Bonneau2016]). More generally, an accurate geometric 
  representation of subsurface geologic features is important to create benchmarks 
  such as the SEAM model; homogeneized parameter field on Cartesian grids can then 
  eventually become handy [Cupillard2015]. 
* **Adaptivity.** 
  With Cartesian grids, the grid block size corresponds **everywhere** to the size of 
  the smallest feature that you want to represent. This is generally fine in two dimensions 
  (digital pictures have the same limitations and are still very good "digital eyes"), 
  but raises significant computational challenges in three-dimensional domains. 
  Moreover, the Earth remains mostly inaccessible to observations. Practioners, therefore, 
  make compromises by averaging some (expensive) borehole measurements at flow 
  simulation block scale; conversely, values away from observations 
  are poorly constrained and are sampled using geostatistical methods, 
  even in the areas where heterogeneity has little or no impact. 
  With unstructured grids, the element size can vary according to the dimention of the 
  features that matter (See for instance [Sambridge2005] for further discussions in seismology).  

All in all, unstructured meshing technology, once restricted to CAD/CAM applications, has matured 
to handle realistic geometries of geological features. 
We believe this is now the right time to use these technologies to address longstanding 
geocomputing challenges. 


## References

[Bonneau2016]: Bonneau F et al. (2016). Impact of a stochastic sequential initiation of fractures on the spatial correlations and connectivity of discrete fracture networks. Journal of Geophysical Research - Solid Earth, 121:5641-5658. 

[Cupillard2018]: Cupillard P and Capdeville Y (2018). Non-periodic homogenization of 3-D elastic media for the seismic wave equation. Geophysical Journal International, 213(2):983-1001

[Nick2011]: Nick HM and Matthäi SK (2011). Comparison of Three FE-FV Numerical Schemes for Single- and Two-Phase Flow Simulation of Fractured Porous Media. Transport in Porous Media, 90:421-444

[Sambridge2005]: Sambridge M and Rawlinson N. (2005). Seismic Tomography with Irregular Meshes. In: Seismic Earth: Array Analysis of Broadband Seismograms, AGU:49-65





