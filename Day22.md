## Day 22 of #dailycoding challenge ⬇️

Today we'll introduce to you #bioinformatics #Bioconductor, #Biostrings and #BSgenome.

The #Bioconductor project provides data packages that contain the full genome sequences of a given organism.

These packages are called Biostrings-based genome data packages because the sequences they contain are
stored in some of the basic containers defined in the #Biostrings package, like the #DNAString, the #DNAStringSet
or the #MaskedDNAString containers.

👉The BSgenome data package for the SARS-COV-2 genome is BSgenome.SARSCoV2.

👉genome$SARS_CoV2:gives some basic information about the origin of the genome (organism, provider,
provider version, etc...) followed by the index of single sequences.

👉countPattern(): counts the number of times the pattern appears in the genome.

👉matchPattern(): shows the start and end position of the match.

Happy Coding Learning !

``` r
library(BSgenome)
library(devtools)
install_github("HediaTnani/BSgenome.SARSCoV2")
library(BSgenome.SARSCoV2)
# creating a BSgenome object
genome <- BSgenome.SARSCoV2
genome
# checking the class of genome
class(genome)
seqnames(genome)
# displaying SARS-CoV2 sequence
genome$SARS_CoV2
# checking the length of the SARS-CoV2 genome
length(genome$SARS_CoV2)
# checking the frequency of each nucleotide
alphabetFrequency(genome$SARS_CoV2, baseOnly=TRUE)
# checking the frequency of "G" or "C" in the SARS-CoV2 genome
letterFrequency(genome$SARS_CoV2, "GC")
# finding an arbitrary nucleotide pattern in the SARS-CoV2 genome
p1 <-"TTAACAA"
countPattern(p1, genome$SARS_CoV2)
matchPattern(p1, genome$SARS_CoV2)
```
