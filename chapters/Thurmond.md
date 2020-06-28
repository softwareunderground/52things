
# Overcoming the tyranny of formats

Format conversion is a great way to get started in programming, because the challenges are usually very simple, and it opens up an enormous toolbox that becomes useful for almost everything else you will ever have to do, even if you never go any further with programming. Without this skill, you can only work with formats that your software can read and write, which can quickly stymie good ideas.

When I first started working with 3D data, I was lucky enough to have learned some simple programming and was comfortable reading and manipulating data. At the time, 3D polygonal mesh construction and editing was an esoteric art. Software vendors mostly used their own formats, and format exchange programs were either non-existent or prohibitively expensive. To do the work I knew I wanted to do, I had to figure out how to convert between different formats. What I didn’t know at the time was that this was a remarkably simple problem.

Like most data files, 3D polygonal mesh formats are made up of very simple structures. The main information is a sequence of points or _vertices_ with (_x_, _y_, _z_) positions, and set of _faces_ that describe how to connect these points. Additionally, the files were typically just plain text!  

For example, here's how to encode a simple triangle in Wavefront OBJ format:

    v 0.0 0.0 0.0
    v 0.0 10.0 0.0
    v 10.0 0.0 0.0
    f 1 2 3

And here's the same triangle in 3D Systems STL format:

    facet
    outerloop
     vertex 0.0 0.0 0.0
     vertex 0.0 10.0 0.0
     vertex 10.0 0.0 0.0
    endloop
    endfacet

If you can program just enough to read in an array of vertices and faces, converting between these two formats is nothing more than a little book-keeping and outputting the right text.

Once I understood this basic building block, I put together a set of very simple scripts that allowed me to convert between formats and connect the capabilities of various software tools.  To others, this seemed like a magic wand that allowed me to do things that they could not, but in reality it was only a few hundred lines of code. I carried this very useful toolbox around with me for years, but turned to it less and less as time went on and software limitations slowly vanished.

Recently, I started working with 3D printing as a hobby. As it turns out, the STL format I had dealt with before is the de facto standard for the interchange of models for printing.  I put some of those old skills to work and built models that others hadn’t seen before, like a dual-color topographic model of the Gulf of Mexico (have a look at thingiverse.com/thing:617729). Being unafraid of working with 3D models and programming meant that it was easy to pick up OpenSCAD (openscad.org), and to use it to allow others to make their own customized geology block models for teaching (for example, thingiverse.com/thing:2222945), or more frivolous things (thingiverse.com/thing:1985430).

These days, there’s much more open sharing of code, and it’s easier than ever to find a format reader or converter already written for you, but I still see people thwarted by format conversion on a regular basis — for example, have a look at https://ageo.co/q2e3Wt.  Having even a rudimentary knowledge of programming and format conversion can be a skeleton key that opens up an incredible number of doors — sometimes even to unexpected places.

_Could add figure if room_
