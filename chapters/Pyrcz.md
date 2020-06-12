# Open source geostatistical geomodelling

Michael J. Pyrcz

Geostatistical geomodelling is strongly algorithm-based; therefore, its practice is dependent on requisite specialized algorithms. These algorithms build geomodels, spatial distributions of geological properties over a volume of interest. For example, a geomodel may include spatial estimates of rock lithology, porosity, and permeability inferred from available geological and engineering observations (e.g. outcrops, well logs, seismic attributes, flow rates etc.). For simulation workflows, multiple realizations are calculated to represent the unavoidable subsurface uncertainty. It is not feasible to do this by hand, nor on the back of an envelope. We need algorithms.

![Figure 1](../figures/Pyrcz.png)

> Figure 1. geostatistical geomodel with various types of geological observations and measurements integrated.

**What is important about these algorithms?** Firstly, these algorithms are designed to flexibly integrate the various previously mentioned information sources in a robust manner that avoids bias and artifacts. None of the algorithms are perfect, the models must always be checked. Secondly, these algorithms are designed to be efficient. Geomodels at the necessary resolution for solving typical subsurface problems are large. Hundreds of millions of model cells or more is common. The computational times must be short, tens of minutes or less, to support the typical empirical, iterative geomodelling workflows. Thirdly, these algorithms must be able to plug into these workflows and talk to each other and produce reasonable results most of the time. Given the broad sets of possible data types and geological settings there is a vast combinatorial of possible subsurface modeling workflows.

**Scientific progress in the geosciences continues to challenge these algorithms.** New data types emerge as candidates for integration such as CT rock core scans, well-bore image logs, micro-seismic and 4D seismic. New physics-based modeling approaches provide new subsurface spatial concepts. In some cases, the data and concepts may have outpaced the ability of the algorithms to model!

**To meet these challenges there are a variety of canned software solutions;** Petrel, Gocad, Roxar to name a few. These software products provide convenient geomodeling environments with database, 3D visualization, modeling interactivity, workflow development and automation, and result summarization and checking. Canned software typically provides general, black box, algorithms that support common modeling workflows.

**What is the advantage of open source?** For expert practice, it is important to be cognizant of what goes on under the hood. Open source offers this transparency. It may not be possible to address all geomodelling problems, unless one can expand or modify the algorithms. Open source may be freely modified to provide differentiated service. Open source harnesses the innovation of the community and often provides the most modern technological solutions.

Given these considerations, I often turn to open source geostatistical software for designing the numerical core of my geomodelling workflows. For example, the Geostatistical Software Library (GSLIB) by Deutsch and Journel (1989) offers a broad set of fundamental algorithms for data investigation, data debiasing, spatial characterization and modeling and model post-processing. Simple FORTRAN design and a common library of subroutines facilitates algorithm review in minutes. Furthermore, various contributors have expanded the original algorithm catalog with programs that address new developments in the field. Remy, Boucher and Wu (2011) have provided an updated Stanford Geostatical Modeling Software (SGeMS) that includes a graphical interface, 3-D visualization along with new modeling algorithms.

In response to the Python tidal wave in the scientific community, various authors have developed packages such as PyGSLIB (Vargas, 2019), GeostatsPy (Pyrcz et al., 2019) and geostatsmodels (Johnson, 2019). These packages utilize or reimplement the original GSLIB FORTRAN libraries while enabling very flexible workflow design in Python. Additionally, geostatistical geomodelling workflow design in Python opens a world of opportunity through the various packages that support data investigation and cleaning, data mining, mathematical modeling, results summarization and promulgation. Therefore I use (and contribute to) open source to do much of my spatial data analytics and geostatistical geomodelling.

## References

Remy, N., Boucher, A., and Wu, J., 2011, Applied Geostatistics with SGeMS: A User’s Guide, Cambridge University Press, 286 p.

Deutsch, C.V. and Journel, A.G., 1997, GSLIB: Geostatistical Software Library and User’s Guide. Oxford University Press, 384 p.

Johnson, C., 2019, geostatsmodels, Python Package Index, https://github.com/cjohnson318/geostatsmodels.

Pyrcz, M.J., Liu, W., Kupenko, A., and Gigliotti, A, 2019, GeostatsPy, Python Package Index, https://pypi.org/project/geostatspy/.

Vargas, A.M., 2019, PyGSLIB, https://opengeostat.github.io/pygslib/.
