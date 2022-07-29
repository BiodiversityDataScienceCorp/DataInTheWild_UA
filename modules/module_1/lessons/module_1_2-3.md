Module 1: Introduction to Base R/RStudio
================
Keaton Wilson, Ellen Bledsoe
11/22/2019, revised July 2022

# Introduction to R/RStudio

## Learning Outcomes

-   Students will be able to successfully install and open RStudio.  
-   Students will be able to differentiate the function of RStudio
    versus R, and generally describe the advantages of using an IDE.  
-   Students will be able to describe the utility of each panel in
    RStudio.  
-   Students will understand what a working directory is and perform
    basic file system navigation using the files panel and
    auto-completion within RStudio.  
-   Students will be able to save a file to a specific place on their
    computers.
-   Students will be able to run code line-by-line and as code chunks
    from an Rmarkdown file.
-   Students will be able to comment their code effectively.

## Check-in (5 minutes)

-   Confirm access to RStudio on their machines or RStudio Cloud/the
    binder instance?
-   If there are a few that had problems or didn’t get to it, do it now…
    ask folks sitting next to you for help. For those who are good to
    go, poke around RStudio for a little bit and see what you can find!

Now is the time to form groups of \~3 people.

## What is an IDE? (10 minutes)

Get on the web. Look up the definition of an IDE, with focus on RStudio.
Think about the following questions with your group and be ready to
report out: \* What does IDE stand for? \* What are some advantages of
using an IDE? \* Why do you think we’re using an IDE over base R?

A few groups report out. (5 minutes)

## RStudio exploration (10 minutes)

Open up RStudio, either on your machine or over the web. Spend some time
familiarizing yourself with the structure of what is in front of you.
Individually, come up with a question or something you don’t really
understand about R/RStudio. Be ready to report out.

## Rstudio Mini-tour (10 minutes)

Link to Google Slides for R/RStudio:
<https://docs.google.com/presentation/d/1lmOLhi2mhIYukCXQ9kw35FnawlIuIPVd51V4aUCFxkU/edit?usp=sharing>

Perform a live-coding mini-tour of RStudio.  
1. What the different panels do  
2. Navigating file structures in the files pane  
3. What is a working directory?  
4. Console versus a script/Rmarkdown?  
5. Getting help!

# Introduction to Programming

## Learning Outcomes

1.  Students will be able to perform basic math functions in the R
    console.  
2.  Students will be able to write scripts that assign values to
    variables and use these variables to perform various operations.  
3.  Students will be able to use helpfiles to learn how to use
    functions.  
4.  Students will be able to recall and explain how functions operate,
    and the basic syntax around functions (arguments, autocompletion,
    parentheses).  
5.  Students will be able to differentiate different data classes in
    R.  
6.  Students will learn how to create their own data structures
    (vectors) and 2d data (dataframes).

## Revisiting the exercise at the end of last class.

Let’s revisit your assignment from the end of last class. Let’s have
someone from each group (1 at a time), come up and wrote what they came
up with.

What were some problems? What difficulties did folks face?

## Using R as a calculator - getting comfortable with the console

You can do basic math in the console (the bottom left part of the
screen). For example:

``` r
3+5
```

    ## [1] 8

``` r
45^7
```

    ## [1] 373669453125

``` r
890*4.76523
```

    ## [1] 4241.055

## Math - Group Challenge

Run the following equation in the console. You’ll need to be creative,
dig into the helpfiles and probably the web to figure out a few of the
more complicated operations. Be ready to share your code.

The log (base 10) of the square root of pi, raised to the power of 12.

``` r
log10(sqrt(pi))^12
```

    ## [1] 5.565293e-08

## Variables, assignments, vectors

Let’s begin by opening a new script - we’ve been working mainly in the
console, but it’s important to get familiar with both the console and a
script, and how to move back and forth between the two.

Demonstrate how to open a new script - highlight headings again. Remind
them that this is best-coding practices. Do it every time!

Assignments are really key to almost everything we do in R. This is how
we create permanence in R. Anything can be saved to an object, and we do
this with the assignment operator.

``` r
# R assignment things

## Assigning Objects
mass <- 47.5 # this is the mass in kg
age <- 122
mass <- mass * 2 # multiply
age <- age - 20 # subtract
mass_index <- mass/age # divide
mass_sq <- mass^2 # raise to an expotent

# This is simple and you'll rarely do it in real-world scenarios. We can also assign more complex lists of objects to a particular object. 

x <- c(1,2,3,4,5,6)
x
```

    ## [1] 1 2 3 4 5 6

``` r
# This is a vector. R is inherently a vectorized language... here is what i mean.  
x <- c(1,2,3,4,5,6)
y <- c(1,2,3,4,5,6)

# What is x + y going to look like?
x + y
```

    ## [1]  2  4  6  8 10 12

``` r
# R does everything in vectors
```

### Subsetting Vectors

Sometimes we want to pull out and work with specific values from a
vector. This is called subsetting (taking a smaller set of the original)

``` r
# Sub-setting vectors
# Use square brackets
x[2]
```

    ## [1] 2

``` r
x[2:4]
```

    ## [1] 2 3 4

## Functions

``` r
## Functions

# functions are always followed by parentheses
# anything you type into the parentheses are called arguments
weight_kg <- sqrt(10) # square root
round(weight_kg) # rounding
```

    ## [1] 3

