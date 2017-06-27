# Best Practices are not (always) the best approach

I am one of the only people in my research group with much of a programming background. Accordingly, I have spent quite a lot of time helping other people with relatively simple scripts for data analysis. This leads to some interesting observations from time to time. A good example of this is some processing scripts that I wrote for a piece of equipment that reads various chemical abundances in gas (in parts per million). Unfortunately, it has no spatial awareness, which means that doing 'drive-around' surveys and sampling as we travel is not something that can be done out of the box. Fortunately, one can obtain a GPS-based location logger that can be easily put into a car and pull out the location at a specific time. Even more fortunately, their sampling rates are about the same, so one can match the timestamps at about second-level accuracy to put a location on a given reading.

Since that was the first priority, I hacked together a fairly ugly bit of code, using python and pandas to do just that. It goes against all the usual rules: the location of the file is hard-coded as a string, as are the locations to save a couple of plots and the combined data file. So you have stuff like the following:

    root = 'C:/Users/mtb/Documents/GitHub/gas_processor/'
    data_root = root + '20170313/data/'
    picarro_file = data_root + '20170313_readings.csv'
    gps_file = data_root + '20170313_gps.csv'

Clearly this is bad design. But my colleague was perfectly happy with this (partly because it means that he does not have to manually match a reading to a location).

I then wrote a second script, to simplify the extraction of the locations from the kml, and combine sequential data files (since the equipment creates a new log every hour or so). These would then be used as input to the first script, and save a bit of mucking about in Excel and copy-pasting data. I decided to push the boat out a little and made it much better, with a series of command line arguments that could stitch an arbitrary number of arbitrarily located files:

    usage: process_data.py [--kml] [-o O] [-t TIME_ADJUST] files [files ...]

`--kml` is a boolean means that we need to extract points from a kml file (defaults to false), `-o` is the location to save the combined file to, `-t` is to account for a delay in gas getting to the sensor as one drives, and `files` are the files to be combined.

Despite being "better", my colleague preferred the approach of the other script, because passing things on a command line is something completely foreign to them. They preferred to just go and edit the source file to point at their data, because it was more obvious what was being changed. They also did not need to think about relative locations of data files and the script.

Partly this is something that can be addressed by education, and after a bit of a lesson in how the command line works, they can now use the script. But it might still be better for their use-case to just edit it to something less sophisticated and hard-code the locations of things in again.

If you are writing stuff for non-technical users, their approach and way of thinking about a given piece of software might be markedly different to your own. Something that is emphasised in proper software development courses is usability testing. Even, possibly especially, when writing software that will be used by non-programming colleagues that is intended to solve a specific problem that is unlikely to have broader outside use (taking two datafiles from two specific pieces of equipment and mashing them together to enable further analysis, for example), we need to make sure that they are comfortable with using it. And if that means that you need to let some best practices slide, I think that that is an acceptable compromise in places.
