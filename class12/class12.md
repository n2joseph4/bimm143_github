# class 12
Nathan Joseph (PID: A17668656)

- [Section 1. Porportion of G/G in a
  population](#section-1-porportion-of-gg-in-a-population)
- [Section 4: Population Scale
  Analysis](#section-4-population-scale-analysis)

## Section 1. Porportion of G/G in a population

Downloaded CSV file from Ensemble

``` r
mxl <- read.csv("373531-SampleGenotypes-Homo_sapiens_Variation_Sample_rs8067378.csv")
head(mxl)
```

      Sample..Male.Female.Unknown. Genotype..forward.strand. Population.s. Father
    1                  NA19648 (F)                       A|A ALL, AMR, MXL      -
    2                  NA19649 (M)                       G|G ALL, AMR, MXL      -
    3                  NA19651 (F)                       A|A ALL, AMR, MXL      -
    4                  NA19652 (M)                       G|G ALL, AMR, MXL      -
    5                  NA19654 (F)                       G|G ALL, AMR, MXL      -
    6                  NA19655 (M)                       A|G ALL, AMR, MXL      -
      Mother
    1      -
    2      -
    3      -
    4      -
    5      -
    6      -

``` r
table(mxl$Genotype..forward.strand.)
```


    A|A A|G G|A G|G 
     22  21  12   9 

``` r
table(mxl$Genotype..forward.strand.) / nrow(mxl) * 100
```


        A|A     A|G     G|A     G|G 
    34.3750 32.8125 18.7500 14.0625 

## Section 4: Population Scale Analysis

One sample is obviously not enough to know what is happening in a
population. You are interested in assessing genetic differences on a
population scale. So, you processed about ~230 samples and did the
normalization on a genome level. Now, you want to find whether there is
any association of the 4 asthma-associated SNPs (rs8067378…) on ORMDL3
expression.

> Q13: Read this file into R and determine the sample size for each
> genotype and their corresponding median expression levels for each of
> these genotypes

How many samples do we have?

``` r
expr <-read.table("rs8067378_ENSG00000172057.6.txt")
head(expr)
```

       sample geno      exp
    1 HG00367  A/G 28.96038
    2 NA20768  A/G 20.24449
    3 HG00361  A/A 31.32628
    4 HG00135  A/A 34.11169
    5 NA18870  G/G 18.25141
    6 NA11993  A/A 32.89721

``` r
nrow(expr)
```

    [1] 462

``` r
table(expr$geno)
```


    A/A A/G G/G 
    108 233 121 

``` r
print(paste("Median Expression for A/A", median(expr$exp[expr$geno == "A/A"])))
```

    [1] "Median Expression for A/A 31.248475"

``` r
print(paste("Median Expression for A/G", median(expr$exp[expr$geno == "A/G"])))
```

    [1] "Median Expression for A/G 25.06486"

``` r
print(paste("Median Expression for G/G", median(expr$exp[expr$geno == "G/G"])))
```

    [1] "Median Expression for G/G 20.07363"

> Q14: Generate a boxplot with a box per genotype, what could you infer
> from the relative expression value between A/A and G/G displayed in
> this plot? Does the SNP effect the expression of ORMDL3?

``` r
library(ggplot2)
```

Let’s make a boxplot:

``` r
ggplot(expr) + aes(x=geno,y=exp, fill=geno) + geom_boxplot(notch=TRUE)
```

![](class12_files/figure-commonmark/unnamed-chunk-9-1.png)

From the relative expression value between A/A and G/G displayed in this
plot I can infer that there is a lower gene expression level associated
with the G/G genotype when compared to the A/A genotype. Henceforth, the
SNP does affect the expression of ORMDL3.
