## SEGY: Judging books by their covers.

The Society of Exploration Geophysicists seismic data exchange format (SEG-Y) shares a lot of similarities with books. All books have a cover; a series of numbered pages;  each containing text or pictures. Similarly, all segys have file headers, trace headers and data traces.

The publication industry has emerged that oversees the exchange of information via books. This industry has conventions around information encapsulation that includes cover formats, blurb location, ISBN numbers and author attribution. Without exception, every book publisher follows these conventions. 

The geophysical industry lacks a similar orthodoxy around the data encapsulation for SEGY. Unsurprisingly, this makes the reading of poorly documented seismic data near impossible. Why has a rigidity to our industry’s norms failed to materialise? The reasons for this are many and varied. The textual header format recommended is very North American centric. The standard has not kept pace with the variety of datatypes using SEGY. Software output generic textual headers with little default data context or opportunity for change. Data creators don’t understand how important it is to correctly encapsulate their data, and data recipients fail to demand higher standards. All of these issues are fundamentally behavioural and will not disappear by moving to a new data standard. People have criticised SEGY as an archaic format, but most reported issues can be solved by rejecting the idea of exchange as an ad-hoc data transfer and embracing a data publication mentality.

The very first thing read when loading a SEGY file is the textual header, so this header is akin to a book cover. All books regardless of their type have the following on or near their cover; a title, a blurb and author/publisher, a publication location, a language and a statement of copyright. 
Similarly all SEGY textual headers need similar:
1. Title –  Dataset Summary (4-5 lines)
This section contains at a minimum, the survey/well name, general location of the data, permits ingressed, data type, and data extents.
2. Blurb and Author –  Dataset History (15-20 lines)
This section contains every thing that has been done to this dataset since it was acquired and who did it. It generally includes a number of sections; acquisition; processing; imaging; post-migration data conditioning; calibration; inversion.
3. Publication location - Dataset CRS and geometry (4-5 lines)
This contains what CRS the data is in; the corner points, bin spacing and extent of the 3D grid; Shotpoint and CDP extent and relationship for 2D lines.
4. Language – Trace Header description. (4-5 lines)
Trace headers in the file needs a label, a byte header location and a format statement.
5. Copyright- dataset owner (1-2 lines)
Is this data openfile, proprietary or multi-client? Who owns the data. Who can I contact about buying it?

An example of such a header is shown below in figure 1.
Link to figure: https://github.com/softwareunderground/52things/blob/master/figures/Dinneen_Figure1.png

The textual header IS the location this information. Filenames are lost when data is transcribed to tape. Internal datamodels of geotechnical software rarely allow attaching reports and documents to seismic data. It is only by embedding this vital information in the most visible part of the file that you can be sure that is will be kept with your data, forever.

So how can you help? 
If you are delivered data; demand higher standards. Look at the textual header and ask yourself, "is this a satisfactory summary of this data?” and “Can this data be read using only the information here". If the answer is no, send it back to the source and ask for it to be done properly.
If you create data, take the time to write a header using the above.

Fundamentally we must as ourselves, what does the cover of my book say about the quality of my work, after all, we all judge books by their covers.
