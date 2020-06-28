# My favourite 10-line program

> Dave Hale

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

Simon Luo, a Mines graduate student, recently helped to remove some clutter in a slightly longer version that I wrote a while ago. Yes, we are cheating a little bit by putting two statements on one line, but our program still looks clean, with plenty of symmetry that makes us feel good. Besides, a real cheater would write this code in one line!

This program is valid in the programming languages Java, C++, and (with a few minor changes) C. The program inputs are a float parameter `a` and a sequence of `n` float values `x[i]`, for `i` = 0, 1, ..., (`n` – 1). The program output is a sequence of `n` float values `y[i]` with the same length. Before I explain why this is my favorite ten-line program, let's first look at an example of what it does.

In the figure, the input sequence `x` (grey) was recorded in a lab experiment. We suspect that the rapid fluctuations are noise, because they do not fit any reasonable model of the signal we were expecting. The output sequence `y` (black) was computed with our ten-line program and better approximates the expected signal.

Each output value `y[i]` is a weighted average of input values `x[j]`. The weights are proportional to `a|i-j|`, so that (for 0 <= `a` <= 1) they decrease exponentially with increasing `|i-j|`. In this example, the parameter `a` = 0.932.

In effect, our ten-line program is a smoothing filter. The weights are normalized so that they sum to one, which means that when this filter is applied to a sequence with constant input value `x[i]` = constant (already as smooth as can be), the output values will be the same `y[i]` = constant.

The following figure illustrates the weights for the exponential filter (black) and two alternative smoothing filters with comparable widths: the Gaussian (dark grey) and boxcar (light grey). All three of these smoothing filters can be implemented efficiently, with computational cost that is independent of their width.

A less efficient (non-recursive) but simpler implementation of the boxcar filter is often used, perhaps because it more obviously computes a moving average. But the abrupt transition from non-zero weight to zero weight makes no sense for such an average, and it is hard to beat the simplicity of our ten-line program.

To summarize, the exponential filter:

- Gives more weight to input samples located (in time or space) near the output sample than to input samples located farther away.
- Guarantees that all weights are non-negative, unlike many recursive implementations of Gaussian filters.
- Can be applied in-place, so that output values `y[i]` replace input values `x[i]` stored in the same array, which is especially useful when filtering large arrays of arrays that consume a lot of memory.
- Requires only six floating-point operations (multiplies and adds) per output sample `y[i]`, and this computational cost is independent of the extent of smoothing.
- Can be implemented with a simple ten-line computer program that includes careful treatment of the ends of input and output sequences.

Careful treatment of the ends is important. When averaging input values to compute output values near the ends, our ten-line program listed above implicitly assumes that input values beyond the ends are equal to the end values. This zero-slope assumption is often appropriate. But suppose that the data we are smoothing are known to have zero mean. In this case, the zero-value assumption may be more appropriate; surprisingly, the only change we require is in the initialization of `sx`, so that line 2 becomes `float sx = b, sy = a;`. This switches our treatment of the ends from zero-slope to zero-value.

This chapter is adapted from a blog post: https://ageo.co/hale-2012
