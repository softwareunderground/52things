I am one of the only people in my research group with much of a programming
background. Accordingly, I have spent quite a lot of time helping other people
with relatively simple scripts for data analysis. A good example of this was a
piece of equipment that reads various chemical abundances in gas. Unfortunately,
it has no spatial awareness, which means that doing 'drive-around' surveys and
sampling as we travel is not something that can be done. Fortunately, one can
get GPS-based location loggers that can be easily put into a car. Even more
fortunately, their sampling rates are very similar.

The GPS logger can give you positions at a particlar time in a kml file (which
is just a specialised xml file) and the equipment outputs space-delimited data.
So one could, in theory open both up and match the time of the reading and add
a location to the space-delimited table, and from there import it into a GIS of
some kind and plot variations in air composition. In theory, sure, but in
practice, this is utter madness. Remember that I said that the sampling rates
are very close? The analytical equipment sometimes takes two readings in a
second, and other times skips a second. The GPS is strictly once a second. So
to do this manually you would not just be able to drop a block of GPS locations
in a couple of new columns at the end of the data file.

You need to write a bit of software. So, my colleagues turned to me. This is
pretty simple, low-level stuff to actually do: find matching times in two
different files, and add the data from one file to the end of that row. My
weapon of choice for something like this is the python module `pandas`, since
it deals very nicely with tabular data. So I wrote a bit of code that did the
glueing:, the meat of which comes down to the following pseudocode:

    combined = merge(df1=gps_data, df2=air_data, on_column='Time', outer_join=true)

So, now we have script that can glue our two different datafiles together. If
we were putting all of this stuff into a database, this would probably be easier,
but a simple utility script like this does not take too long to set up. There
are still a few bugbears though: the location data is in a kml, and there is a
new datafile created every hour or so.

So, turning back to python, we can pull out specific tags from an xml file
(which will work on a kml as well). These can then be written to a file and
passed onto the script. This same script, with a little tweaking, can combine
multiple kml files. So if we ignore the kml-specific tag extraction, we can
use it to combine our data files as well.

After a day or two of programmer time, we have a much quicker and easier
workflow than trying to extract tags and match timings manually:

1. Get the datafiles off the equipment.
2. Get the kml of the track(s) from the GPS logger
3. Pass the datafiles through the combiner.
4. Pass the kml files through the combiner.
5. Give both the locations and the combined datafiles to the glueing script.
6. Take the glued information into whatever spatial analysis tool you favour.

So why am I telling you this? Because there are huge amounts of these little
problems in (geo)science. My colleagues are going to have a hugely easier time
processing and analysing this data now. It is the sort of thing that could be
done by pretty much any decent programmer (I mean, I managed it). But they are
not programmers; they do chemical stuff and groundwater stuff. Having someone
around who can spend a day writing code that solves the little niggles in the
data nalytics process is a good second place to trying to teach people to code
for themselves. And it might not be the most amazing code, but it works for
what they need to do, and will get them on their way faster, which I think is
good enough for me, and, more importantly, them.
