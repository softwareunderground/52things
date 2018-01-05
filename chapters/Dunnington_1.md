
# R, RStudio, and the tidyverse for Geocomputing

> Dewey Dunnington

As a geoscientist who switched from mostly typing code in Python to mostly typing code in R three years ago, it seems to me that R, particularly when combined with RStudio and the `tidyverse`, is an underutilized resource in the geological community. I switched from Python to R because I needed to make a plot for my M.Sc. thesis that somebody had figured out in R already, but three years later I type more R code than anything else. Here are a few reasons why:

1. **RStudio is the best development environment I have ever used.** I have tried many IDEs for Python, R, and other languages, but none of them seem to be as simple and elegant as RStudio. Jupyter, Rodeo, PyCharm and Spyder all do *some* of the things that I need to do (data analysis, generating documents/figures, and building software tools), but RStudio does *all* of the things that I need to do, provided that I'm writing mostly R code. Development environments are certainly a matter of preference, and RStudio is definitely centered around R, but if RStudio existed for Python three years ago, there is a good chance I never would have switched.

2. **R was built for data.** Independent of RStudio and the `tidyverse`, R was built to natively handle categorical variables and missing values for all data types. While it is possible to use `pandas` to do some of this in Python, I am constantly annoyed when I have to work in Python with data that contains incomplete observations or categorical variables that have a natural order. 

3. **R has the `tidyverse`.** The `tidyverse` is a collection of packages for R that ameliorate the sometimes haphazard and inconsistent nature of many base R functions. The `tidyverse` provides tools for data wrangling (`dplyr`, `tidyr`, and `readr`, which are like `pandas` in Python), tools for data communication (`ggplot2` and `RMarkdown`, which are like `matplotlib` and the export feature of Jupyter Notebooks, respectively), and tools for building other R packages (`devtools`). The `tidyverse` is maintained by the same people who maintain RStudio, and combined, they make R an end-to-end solution for data analysis. I now write articles and reports using `RMarkdown`, which embeds R code within documents, create figures using `ggplot2`, and do data wrangling with `dplyr` and `tidyr`. Parts of this I can do using Jupyter Notebooks, `pandas`, and `matplotlib`, but the completeness of the `tidyverse` is impressive: I can add a few line breaks to the word processor output of `RMarkdown`, and the article is ready for submission.

4. **R, RStudio, and the `tidyverse` have excellent teaching resources.** There are without a doubt excellent teaching resources for many programming languages, but I have found that the creators of RStudio and the `tidyverse` have embraced the philosophy of do-first, learn-the-details afterward, and the teaching resources they provide are mostly free. There are debates within the R community as to whether or not one should teach the details first, but I have found that teaching using *R for Data Science* (Grolemund and Wickham 2017) particularly effective for newcomers and experienced programmers alike.

After three years of writing code in R, I still prefer writing code in Python, however, the ability of R, RStudio, and the `tidyverse` to support the vast majority of my academic workflow means that I will likely continue to use R as my language of choice for a long time to come. For geoscientists who are curious, I would argue that at the very least, learning R, RStudio and the `tidyverse` is a worthwhile investment of time.

### References

Grolemund, G, and H Wickham (2017). *R for Data Science: Visualize, Model, Transform, Tidy, and Import Data*. O'Reilly. http://r4ds.had.co.nz/.
