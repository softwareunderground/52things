# A 5-minute introduction to HCP

George Bisbas

# Introduction
The need to execute complex and demanding problems at scale is more imminent than ever! The rise of big data and the requirements for just in time solutions made HPC a dominant research area in our days. Typical examples that may be encountered in real-life can be the following: Scientists of various fields need to cross-validate their model. 1000 runs are required but every one of them takes an hour. Running on their local desktop may take over a month! A biologist has been using small datasets of DNA sequence data, but a new model is 10 times as large. Opening the data in his PC is already challenging. Processing the larger dataset will probably crash it.

In these cases as well as a lot more ones, what is needed is computer power than can be used in sync. Large scale computing systems – shared computing resources with lots of computers – are available at many universities, labs, or through national networks. These resources usually have more processors, that operate at higher speeds, more memory, more storage, and faster connections with other computer systems. They are often interchangeably called “clusters”, “supercomputers” or resources for “high-performance computing” or HPC.

# Some Terminology 

* What is High Performance Computing (HPC)? Computing resources that allow people to solve their problems faster or treat larger problems than they would be able to use standard computing resources (e.g. a laptop, desktop, or workstation). Usually implies some sort of parallel computing.
* What is Parallel Computing? The use of computing resources in parallel to speed up computation or treat larger computational problems.
* What is a Supercomputer? Typically used to describe a very large HPC resource such as those found on the Top500 list. Often uses the same technology as compute clusters but at a larger scale.
* What is a Compute Cluster. Typically used to describe a smaller HPC resource than those referred to as supercomputers. Usually, use exactly the same technology as supercomputers but on a smaller scale.
* What is High Throughput Computing (HTC)? A subset of parallel computing where computing resources are used in parallel on many independent sub-tasks to increase the rate at which computation can be performed. For example, varying an input parameter (or input data) to computation and running many copies simultaneously.
* What is Cloud Computing? Using remote computing resources on demand. Often associated with using public cloud computing resources provided by large internet corporations.


# Advantages of HPC
Although HPC systems often have slightly more powerful processors, more memory and more storage the real additional power comes from using the resources in parallel rather than in serial. Using an HPC system often has the following advantages for researchers:

* Speed. With many more processing cores, often with higher performance specs, than a typical laptop or desktop, HPC systems can offer significant speed up.
* Volume. Many HPC systems have both the processing memory (RAM) and disk storage to handle very large amounts of data. Terabytes of RAM and petabytes of storage are available for research projects.
* Efficiency. Many HPC systems operate a pool of resources that are drawn on by many users. In most cases when the pool is large and diverse enough the resources on the system are used almost constantly.
* Cost. Bulk purchasing and government funding mean that the cost to the research community for using these systems is significantly less than it would be otherwise.
* Convenience. Maybe your calculations just take a long time to run or are otherwise inconvenient to run on your personal computer. There’s no need to tie up your own computer for hours when you can use someone else’s instead.

# Getting started in the world of HPC

Getting familiar with HPC is not easy and is not meant to be achieved through this chapter. In order to get a first taste o HPC we suggest following these tutorials:

* OpenMP tutorial: https://computing.llnl.gov/tutorials/openMP/
* MPI tutorial https://mpitutorial.com/tutorials/
* CUDA tutorial https://www.tutorialspoint.com/cuda/index.htm



## References

* [Online]https://epcced.github.io/hpc-intro/00-why-hpc/, CC BY 4.0 license.

