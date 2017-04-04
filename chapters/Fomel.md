# Reproducible Research

Sergey Fomel

"Reproducible research" is a term coined by Jon Claerbout, a famous geophysicist and Cecil Green Professor Emeritus at Stanford University. In 1991, while working on his third book, _Processing Versus Inversion_, Claerbout made the following observation:

> It is a big chore for one researcher to reproduce the analysis and computational results of another […] I discovered that this problem has a simple technological solution: illustrations (figures) in a technical document are made by programs and command scripts that along with required data should be linked to the document itself […] This is hardly any extra work for the author, but it makes the document much more valuable to readers who possess the document in electronic form because they are able to track down the computations that lead to the illustrations. (Claerbout 1991)

Since its introduction in the early 1990’s, the concept of reproducible research has been spreading across different scientific disciplines that involve computations or data analysis. Many computational scientists became familiar with Claerbout's Principle via Buckheit and Donoho’s following formulation: 

> An article about computational science in a scientific publication is not the scholarship itself, it is merely advertising of the scholarship. The actual scholarship is the complete software development environment and the complete set of instructions which generated the figures. (Buckheit & Donoho 1995)

This statement is easy for mathematicians to understand if they think of an analogy with theorem proofs (Leveque 2013). A theorem without proof, which might be presented at a mathematical convention, is certainly not the scholarship but merely an advertising of the scholarship. To be able to verify the validity of a theorem and, more importantly, to be able to use it for deriving new theorems, it is necessary to be able to examine its proof. Similarly, access to the details of a scientific computation is often necessary to be able both to verify the correctness of a published result and to extend it to new computations.

In the geophysical community, reproducible research is fully supported by the Madagascar open-source software package (Fomel et al 2014). Madagascar provides not only software tools for making geophysical computations but also research papers complete with links to data and reproducible data-analysis workflows. When researchers discover a research paper published on the Madagascar website (www.ahay.org) and install Madagascar, they are able to replicate all computations and verify the published computational results. Of course, reproducibility is not the goal in itself (Fomel 2015). The goal is to be able to extend previously published research by, for example, trying new computations on previously used data or previously used computations on new data.

More fundamentally, the idea of reproducible research goes to the core of the scientific method. In order for science to fulfill its function of generating new knowledge, participants in the scientific research process must be able to inspect each other's results through the prism of skepticism and to independently verify the validity of the published results. The formal definition of Science by the American Physical Society states (http://www.aps.org/policy/statements/99_6.cfm):

> Science is the systematic enterprise of gathering knowledge about the universe and organizing and condensing that knowledge into testable laws and theories. The success and credibility of science are anchored in the willingness of scientists to expose their ideas and results to independent testing and replication by other scientists. This requires the complete and open exchange of data, procedures and materials.

In computational science, the complete and open exchange of data, procedures, and materials amounts to reproducible research. Whether you share your computational results only with people inside your immediate organization or with the world at large, you will quickly discover the power of reproducible research to generate new scientific knowledge.


## References

Claerbout, JF (1991). Electronic document preface, in SEP-72, Stanford Exploration Project, p 1–18.

Buckheit, J and DL Donoho (1995). Wavelab and reproducible research. In: _Wavelets and Statistics_, New York, Springer-Verlag, v. 103, p. 55–81.

LeVeque, RJ (2013). Top ten reasons to not share your code (and why you should anyway). _SIAM News_ *46* (3).

Fomel, S, P Sava, I Vlad, Y Liu, and V Bashkardin (2013). Madagascar: open-source software project for multidimensional data analysis and reproducible computational experiments. _Journal of Open Research Software_, e8.

Fomel, S (2015). Reproducible research as a community effort: lessons from the Madagascar project. _Computing in Science and Engineering_ *17*, p 20–26.
