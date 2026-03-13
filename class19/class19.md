# class19
Nathan Joseph (PID: A17668656)

# Cancer Mutation Analysis

## Q1

``` r
library(seqinr)
seq <- read.fasta("A17668656_mutant_seq.fa")
```

``` r
seq
```

    $wt_healthy
       [1] "m" "g" "a" "i" "g" "l" "l" "w" "l" "l" "p" "l" "l" "l" "s" "t" "a" "a"
      [19] "v" "g" "s" "g" "m" "g" "t" "g" "q" "r" "a" "g" "s" "p" "a" "a" "g" "p"
      [37] "p" "l" "q" "p" "r" "e" "p" "l" "s" "y" "s" "r" "l" "q" "r" "k" "s" "l"
      [55] "a" "v" "d" "f" "v" "v" "p" "s" "l" "f" "r" "v" "y" "a" "r" "d" "l" "l"
      [73] "l" "p" "p" "s" "s" "s" "e" "l" "k" "a" "g" "r" "p" "e" "a" "r" "g" "s"
      [91] "l" "a" "l" "d" "c" "a" "p" "l" "l" "r" "l" "l" "g" "p" "a" "p" "g" "v"
     [109] "s" "w" "t" "a" "g" "s" "p" "a" "p" "a" "e" "a" "r" "t" "l" "s" "r" "v"
     [127] "l" "k" "g" "g" "s" "v" "r" "k" "l" "r" "r" "a" "k" "q" "l" "v" "l" "e"
     [145] "l" "g" "e" "e" "a" "i" "l" "e" "g" "c" "v" "g" "p" "p" "g" "e" "a" "a"
     [163] "v" "g" "l" "l" "q" "f" "n" "l" "s" "e" "l" "f" "s" "w" "w" "i" "r" "q"
     [181] "g" "e" "g" "r" "l" "r" "i" "r" "l" "m" "p" "e" "k" "k" "a" "s" "e" "v"
     [199] "g" "r" "e" "g" "r" "l" "s" "a" "a" "i" "r" "a" "s" "q" "p" "r" "l" "l"
     [217] "f" "q" "i" "f" "g" "t" "g" "h" "s" "s" "l" "e" "s" "p" "t" "n" "m" "p"
     [235] "s" "p" "s" "p" "d" "y" "f" "t" "w" "n" "l" "t" "w" "i" "m" "k" "d" "s"
     [253] "f" "p" "f" "l" "s" "h" "r" "s" "r" "y" "g" "l" "e" "c" "s" "f" "d" "f"
     [271] "p" "c" "e" "l" "e" "y" "s" "p" "p" "l" "h" "d" "l" "r" "n" "q" "s" "w"
     [289] "s" "w" "r" "r" "i" "p" "s" "e" "e" "a" "s" "q" "m" "d" "l" "l" "d" "g"
     [307] "p" "g" "a" "e" "r" "s" "k" "e" "m" "p" "r" "g" "s" "f" "l" "l" "l" "n"
     [325] "t" "s" "a" "d" "s" "k" "h" "t" "i" "l" "s" "p" "w" "m" "r" "s" "s" "s"
     [343] "e" "h" "c" "t" "l" "a" "v" "s" "v" "h" "r" "h" "l" "q" "p" "s" "g" "r"
     [361] "y" "i" "a" "q" "l" "l" "p" "h" "n" "e" "a" "a" "r" "e" "i" "l" "l" "m"
     [379] "p" "t" "p" "g" "k" "h" "g" "w" "t" "v" "l" "q" "g" "r" "i" "g" "r" "p"
     [397] "d" "n" "p" "f" "r" "v" "a" "l" "e" "y" "i" "s" "s" "g" "n" "r" "s" "l"
     [415] "s" "a" "v" "d" "f" "f" "a" "l" "k" "n" "c" "s" "e" "g" "t" "s" "p" "g"
     [433] "s" "k" "m" "a" "l" "q" "s" "s" "f" "t" "c" "w" "n" "g" "t" "v" "l" "q"
     [451] "l" "g" "q" "a" "c" "d" "f" "h" "q" "d" "c" "a" "q" "g" "e" "d" "e" "s"
     [469] "q" "m" "c" "r" "k" "l" "p" "v" "g" "f" "y" "c" "n" "f" "e" "d" "g" "f"
     [487] "c" "g" "w" "t" "q" "g" "t" "l" "s" "p" "h" "t" "p" "q" "w" "q" "v" "r"
     [505] "t" "l" "k" "d" "a" "r" "f" "q" "d" "h" "q" "d" "h" "a" "l" "l" "l" "s"
     [523] "t" "t" "d" "v" "p" "a" "s" "e" "s" "a" "t" "v" "t" "s" "a" "t" "f" "p"
     [541] "a" "p" "i" "k" "s" "s" "p" "c" "e" "l" "r" "m" "s" "w" "l" "i" "r" "g"
     [559] "v" "l" "r" "g" "n" "v" "s" "l" "v" "l" "v" "e" "n" "k" "t" "g" "k" "e"
     [577] "q" "g" "r" "m" "v" "w" "h" "v" "a" "a" "y" "e" "g" "l" "s" "l" "w" "q"
     [595] "w" "m" "v" "l" "p" "l" "l" "d" "v" "s" "d" "r" "f" "w" "l" "q" "m" "v"
     [613] "a" "w" "w" "g" "q" "g" "s" "r" "a" "i" "v" "a" "f" "d" "n" "i" "s" "i"
     [631] "s" "l" "d" "c" "y" "l" "t" "i" "s" "g" "e" "d" "k" "i" "l" "q" "n" "t"
     [649] "a" "p" "k" "s" "r" "n" "l" "f" "e" "r" "n" "p" "n" "k" "e" "l" "k" "p"
     [667] "g" "e" "n" "s" "p" "r" "q" "t" "p" "i" "f" "d" "p" "t" "v" "h" "w" "l"
     [685] "f" "t" "t" "c" "g" "a" "s" "g" "p" "h" "g" "p" "t" "q" "a" "q" "c" "n"
     [703] "n" "a" "y" "q" "n" "s" "n" "l" "s" "v" "e" "v" "g" "s" "e" "g" "p" "l"
     [721] "k" "g" "i" "q" "i" "w" "k" "v" "p" "a" "t" "d" "t" "y" "s" "i" "s" "g"
     [739] "y" "g" "a" "a" "g" "g" "k" "g" "g" "k" "n" "t" "m" "m" "r" "s" "h" "g"
     [757] "v" "s" "v" "l" "g" "i" "f" "n" "l" "e" "k" "d" "d" "m" "l" "y" "i" "l"
     [775] "v" "g" "q" "q" "g" "e" "d" "a" "c" "p" "s" "t" "n" "q" "l" "i" "q" "k"
     [793] "v" "c" "i" "g" "e" "n" "n" "v" "i" "e" "e" "e" "i" "r" "v" "n" "r" "s"
     [811] "v" "h" "e" "w" "a" "g" "g" "g" "g" "g" "g" "g" "g" "a" "t" "y" "v" "f"
     [829] "k" "m" "k" "d" "g" "v" "p" "v" "p" "l" "i" "i" "a" "a" "g" "g" "g" "g"
     [847] "r" "a" "y" "g" "a" "k" "t" "d" "t" "f" "h" "p" "e" "r" "l" "e" "n" "n"
     [865] "s" "s" "v" "l" "g" "l" "n" "g" "n" "s" "g" "a" "a" "g" "g" "g" "g" "g"
     [883] "w" "n" "d" "n" "t" "s" "l" "l" "w" "a" "g" "k" "s" "l" "q" "e" "g" "a"
     [901] "t" "g" "g" "h" "s" "c" "p" "q" "a" "m" "k" "k" "w" "g" "w" "e" "t" "r"
     [919] "g" "g" "f" "g" "g" "g" "g" "g" "g" "c" "s" "s" "g" "g" "g" "g" "g" "g"
     [937] "y" "i" "g" "g" "n" "a" "a" "s" "n" "n" "d" "p" "e" "m" "d" "g" "e" "d"
     [955] "g" "v" "s" "f" "i" "s" "p" "l" "g" "i" "l" "y" "t" "p" "a" "l" "k" "v"
     [973] "m" "e" "g" "h" "g" "e" "v" "n" "i" "k" "h" "y" "l" "n" "c" "s" "h" "c"
     [991] "e" "v" "d" "e" "c" "h" "m" "d" "p" "e" "s" "h" "k" "v" "i" "c" "f" "c"
    [1009] "d" "h" "g" "t" "v" "l" "a" "e" "d" "g" "v" "s" "c" "i" "v" "s" "p" "t"
    [1027] "p" "e" "p" "h" "l" "p" "l" "s" "l" "i" "l" "s" "v" "v" "t" "s" "a" "l"
    [1045] "v" "a" "a" "l" "v" "l" "a" "f" "s" "g" "i" "m" "i" "v" "y" "r" "r" "k"
    [1063] "h" "q" "e" "l" "q" "a" "m" "q" "m" "e" "l" "q" "s" "p" "e" "y" "k" "l"
    [1081] "s" "k" "l" "r" "t" "s" "t" "i" "m" "t" "d" "y" "n" "p" "n" "y" "c" "f"
    [1099] "a" "g" "k" "t" "s" "s" "i" "s" "d" "l" "k" "e" "v" "p" "r" "k" "n" "i"
    [1117] "t" "l" "i" "r" "g" "l" "g" "h" "g" "a" "f" "g" "e" "v" "y" "e" "g" "q"
    [1135] "v" "s" "g" "m" "p" "n" "d" "p" "s" "p" "l" "q" "v" "a" "v" "k" "t" "l"
    [1153] "p" "e" "v" "c" "s" "e" "q" "d" "e" "l" "d" "f" "l" "m" "e" "a" "l" "i"
    [1171] "i" "s" "k" "f" "n" "h" "q" "n" "i" "v" "r" "c" "i" "g" "v" "s" "l" "q"
    [1189] "s" "l" "p" "r" "f" "i" "l" "l" "e" "l" "m" "a" "g" "g" "d" "l" "k" "s"
    [1207] "f" "l" "r" "e" "t" "r" "p" "r" "p" "s" "q" "p" "s" "s" "l" "a" "m" "l"
    [1225] "d" "l" "l" "h" "v" "a" "r" "d" "i" "a" "c" "g" "c" "q" "y" "l" "e" "e"
    [1243] "n" "h" "f" "i" "h" "r" "d" "i" "a" "a" "r" "n" "c" "l" "l" "t" "c" "p"
    [1261] "g" "p" "g" "r" "v" "a" "k" "i" "g" "d" "f" "g" "m" "a" "r" "d" "i" "y"
    [1279] "r" "a" "s" "y" "y" "r" "k" "g" "g" "c" "a" "m" "l" "p" "v" "k" "w" "m"
    [1297] "p" "p" "e" "a" "f" "m" "e" "g" "i" "f" "t" "s" "k" "t" "d" "t" "w" "s"
    [1315] "f" "g" "v" "l" "l" "w" "e" "i" "f" "s" "l" "g" "y" "m" "p" "y" "p" "s"
    [1333] "k" "s" "n" "q" "e" "v" "l" "e" "f" "v" "t" "s" "g" "g" "r" "m" "d" "p"
    [1351] "p" "k" "n" "c" "p" "g" "p" "v" "y" "r" "i" "m" "t" "q" "c" "w" "q" "h"
    [1369] "q" "p" "e" "d" "r" "p" "n" "f" "a" "i" "i" "l" "e" "r" "i" "e" "y" "c"
    [1387] "t" "q" "d" "p" "d" "v" "i" "n" "t" "a" "l" "p" "i" "e" "y" "g" "p" "l"
    [1405] "v" "e" "e" "e" "e" "k" "v" "p" "v" "r" "p" "k" "d" "p" "e" "g" "v" "p"
    [1423] "p" "l" "l" "v" "s" "q" "q" "a" "k" "r" "e" "e" "e" "r" "s" "p" "a" "a"
    [1441] "p" "p" "p" "l" "p" "t" "t" "s" "s" "g" "k" "a" "a" "k" "k" "p" "t" "a"
    [1459] "a" "e" "i" "s" "v" "r" "v" "p" "r" "g" "p" "a" "v" "e" "g" "g" "h" "v"
    [1477] "n" "m" "a" "f" "s" "q" "s" "n" "p" "p" "s" "e" "l" "h" "k" "v" "h" "g"
    [1495] "s" "r" "n" "k" "p" "t" "s" "l" "w" "n" "p" "t" "y" "g" "s" "w" "f" "t"
    [1513] "e" "k" "p" "t" "k" "k" "n" "n" "p" "i" "a" "k" "k" "e" "p" "h" "d" "r"
    [1531] "g" "n" "l" "g" "l" "e" "g" "s" "c" "t" "v" "p" "p" "n" "v" "a" "t" "g"
    [1549] "r" "l" "p" "g" "a" "s" "l" "l" "l" "e" "p" "s" "s" "l" "t" "a" "n" "m"
    [1567] "k" "e" "v" "p" "l" "f" "r" "l" "r" "h" "f" "p" "c" "g" "n" "v" "n" "y"
    [1585] "g" "y" "q" "q" "q" "g" "l" "p" "l" "e" "a" "a" "t" "a" "p" "g" "a" "g"
    [1603] "h" "y" "e" "d" "t" "i" "l" "k" "s" "k" "n" "s" "m" "n" "q" "p" "g" "p"
    attr(,"name")
    [1] "wt_healthy"
    attr(,"Annot")
    [1] ">wt_healthy"
    attr(,"class")
    [1] "SeqFastadna"

    $mutant_tumor
       [1] "m" "g" "a" "i" "g" "l" "l" "w" "l" "l" "p" "l" "l" "l" "s" "t" "a" "a"
      [19] "v" "g" "s" "g" "m" "g" "t" "g" "q" "r" "a" "g" "s" "p" "a" "a" "g" "p"
      [37] "p" "l" "q" "p" "r" "e" "p" "l" "s" "y" "s" "r" "l" "q" "r" "k" "s" "l"
      [55] "a" "v" "d" "f" "v" "v" "p" "s" "l" "f" "r" "v" "y" "a" "r" "d" "l" "l"
      [73] "l" "p" "p" "s" "s" "s" "e" "l" "k" "a" "g" "r" "p" "e" "a" "r" "g" "s"
      [91] "l" "a" "l" "d" "c" "a" "p" "l" "l" "r" "l" "l" "g" "p" "a" "p" "g" "v"
     [109] "s" "w" "t" "a" "g" "s" "p" "a" "p" "a" "e" "a" "r" "t" "l" "s" "r" "v"
     [127] "l" "k" "g" "g" "s" "v" "r" "k" "l" "r" "r" "a" "k" "q" "l" "v" "l" "e"
     [145] "l" "g" "e" "e" "a" "i" "l" "e" "g" "c" "v" "g" "p" "p" "g" "e" "a" "a"
     [163] "v" "g" "l" "l" "q" "f" "n" "l" "s" "e" "l" "f" "s" "w" "w" "i" "r" "q"
     [181] "g" "e" "g" "r" "l" "r" "i" "r" "l" "m" "p" "e" "k" "k" "a" "s" "e" "v"
     [199] "g" "r" "e" "g" "r" "l" "s" "a" "a" "i" "r" "a" "s" "q" "p" "r" "l" "l"
     [217] "f" "q" "i" "f" "g" "t" "g" "h" "s" "s" "l" "e" "s" "p" "t" "n" "m" "p"
     [235] "s" "p" "s" "p" "d" "y" "f" "t" "w" "n" "l" "t" "w" "i" "m" "k" "d" "s"
     [253] "f" "p" "f" "l" "s" "h" "r" "s" "r" "y" "g" "l" "e" "c" "s" "f" "d" "f"
     [271] "p" "c" "e" "l" "e" "y" "s" "p" "p" "l" "h" "d" "l" "r" "n" "q" "s" "w"
     [289] "s" "w" "r" "r" "i" "p" "s" "e" "e" "a" "s" "q" "m" "d" "l" "l" "d" "g"
     [307] "p" "g" "a" "e" "r" "s" "k" "e" "m" "p" "r" "g" "s" "f" "l" "l" "l" "n"
     [325] "t" "s" "a" "d" "s" "k" "h" "t" "i" "l" "s" "p" "w" "m" "r" "s" "s" "s"
     [343] "e" "h" "c" "t" "l" "a" "v" "s" "v" "h" "r" "h" "l" "q" "p" "s" "g" "r"
     [361] "y" "i" "a" "q" "l" "l" "p" "h" "n" "e" "a" "a" "r" "e" "i" "l" "l" "m"
     [379] "p" "t" "p" "g" "k" "h" "g" "w" "t" "v" "l" "q" "g" "r" "i" "g" "r" "p"
     [397] "d" "n" "p" "f" "r" "v" "a" "l" "e" "y" "i" "s" "s" "g" "n" "r" "s" "l"
     [415] "s" "a" "v" "d" "f" "f" "a" "l" "k" "n" "c" "s" "e" "g" "t" "s" "p" "g"
     [433] "s" "k" "m" "a" "l" "q" "s" "s" "f" "t" "c" "w" "n" "g" "t" "v" "l" "q"
     [451] "l" "g" "q" "a" "c" "d" "f" "h" "q" "d" "c" "a" "q" "g" "e" "d" "e" "s"
     [469] "q" "m" "c" "r" "k" "l" "p" "v" "g" "f" "y" "c" "n" "f" "e" "d" "g" "f"
     [487] "c" "g" "w" "t" "q" "g" "t" "l" "s" "p" "h" "t" "p" "q" "w" "q" "v" "r"
     [505] "t" "l" "k" "d" "a" "r" "f" "q" "d" "h" "q" "d" "h" "a" "l" "l" "l" "s"
     [523] "t" "t" "d" "v" "p" "a" "s" "e" "s" "a" "t" "v" "t" "s" "a" "t" "f" "p"
     [541] "a" "p" "i" "k" "s" "s" "p" "c" "e" "l" "r" "m" "s" "w" "l" "i" "r" "g"
     [559] "v" "l" "r" "g" "n" "v" "s" "l" "v" "l" "v" "e" "n" "k" "t" "g" "k" "e"
     [577] "q" "g" "r" "m" "v" "w" "h" "v" "a" "a" "y" "e" "g" "l" "s" "l" "w" "q"
     [595] "w" "m" "v" "l" "p" "l" "l" "d" "v" "s" "d" "r" "f" "w" "l" "q" "m" "v"
     [613] "a" "w" "w" "g" "q" "g" "s" "r" "a" "i" "v" "a" "f" "d" "n" "i" "s" "i"
     [631] "s" "l" "d" "c" "y" "l" "t" "i" "s" "g" "e" "d" "k" "i" "l" "q" "n" "t"
     [649] "a" "p" "k" "s" "r" "n" "l" "f" "e" "r" "n" "p" "n" "k" "e" "l" "k" "p"
     [667] "g" "e" "n" "s" "p" "r" "q" "t" "p" "i" "f" "d" "p" "t" "v" "h" "w" "l"
     [685] "f" "t" "t" "c" "g" "a" "s" "g" "p" "h" "g" "p" "t" "q" "a" "q" "c" "n"
     [703] "n" "a" "y" "q" "n" "s" "n" "l" "s" "v" "e" "v" "g" "s" "e" "g" "p" "l"
     [721] "k" "g" "i" "q" "i" "w" "k" "v" "p" "a" "t" "d" "t" "y" "s" "i" "s" "g"
     [739] "y" "g" "a" "a" "g" "g" "k" "g" "g" "k" "n" "t" "m" "m" "r" "s" "h" "g"
     [757] "v" "s" "v" "l" "g" "i" "f" "n" "l" "e" "k" "d" "d" "m" "l" "y" "i" "l"
     [775] "v" "g" "q" "q" "g" "e" "d" "a" "c" "p" "s" "t" "n" "q" "l" "i" "q" "k"
     [793] "v" "c" "i" "g" "e" "n" "n" "v" "i" "e" "e" "e" "i" "r" "v" "n" "r" "s"
     [811] "v" "h" "e" "w" "a" "g" "g" "g" "g" "g" "g" "g" "g" "a" "t" "y" "v" "f"
     [829] "k" "m" "k" "d" "g" "v" "p" "v" "p" "l" "i" "i" "a" "a" "g" "g" "g" "g"
     [847] "r" "a" "y" "g" "a" "k" "t" "d" "t" "f" "h" "p" "e" "r" "l" "e" "n" "n"
     [865] "s" "s" "v" "l" "g" "l" "n" "g" "n" "s" "g" "a" "a" "g" "g" "g" "g" "g"
     [883] "w" "n" "d" "n" "t" "s" "l" "l" "w" "a" "g" "k" "s" "l" "q" "e" "g" "a"
     [901] "t" "g" "g" "h" "s" "c" "p" "q" "a" "m" "k" "k" "w" "g" "w" "e" "t" "r"
     [919] "g" "g" "f" "g" "g" "g" "g" "g" "g" "c" "s" "s" "g" "g" "g" "g" "g" "g"
     [937] "y" "i" "g" "g" "n" "a" "a" "s" "n" "n" "d" "p" "e" "m" "d" "g" "e" "d"
     [955] "g" "v" "s" "f" "i" "s" "p" "l" "g" "i" "l" "y" "t" "p" "a" "l" "k" "v"
     [973] "m" "e" "g" "h" "g" "e" "v" "n" "i" "k" "h" "y" "l" "n" "c" "s" "h" "c"
     [991] "e" "v" "d" "e" "c" "h" "m" "d" "p" "e" "s" "h" "k" "v" "i" "c" "f" "c"
    [1009] "d" "h" "g" "t" "v" "l" "a" "e" "d" "g" "v" "s" "c" "i" "v" "s" "p" "t"
    [1027] "p" "e" "p" "h" "l" "p" "l" "s" "l" "i" "l" "s" "v" "v" "t" "s" "a" "l"
    [1045] "v" "a" "a" "l" "v" "l" "a" "f" "s" "g" "i" "m" "i" "v" "y" "r" "r" "k"
    [1063] "h" "q" "e" "l" "q" "a" "m" "q" "m" "e" "l" "q" "s" "p" "e" "y" "k" "l"
    [1081] "s" "k" "l" "r" "t" "s" "t" "i" "m" "t" "d" "y" "n" "p" "n" "y" "c" "f"
    [1099] "a" "g" "k" "t" "s" "s" "i" "s" "d" "l" "k" "e" "v" "p" "r" "k" "n" "i"
    [1117] "t" "l" "i" "r" "g" "l" "g" "h" "g" "a" "f" "g" "e" "v" "y" "e" "g" "q"
    [1135] "v" "s" "g" "m" "p" "n" "d" "p" "s" "p" "l" "q" "v" "a" "v" "k" "t" "l"
    [1153] "p" "e" "v" "c" "s" "e" "q" "d" "e" "l" "d" "f" "l" "m" "e" "a" "l" "i"
    [1171] "i" "s" "k" "f" "n" "h" "q" "n" "i" "v" "r" "c" "i" "g" "v" "s" "l" "q"
    [1189] "s" "l" "p" "r" "f" "i" "l" "l" "e" "l" "m" "a" "g" "g" "d" "l" "k" "s"
    [1207] "f" "l" "r" "e" "t" "r" "p" "r" "p" "s" "q" "p" "s" "s" "l" "a" "m" "l"
    [1225] "d" "l" "l" "h" "v" "a" "r" "d" "i" "a" "c" "g" "c" "q" "y" "l" "e" "e"
    [1243] "n" "h" "f" "i" "h" "r" "d" "i" "a" "a" "r" "n" "c" "l" "l" "t" "c" "p"
    [1261] "g" "p" "g" "r" "v" "a" "k" "i" "g" "d" "f" "g" "m" "a" "r" "d" "i" "y"
    [1279] "r" "a" "s" "y" "y" "r" "k" "g" "g" "c" "a" "m" "l" "p" "v" "k" "w" "m"
    [1297] "p" "p" "e" "a" "f" "m" "e" "g" "i" "f" "t" "s" "k" "t" "d" "t" "w" "s"
    [1315] "f" "g" "v" "l" "l" "w" "e" "i" "f" "r" "l" "g" "y" "m" "p" "y" "p" "s"
    [1333] "k" "s" "n" "q" "e" "v" "l" "e" "f" "v" "t" "s" "g" "g" "r" "m" "d" "p"
    [1351] "p" "k" "n" "c" "p" "g" "p" "v" "y" "r" "i" "m" "t" "q" "c" "w" "q" "h"
    [1369] "q" "p" "e" "d" "r" "p" "n" "f" "a" "i" "i" "l" "e" "r" "i" "e" "y" "c"
    [1387] "t" "q" "d" "p" "d" "v" "i" "n" "t" "a" "l" "p" "i" "e" "y" "g" "p" "l"
    [1405] "v" "e" "e" "e" "e" "k" "v" "p" "v" "r" "p" "k" "d" "p" "e" "g" "v" "p"
    [1423] "p" "l" "l" "v" "s" "q" "q" "a" "k" "r" "e" "e" "e" "r" "s" "p" "a" "a"
    [1441] "p" "p" "p" "l" "p" "t" "t" "s" "s" "g" "k" "a" "a" "k" "k" "p" "t" "a"
    [1459] "a" "e" "i" "s" "v" "r" "v" "p" "r" "g" "p" "a" "v" "e" "g" "g" "h" "v"
    [1477] "n" "m" "a" "f" "s" "q" "s" "n" "p" "p" "s" "e" "l" "h" "k" "v" "h" "g"
    [1495] "s" "r" "n" "k" "p" "t" "s" "l" "w" "n" "p" "t" "y" "g" "s" "w" "f" "t"
    [1513] "e" "k" "p" "t" "k" "k" "n" "n" "p" "i" "a" "k" "k" "e" "p" "h" "d" "r"
    [1531] "g" "n" "l" "g" "l" "e" "g" "s" "c" "t" "v" "p" "p" "n" "v" "a" "t" "g"
    [1549] "r" "l" "p" "g" "a" "s" "l" "l" "l" "e" "p" "s" "s" "l" "t" "a" "n" "m"
    [1567] "k" "e" "v" "p" "l" "f" "r" "l" "r" "h" "f" "p" "c" "g" "n" "v" "n" "y"
    [1585] "g" "y" "q" "q" "q" "g" "l" "p" "l" "e" "a" "a" "t" "a" "p" "g" "a" "g"
    [1603] "h" "y" "e" "d" "t" "i" "l" "k" "s" "k" "n" "s" "m" "n" "q" "p" "g" "p"
    attr(,"name")
    [1] "mutant_tumor"
    attr(,"Annot")
    [1] ">mutant_tumor"
    attr(,"class")
    [1] "SeqFastadna"

``` r
#pos <- which(conserv(seq) != 1)
#pos
```

``` r
#seq$ali[, pos]
```

``` r
#print("S1324R")
```

``` r
#seq$ali
```

``` r
#mut_protein_seq <- paste(seq$ali["mutant_tumor", ], collapse = "")

#mut_protein_seq
```

``` r
#wt_protein_seq <- paste(seq$ali["wt_healthy", ], collapse = "")

#wt_protein_seq
```
