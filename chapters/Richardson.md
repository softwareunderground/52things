# Use standard, not specialized, file and problem formats

In The Cathedral and the Bazaar, Eric S. Raymond discusses two models of code
development. He calls these the Cathedral and the Bazaar. The former occurs
when a closed group of developers works on a code, whereas in the Bazaar, 
anyone who has an idea can contribute. As suggested by the name, the latter 
is a more vibrant model and can adapt quickly to changes. The book was
published in the 1990s, and, since then, the Bazaar model has become almost
synonymous with open source code, especially since the likes of Github easily
enable community code contributions.

I believe the idea goes beyond development style. Even if a geoscience code is
open source and its repository is on Github, contributions from non-geoscientists
are unlikely. Development is thus still limited to a closed community, like
the Cathedral. It may feel like there are a lot of people working in
geoscience, especially when you are at the AGU or SEG annual meeting, but
limiting development to this group excludes many capable people and reduces
the diversity of contributors. With more effort to use tools, techniques, and ways of posing
our problems that are common outside our discipline, we might be able to
improve this.

As an example, exploration seismic datasets are often stored in SEG-Y format.
There are undoubtedly some advantages to using a specialized format that was
designed specifically for our problems, but there are also many disadvantages.
An expert in machine learning who has an idea for a new seismic inversion
method would need to learn about SEG-Y files and find a tool (from the small
range available) for reading them before the idea could be tested. If we instead
stored seismic data in a more general and widely used format, such as HDF5,
then there would be lower barriers to entry.

A lot of geoscience problems involve using measurements to make predictions.
Applying an operator, possibly non-linear, to the measurements transforms them
into the predictions.
In remote sensing applications like seismic imaging, this is obvious, but
other problems can also be posed in this way. For example, in seismic 
interpretation the measurements are the pixel values of the seismic image and
the predictions are subsurface structures such as horizons and faults.
Applying a neural network classifier to the pixels can transform them into the
predictions. The advantage of posing problems in this way is that this is the
typical form used in data science. The problem then becomes recognizable to
large new groups of researchers and developers, and the tools and techniques
developed for other fields can be more easily applied.

Kaggle competitions are an example of what can be achieved when artificial
barriers of specialization are removed. Past competitions have ranged from
recognizing lung tumors in chest X-ray images, and predicting rainfall quantity
using doppler radar data, to identifying a rare decay phenomenon in Large
Hadron Collider data. By posing the problems in a standard data science form
and using well known data formats, people from diverse backgrounds are able to
work on them. I am sure specialists in those areas previously believed
it would be impossible for an outsider to quickly start working on their
topic, and maybe to even develop a model that outperforms
those conventionally used in their discipline.

Using standard, rather than specialized, approaches is not only healthy for
the field, but also benefits geoscience developers. I previously alluded to
the paucity of SEG-Y tools. Anyone who has worked with this format has
probably experienced the frustration of trying to use them. With a small target
market, it is unlikely that the situation will ever dramatically improve.
The solution is to switch to a more widely used format, thus benefiting from
a larger community of tool developers.

Let us avoid the isolationist Cathedral model that leads to stale code, and
instead embrace the Bazaar.
