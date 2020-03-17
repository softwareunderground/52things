# Speeding things up

Slow code is nothing to be ashamed of. If the program runs and
produces correct results, the important work is done. But when the
time does come to speed things up, it can be difficult to know where
to start. Don't panic and write a blog post about how slow
Python/R/Julia is, instead try to utilize some of these tools and
strategies.

## Measuring performance

To speed up slow code, the first step is to determine what is slowing
things down. For simple programs it may be easy to intuitively
identify bottlenecks. Trusting your gut ceases to be an appropriate
strategy as codebases grow in size and complexity.

Measurement tools such as *profilers* and *timers* are invaluable
allies when optimizing programs. Explicitly measuring the speed of
code execution can shine light on subtle bottlenecks and
inefficiencies which may not have been discovered otherwise.

### Timers

Timers measure the time it takes to execute an expression. Using a
timer helps to isolate and test the speed of a small snippet or
function. The code block below demonstrates using the IPython
`%timeit` magic command to compare two different ways to build a list
of squares in Python:

```python
In [1]: def comprehension(n):
   ...:     return [i**2 for i in range(n)]
   ...:

In [2]: def loop(n):
   ...:     x = []
   ...:     for i in range(n):
   ...:         x.append(i**2)
   ...:     return x
   ...:

In [3]: %timeit comprehension(1000)
190 µs ± 1.35 µs per loop (mean ± std. dev. of 7 runs, 10000 loops each)

In [4]: %timeit loop(1000)
226 µs ± 2.44 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
```

### Profilers

Profilers measure how often different parts of a program are called
and how long they take to execute. For example, consider the following
inefficient Python program:

```python
# fib_buzz.py

def fib(n):
    if n < 2:
        return n
    else:
        return fib(n - 1) + fib(n - 2)


def fib_buzz(n):
    for i in range(n):
        if fib(i) % 3 == 0 and fib(i) % 5 == 0:
            print("fibbuzz")

        elif fib(i) % 3 == 0:
            print("fib")

        elif fib(i) % 5 == 0:
            print("buzz")

        else:
            print(i)
```

Profiling `fib_buzz` with the IPython `%prun` magic command produces
the following table:

```python
In [1] %load fib_buzz.py

In [2] %prun -s calls -l 10 fib_buzz(30)

         13048500 function calls (722 primitive calls) in 2.959 seconds

   Ordered by: call count
   List reduced from 15 to 10 due to restriction <10>

   ncalls  tottime  percall  cumtime  percall filename:lineno(function)
13047866/88    2.948    0.000    2.948    0.034 <ipython-input-3-a0fe65949268>:2(fib)
      120    0.000    0.000    0.000    0.000 {method 'finditer' of 're.Pattern' objects}
       60    0.000    0.000    0.010    0.000 ansitowin32.py:40(write)
       60    0.000    0.000    0.010    0.000 ansitowin32.py:160(write)
       60    0.000    0.000    0.010    0.000 ansitowin32.py:177(write_and_convert)
       60    0.000    0.000    0.009    0.000 ansitowin32.py:193(write_plain_text)
       60    0.000    0.000    0.000    0.000 ansitowin32.py:245(convert_osc)
       60    0.004    0.000    0.004    0.000 {method 'write' of '_io.TextIOWrapper' objects}
       60    0.006    0.000    0.006    0.000 {method 'flush' of '_io.TextIOWrapper' objects}
       60    0.000    0.000    0.000    0.000 {built-in method builtins.len}
```

This output shows that `fib` function calls make up the majority of
the program runtime. Optimization efforts should be focused on the
`fib` function, either by reducing the number of times it is called or
by speeding up execution time per call.

## Tips for writing faster code

Writing fast code to solve problems in scientific computing is a lot
like writing fast code in any other domain. However, there are some
specific performance considerations to keep in mind, especially
regarding n-dimensional arrays. Below are a few tips for
writing faster scientific code:

### 1. Use vectorized operations

When working with data stored in arrays, vectorized functions are much
faster than using a loop to apply an operation element by
element. Vectorized functions operate on entire dimensions at once and
take advantage of low-level optimizations to perform calculations
fast.

For example, the snippet below shows that squaring a `numpy` array
using a vectorized function is >35 times faster than looping over the
array with `apply_along_axis`.

```python
In [1]: import numpy as np

In [2]: a = np.arange(1000)

In [3]: %timeit np.apply_along_axis(lambda x: x**2, 0, a)
62 µs ± 4.23 µs per loop (mean ± std. dev. of 7 runs, 10000 loops each)

In [4]: %timeit a ** 2
1.75 µs ± 38.3 ns per loop (mean ± std. dev. of 7 runs, 1000000 loops each)
```

### 2. Don't forget about I/O

Reading and writing data can be an easy bottleneck to overlook, I/O
handling often amounts to a few lines of code at the beginning and end
of a script. When working with a lot of data&mdash;whatever that means
to you&mdash;carefully consider how data is being stored and
accessed. Some tips:

- Only load necessary columns into memory and specify data types so
  the loader doesn't have to infer them.
- Loading data in chunks, processing the chunks, then aggregating is a
  powerful strategy for efficiently dealing with larger datasets.
- Delimited text files aren't always the right way to store
  data. Alternative options depending on how your data is structured
  could include `HDF`, `NetCDF`, `Parquet`, or a trusty relational
  database.

### 3. Be Lazy

As thrilling as it may be to write something from scratch, utilizing
the right library is a shortcut to writing fast code. Scientific
programming libraries are written with speed in mind and take liberal
advantage of low-level optimizations (the `numpy` package is about 50%
C code).

### 4. Think like a computer scientist

Micro-optimizations that speed up single expressions are often trumped
by picking a more efficient algorithm. Selecting the right data
structures and algorithm for the problem at hand is an essential skill
when writing efficient code.

Not everyone who writes code for scientific analysis needs a computer
science degree and an A+ in an algorithms class. Just like with cars
or bikes, a little bit of knowledge of the mechanics of what is going
on beneath the hood goes a long way.
