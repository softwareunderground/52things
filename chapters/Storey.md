# De Profundis – Of well depth

Martin Storey

How deep is your well?  Where did our well go?  These questions are less facetious than they may seem.  Sure, we want to avoid collisions between wellbores, but that is still an unusual requirement.  We want to know “exactly” where our prize lies and how big it is.  But first of all, we want to integrate data, and that requires a good depth.

The geotechnical experts in a subsurface team are able to work together in spite of their different data types, software tools and lingo, because they share a common reference.  In wells, that reference is usually well depth.  Yet depth is a measurement too, and far from being the same for everyone, it is potentially different for each data set acquired in the well.  That problem is often conveniently overlooked or underestimated.  The resulting incremental errors and uncertainties are difficult to characterize and to quantify, yet they can be easily mitigated through good practices, team work and the use of appropriate technology.   

Every depth-indexed data item has at least two depths: that at which it was acquired, and its depth in the common reference system.  In our geocomputing environment, all depth-indexed data should related to this common reference.  An essential duty of an organisation is to select a reference depth, and to document it formally.  

For wells drilled to several thousand metres below ground, conventional wisdom has it that depth measured methodically using an electric wireline logging system is the most accurate and precise.  That is what has traditionally been used for reference for both absolute and relative depths – i.e. locations in the well and thicknesses, respectively.  

In recent years however, wells have often been logged with Logging While Drilling only, or perhaps a few wireline logs have been run at the very end of the well drilling operations.  In some extreme but by no means uncommon cases, the best depth measurement in a well is based on cuttings descriptions and the drillers’ tally.  

The choice or definition of the reference depth remains the organisation’s prerogative, but considering that the well data will outlive all of us and will be handled by and diffused to many other organisations, it pays to conform to common practices, and to consult and communicate widely about how best to do evolve these.  

The dividend of good practices is not rhetorical: as soon as two data items are used jointly or integrated, results will fall into place more readily and more reliably if their depths have been conditioned beforehand.  As examples: a porosity measured on a fullbore core plug should not be compared to a log-derived porosity without a depth match; a density and an acoustic slowness log should not be combined to construct synthetic seismograms without having been depth matched, even if they were acquired in the same logging run (ask your petrophysicist if this surprises you, or take one’s word for it); free fluid surfaces should not be defined between wells that use an electric wireline depth measurement and others that use LWD depths, without correcting for the inconsistency.

To do the right thing, every mention of a depth should feature:

- A unit – typically metres or feet
- A trajectory – e.g. “measured depth” (a.k.a. “along hole depth”) or “true vertical”
- A reference or origin – e.g. “Rotary Table”, “Drill floor”, “Ground Level”, “Casing Bowl Flange”, “Mean Sea Level” or a locally prescribed permanent datum, etc.  Please don’t use “Sub Sea” which can have a range of different meanings and is sure to cause errors: below the sea surface, the mean sea level, the lowest astronomical tide, the sea floor…?
- A measurement system – “core depth”, “loggers’ depth”, “LWD depth”, “Drillers’ depth”, or preferably “Reference depth”
- A wellbore identification – e.g. “well ACME-1, sidetrack 1” - unless there is only one for the well.
Granted, it’s a bit tedious, but that’s a small effort to avoid the hassles of figuring out what an incompletely depth specification was meant to be, or the unknown costs of errors we make when we combine data items that have inconsistent depth handles.  
