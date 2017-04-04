# My favourite 10-line program

Dave Hale

I write a lot of software, but here is my favorite ten-line program:

    float b = 1.0f-a;
    float sx = 1.0f, sy = a;
    float yi = 0.0f;
    y[0] = yi = sy*yi+sx*x[0];
    for (int i=1; i<n-1; ++i)
        y[i] = yi = a*yi+b*x[i];
    sx /= 1.0f+a; sy /= 1.0f+a;
    y[n-1] = yi = sy*yi+sx*x[n-1];
    for (int i=n-2; i>=0; --i)
        y[i] = yi = a*yi+b*y[i]; 

Simon Luo, a Mines graduate student, recently helped to remove some clutter in a slightly longer version that I wrote awhile ago. Yes, we are cheating a little bit by putting two statements on one line, but our program still looks clean, with plenty of symmetry that makes us feel good. Besides, a real cheater would write this code in a one-line program!

This program is valid in the programming languages Java, C++, and (with a few minor changes) C. The program inputs are a float parameter a and a sequence of n float values x[i], for i = 0, 1, ..., n-1. The program output is a sequence of n float values y[i] with the same length. Before I explain why this is my favorite ten-line program, let's first look at an example of what it does.

In the following figure, the input sequence x in red was recorded in a lab experiment. We suspect that the rapid fluctuations are noise, because they do not fit any reasonable model of the signal we were expecting. The output sequence y(black) computed with our ten-line program better approximates the expected signal.

_Figure 1: A noisy input sequence (red) after smoothing (black) with the ten-line program._

Each output value y[i] is a weighted average of input values x[j]. The weights are proportional to a|i-j|, so that (for 0 <= a <= 1) they decrease exponentially with increasing |i-j|. In this example, the parameter a = 0.932.

In effect, our ten-line program is a smoothing filter. The weights are normalized so that they sum to one, which means that when this filter is applied to a sequence with constant input value x[i] = constant (already as smooth as can be), the output values will be the same y[i] = constant.

The following figure illustrates weights for the exponential filter and two alternative smoothing filters with comparable widths.

_Figure 2: Impulse responses of exponential (black), Gaussian (blue) and boxcar (red) smoothing filters. For these filters, each output sample is a weighted average of nearby input samples; shown here are the weights._

All three of these smoothing filters can be implemented efficiently, with computational cost that is independent of their width. But efficient (recursive) implementations of both the Gaussian and boxcar filters require more complex programs, especially when carefully handling the ends of input and output sequences.

A less efficient (non-recursive) but simpler implementation of the boxcar filter is often used, perhaps because it more obviously computes a moving average. But the abrupt transition from non-zero weight to zero weight makes no sense for such an average, and it is hard to beat the simplicity of our ten-line program.

To summarize, the exponential filter gives more weight to input samples located (in time or space) near the output sample than to input samples located farther away guarantees that all weights are non-negative, unlike many recursive implementations of Gaussian filters can be applied in-place, so that output values y[i] replace input values x[i]stored in the same array, which is especially useful when filtering large arrays of arrays that consume a lot of memory requires only six floating-point operations (multiplies and adds) per output sample y[i], and this computational cost is independent of the extent of smoothing can be implemented with a simple ten-line computer program that includes careful treatment of the ends of input and output sequences.

Careful treatment of the ends is important. When averaging input values to compute output values near the ends, our ten-line program listed above implicitly assumes that input values beyond the ends are equal to the end values. This zero-slope assumption is often appropriate.

Another common assumption is that input values beyond the ends are zero, and the figure below shows how this zero-value assumption may be inappropriate, as the decrease in the output sequence near time zero seems inaccurate.

_Figure 3: A noisy input sequence (red) after smoothing (black) with the recursive two-sided exponential filter. Input values off the ends have been assumed to be zero, which seems unreasonable for the left end where times are nearly zero._

But suppose that the data we are smoothing are known to have zero mean. In this case, the zero-value assumption may be more appropriate, and our ten-line program becomes

    float b = 1.0f-a;
    float sx = b, sy = a;
    float yi = 0.0f;
    y[0] = yi = sy*yi+sx*x[0];
    for (int i=1; i<n-1; ++i)
        y[i] = yi = a*yi+b*x[i];
    sx /= 1.0f+a; sy /= 1.0f+a;
    y[n-1] = yi = sy*yi+sx*x[n-1];
    for (int i=n-2; i>=0; --i)
        y[i] = yi = a*yi+b*y[i]; 

Can you see the difference? It is not obvious, but look carefully at the second line. That's it! A simple change to the initialization of one variable switches our treatment of the ends from zero-slope to zero-value.

One final tip. The relationship between the extent of smoothing and the parameter ais not at all intuitive, so I rarely specify this parameter directly. Instead, I compute the parameter a to obtain an exponential filter that (for low frequencies) is comparable to a Gaussian filter with a specified half-width sigma (measured in samples), using:

    float ss = sigma*sigma;
    float a = (1.0f+ss-sqrt(1.0f+2.0f*ss))/ss; 

So, in practice, this adds two lines to our ten-line program. And if you would rather think in terms of the integer half-width m of a boxcar filter, then (again, for low frequencies) the half-width sigma of the comparable Gaussian filter can be computed using:

    float sigma = sqrt(m*(m+1)/3.0f); 

For the boxcar filter with half-width m = 10 displayed in the figure above, these expressions yield sigma = 6.06 and a = 0.792.

_This chapter originally appeared [as a blog post](http://inside.mines.edu/~dhale/notebook.html#2012_08_13)._