``` r
round(weight_kg, digits = 2) # round to 2 digits past 0
```

    ## [1] 3.16

``` r
# to get more information about a function, use the help function
help(mean) # or type ?help
```

## 2-dimensional Data

Most of the data you will encounter is two-dimensional, i.e. it has
columns and rows (should be familiar for those of you who have worked
with Excel before). R is really great at working with these types of
data.

``` r
# Create a simple data frame
plants <- data.frame(height = c(55, 17, 42, 47, 68, 39),
                     nitrogen = c("Y", "N", "N", "Y", "Y", "N"))

plants
```

    ##   height nitrogen
    ## 1     55        Y
    ## 2     17        N
    ## 3     42        N
    ## 4     47        Y
    ## 5     68        Y
    ## 6     39        N

### Subsetting Data Frames

Because data frames are two-dimensional, we can subset data in different
ways. We can select specific columns, specific rows, or filter rows by
values.

``` r
# Sub-setting data frames
# 2-dimensional, so you need to specify row and then column
plants[4,1]
```

    ## [1] 47

``` r
plants[,2]
```

    ## [1] "Y" "N" "N" "Y" "Y" "N"

``` r
# We can also choose specific columns using `$`
plants$height
```

    ## [1] 55 17 42 47 68 39

### Discussion point

This is a simple data set, but let’s come up with some questions. Let’s
write them on the board.

Example: height of plants treated with nitrogen vs. those not treated.

``` r
# filter rows based on values in the nitrogen column
plants[plants$nitrogen == "Y", ]
```

    ##   height nitrogen
    ## 1     55        Y
    ## 4     47        Y
    ## 5     68        Y

``` r
mean(plants[plants$nitrogen == "Y", 1])
```

    ## [1] 56.66667

### Group Challenge (5 min)

Using help files on functions

As a group, find the standard deviation `sd()` of the height of plants
treated with nitrogen and those not treated with nitrogen. Which group
has the larger standard deviation? Come up with a definition of standard
deviation, use the help file to find out how the function works, and be
prepared to show the code you used.

## Data classes

There are a few main types in R, and they behave differently:  
1. Numerical  
2. Character  
3. Integer  
4. Logical  
5. Complex  
6. Factors (kind of)

## The big takeaways:

1.  You can use `class()` to determine the class (or some easier ways
    for big data frames that we’ll cover later in the course)  
2.  Columns that end up being character vectors can trip you up a lot  
3.  Vectors must be of all the same data type

``` r
# Comparison
1 + 1 + 1 + 1
"1" + "1" + "1" + "1"

vec <- (1, 1.000, "1", TRUE)
```

# Rmarkdown and Code Chunks (10 minutes)

Rmarkdown (.Rmd) is a file format that let’s us incorporate text and
code into one document seamlessly. In fact, it is the file format for
this document!

To open a new Rmarkdown file, go the File \> New File \> R Markdown.
Enter a title for the document (short but descriptive), your name, and
make sure the default output HTML is selected.

When the Rmd file opens, you’ll see that there is already stuff in it!
The file will have a header with the information you entered, some code
chunks, and some text explaining how Rmd files work. \* For writing
text, you can type as you would normally \* Code chunks are a bit
different. To include text in them, you will need to put a \# in front.
R will not read anything after the \# as code. Chunks look like this:

Type your R code in between the lines with the \`\`\`. A quick shortcut
for adding a code chunk is Ctrl + Atl + i (Cmd + Opt + i on a Mac).
Alternatively, you can go to Code \> Insert Chunk.

To run a chunk of code, click the green arrow on the far right side of
the chunk.

Let’s work with an example code chunk:

``` r
# My first code chunk!
# Ellen Bledsoe
# Aug 2022

# Examining a pre-built data set in R
Orange
```

    ##    Tree  age circumference
    ## 1     1  118            30
    ## 2     1  484            58
    ## 3     1  664            87
    ## 4     1 1004           115
    ## 5     1 1231           120
    ## 6     1 1372           142
    ## 7     1 1582           145
    ## 8     2  118            33
    ## 9     2  484            69
    ## 10    2  664           111
    ## 11    2 1004           156
    ## 12    2 1231           172
    ## 13    2 1372           203
    ## 14    2 1582           203
    ## 15    3  118            30
    ## 16    3  484            51
    ## 17    3  664            75
    ## 18    3 1004           108
    ## 19    3 1231           115
    ## 20    3 1372           139
    ## 21    3 1582           140
    ## 22    4  118            32
    ## 23    4  484            62
    ## 24    4  664           112
    ## 25    4 1004           167
    ## 26    4 1231           179
    ## 27    4 1372           209
    ## 28    4 1582           214
    ## 29    5  118            30
    ## 30    5  484            49
    ## 31    5  664            81
    ## 32    5 1004           125
    ## 33    5 1231           142
    ## 34    5 1372           174
    ## 35    5 1582           177

``` r
# printing maximum circumference of the biggest tree
max(Orange$circumference)
```

    ## [1] 214

### Group challenge (Until the end of class)

Construct a new Rmarkdown script (with all of the appropriate formatting
we discussed) that calculates the average (mean) circumference of trees
in the orange data set. Save the mean as an object called “avg_circ.”

Save the script and be ready to share it at the beginning of next class.