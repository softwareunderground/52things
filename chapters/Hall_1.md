# What's so special about geoscience?

> Matt Hall


I expect transformative, revolutionary developments in geology and geophysics in the next decade or two. Advances as profound as deep time, plate tectonics, and sequence stratigraphy. As these breakthroughs were data-driven, so too will the coming revolutions. The difference is that a substantial chunk of the analysis will not be performed by humans, but by computers. 

By 'analysis', I don't mean 'data storage', or 'chart-making', or 'statistical calculation'. I mean that computers will learn for themselves how to solve important problems in geoscience, at an unprecedented scale, and then show us their conclusions. (And if we're clever about it, they will also show us their working &mdash; the matrices of weights in their neural networks &mdash; which we may even learn new geoscience from. But that's for another essay.)

These revolutions will not just be of academic interest. If humans are to continue to make social and economic progress without corrupting Earth's natural systems, I believe that  humans need artificial Earth-intelligence systems &mdash; geoscience AIs &mdash; and that this is the community to build them. To leave it to the computer scientists would be to lose centuries of insight into the earth's hardware and software. I'm not ready to accept that computers can start from scratch, or that computer scientists will know what kind of data to provide for them. Besides, we'd miss out on all the fun.

I'd go a step further: I am convinced that geoscience AIs _cannot_ be built without geoscientists. While it's clear that other researchers are making amazing headway on some very hard tasks, I think our problems in geoscience are different from those of other AI researchers. I think we will need new machine learning approaches and network architectures to attack them. You can't predict earthquakes with support vector machines.

Why is geoscience different from any other arena? I think there are four things &mdash; maybe you can think of others:

**Huge space-time bandwidth.** Geoscience grapples with nanometres and gigametres, microseconds and exaseconds (or, in terms of rates, attohertz and megahertz). That's about 18 orders of spatial magnitude, and 22 orders of temporal magnitude. Few other natural sciences deal in such broad bands &mdash; perhaps cosmology.

**The indirectness of our measurements.** We often don't get to measure the thing we really want to measure. For example, we can't easily get at the mud content of rocks down a borehole, so we measure natural radioactivity with the gamma-ray tool because muddy minerals tend to contain more radioactive elements like potassium and uranium. We can't get at porosity so we measure the attenuation of neutrons. We can't get at the amount of oil or gas present so we measure the conductivity of the rock-fluid system. The indirectness introduces a raft of other questions: Was the instrument calibrated properly? Do we really understand the physics of the measurement? Should we feed a neural net the raw measurements, or should we transform our data as we would for a geologist?

**The high dimensionality of our measurements.** At least in most physical experiments, the investigators get specific and accurate answers to their specific questions, like "what is the energy of this interaction?" or "how many cobras does a honey badger eat at one sitting?". Meanwhile in geoscience, we can't even answer a simple question like, "what's the porosity of this rock?". Which bit of the rock? When in geologic time? What's the pressure? Are we counting disconnected, inaccessible pores? What about the space between sheets of clay? There are more ways of answering the question than of asking it.

**The expense of repeated experiments.** The British AI research company DeepMind broke new ground in 2013 with their Atari-playing deep-Q-network, which learned from its mistakes by so-called reinforcement learning (Mnih et al. 2013). This brilliant idea is easy to implement when the cost of a new game is essentially zero. But such repeated games are not possible when you're sampling the earth 4000 m down an 8-inch hole. (There's a very quick path to more data, however: open data! Again, a topic for another essay.)

**The complexity of the earth's dynamic systems.** The imperfect sampling of the 3D, scale-free product of manifold processes, each as complex as the whole, is an implicitly complex problem. Reconstructing earth history from a few bits of sidewall core and half a dozen wireline logs is a comically ill-posed inverse problem. Every aspect of it is orders of magnitude harder than interpolating frames in a cat video.

We're lucky enough to be facing some of the most exciting developments in the ancient craft of data analysis. It's up to geoscientists to grasp these tools with both hands, and apply them to some of the most profound, computationally daunting challenges in natural science.

Long live the revolution!


## References and acknowledgments

Mnih, V, K Kavukcuoglu, D Silver, A Graves, I Antonoglou, D Wierstra, M Riedmiller. Playing Atari with Deep Reinforcement Learning. NIPS Deep Learning Workshop 2013. arXiv:1312.5602.

This essay was developed from part of my keynote at the annual conference of the European Association of Engineers and Geoscientists in Paris in June 2017.
