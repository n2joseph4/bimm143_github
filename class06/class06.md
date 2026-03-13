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

    [1] 9 5 7 3

> Q. Return 12 numbers picked randomly from the input 1:10

``` r
sample(1:10, size=12, replace=TRUE)
```

     [1] 10 10  3  9  9  9  9  8  8  9  8  4

> Q: Write the code to generate a random 12 nucleotide long DNA
> sequence?

``` r
bases <- c('A','C','G','T')
sample(bases, size=12, replace=TRUE)
```

     [1] "C" "A" "C" "A" "A" "C" "G" "G" "T" "G" "C" "G"

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

     [1] "C" "G" "A" "G" "C" "G" "T" "T" "T" "G"

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

    [1] "GTTAGGC"

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

    [1] "TCGGT"

``` r
generate_dna(5, fasta = FALSE)
```

    ... is it me you are looking for...

    [1] "C" "G" "C" "A" "T"

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

    [1] "SLVIVR"

``` r
generate_protein(7)
```

    [1] "PQDTAPE"

``` r
generate_protein(8)
```

    [1] "KWWEMIYC"

``` r
generate_protein(9)
```

    [1] "CQESPQPDI"

``` r
generate_protein(10)
```

    [1] "KSRPRAKWNG"

``` r
generate_protein(11)
```

    [1] "HALLGQIQCHS"

``` r
generate_protein(12)
```

    [1] "NGAHKEECPVNG"

Or we could do a `for()` loop:

``` r
for(i in 6:12){
  cat('>', i, "\n", sep='')
  cat(generate_protein(i), '\n')
}
```

    >6
    NCFAVD 
    >7
    RFESCML 
    >8
    VCPDIIQH 
    >9
    ADEHWYWEF 
    >10
    CQPLNFAPWN 
    >11
    MWAFELLSCRK 
    >12
    YKIVRRVWPTHV 

The protein sequences of 8-12 are unique in nature as they do not appear
in the NR database in NCBI.
