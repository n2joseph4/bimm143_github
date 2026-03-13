# class06
Nathan Joseph A17668656

- [Background](#background)
- [A first function](#a-first-function)
- [A second function](#a-second-function)
- [A new cool function](#a-new-cool-function)

## Background

Functions are at the heart of using R. Everything we do involves calling
and using functions (from data input, analysis to results output).

All functions in R have at least 3 things:

1.  A **name** the thing we use to call the function

2.  one or more input **arguments** that are comma separated

3.  the **body**, lines of code between curly brackets { } that does the
    work of the function.

## A first function

Let’s write a silly function to add some numbers to:

``` r
add <- function(x){
  x+1
}
```

Lets try it out

``` r
add(100)
```

    [1] 101

Will this work?

``` r
add(c(100,200,300))
```

    [1] 101 201 301

Modify this to be more useful and add more than just 1

``` r
add <- function(x, y=1){
  x+y
}
```

Will this work?

``` r
add(100)
```

    [1] 101

``` r
plot(1:10, col='blue', type='b')
```

![](class06_files/figure-commonmark/unnamed-chunk-6-1.png)

``` r
log(10, base=10)
```

    [1] 1

> **N.B.** Input arguments can either be **required** or an
> **optional**. The latter have a fall-back default that is specified in
> the function code with an equals sign.

``` r
# add(x=100, y=100, z=300)
```

## A second function

All functions in R look like this

    name <- function(arg){
    body
    }

The `sample()` function in R randomly selects items from a vector

``` r
sample(1:10, size=4)
```

    [1] 3 6 1 9

> Q. Return 12 numbers picked randomly from the input 1:10

``` r
sample(1:10, size=12, replace=TRUE)
```

     [1] 3 1 5 3 2 1 8 9 4 3 6 9

> Q: Write the code to generate a random 12 nucleotide long DNA
> sequence?

``` r
bases <- c('A','C','G','T')
sample(bases, size=12, replace=TRUE)
```

     [1] "C" "C" "C" "G" "A" "T" "C" "A" "A" "C" "C" "A"

> Q. Write a first version function called `generate_dna()` that
> generates a user specified length `n` random DNA sequence?

``` r
generate_dna <- function(n=4){
  bases <- c('A','C','G','T')
  sample(bases, size=n, replace=TRUE)
}
```

``` r
generate_dna(10)
```

     [1] "T" "G" "G" "C" "G" "T" "C" "T" "G" "T"

> Q. Modify your function to return a FASTA like sequence so rather than
> \[1\] “G” “A” “T” “G” “C” “C” we want “GATGCC”

``` r
generate_dna <- function(n=4){
  bases <- c('A','C','G','T')
  ans <- sample(bases, size=n, replace=TRUE)
  answer <- paste(ans, collapse = '')
  return(answer)
}
```

``` r
generate_dna(7)
```

    [1] "ATTGTCG"

> Q. Give the user an option to return FASTA format ouput sequence or
> standard multi-element vector format?

``` r
generate_dna <- function(n=4, fasta=TRUE){
  bases <- c('A','C','G','T')
  ans <- sample(bases, size=n, replace=TRUE)
  if(fasta) {
    ans <- paste(ans, collapse = '')
    cat("Hello...")
  }
  else {
    cat("... is it me you are looking for...")
  }
  return(ans)
}
```

``` r
generate_dna(5)
```

    Hello...

    [1] "AGATT"

``` r
generate_dna(5, fasta = FALSE)
```

    ... is it me you are looking for...

    [1] "T" "T" "T" "C" "C"

## A new cool function

> Q. Write a function called `generate_protein` that generates a user
> specified length protein sequence in FASTA like format

``` r
generate_protein <- function(n=4, fasta=TRUE){
  aa = c("A","R","N","D","C","Q","E","G","H",
         "I","L","K","M","F","P","S","T","W","Y","V")
  ans <- sample(aa, size=n, replace=TRUE)
  if(fasta) {
    return(paste(ans, collapse = ''))
  }
  return(ans)
}
```

> Q. Use your new `generate_protein` function to generate all sequences
> between length 6 and 12 amino-acids in length and check of any of
> these are unique in nature (i.e. found in the NR database at NCBI)?

``` r
generate_protein(6)
```

    [1] "EGHARY"

``` r
generate_protein(7)
```

    [1] "EVPNAVP"

``` r
generate_protein(8)
```

    [1] "YMAPDYRY"

``` r
generate_protein(9)
```

    [1] "DAGISKQMA"

``` r
generate_protein(10)
```

    [1] "DWAYLKRPHL"

``` r
generate_protein(11)
```

    [1] "RSATNHMDNMD"

``` r
generate_protein(12)
```

    [1] "APALHRHTAQIY"

Or we could do a `for()` loop:

``` r
for(i in 6:12){
  cat('>', i, "\n", sep='')
  cat(generate_protein(i), '\n')
}
```

    >6
    MVAISY 
    >7
    VSKILCE 
    >8
    CSNYGWLM 
    >9
    AVLMNHFDR 
    >10
    MWAWYGGFFE 
    >11
    CIAHHPVMAAW 
    >12
    HPWVSSQASNCS 

The protein sequences of 8-12 are unique in nature as they do not appear
in the NR database in NCBI.
