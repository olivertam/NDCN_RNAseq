# NDCN_RNAseq
NDCN RNAseq compbio office hour

## Performing QC of your raw data

When you get your high-throughput sequencing data from the sequencing
facility, it usualy comes in the [FASTQ
format](https://en.wikipedia.org/wiki/FASTQ_format). This is a file
that has four lines for each sequence:

1. A line that starts with the `@` symbol that is followed by a
   sequence identifier.
2. The sequence (typically A, C, T, G or N).
3. A line that starts with the `+` symbol, and can sometimes have the
   sequence identifier from line 1.
4. The quality values for the sequence in line 2.

You can also obtain FASTQ files from [Gene Expression
Omnibus](https://www.ncbi.nlm.nih.gov/geo/) and [Short Read
Archive](https://www.ncbi.nlm.nih.gov/sra), where many people have
deposited published datasets, or from public consortia such as
[ENCODE](https://www.encodeproject.org/)

Whether you are generating your own sequences, or downloading them
from a resource or collaborator, it is always a good idea to do some
quick checks on the FASTQ files to see if there are any issues that
might cause issues with analyses downstream. Here, we use
[FastQC](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/)
to run some basic diagnostics on some FASTQ files

### FastQC

From [FastQC
website](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/):
"FastQC aims to provide a simple way to do some quality control checks
on raw sequence data coming from high throughput sequencing
pipelines. It provides a modular set of analyses which you can use to
give a quick impression of whether your data has any problems of which
you should be aware before doing any further analysis. "

## Performing QC of your processed data

Unless you are processing the raw data yourself, most of the time you
would receive the processed data from your bioinformatician/
computational analyst. For RNA-seq, this is typically a table of gene
expression counts for each of the libraries that you sequenced.

It is always a good idea to take a look at that processed data
yourself, and see if there are things in the data that are out of the ordinary,
and might cause problem further downstream.

### Sample correlation & principal component analysis (PCA)

It is always recommended to have replicates for RNAseq experiments,
since it allows differential analysis programs to model the intrinsic biological
variations of your samples and only extract differences that are
related to the question that you're trying to answer.

However, "variation" in your samples can also come from
"technical" sources that are not part of the biological question
(e.g. culture conditions/reagents, transfection efficiency, library
prep). One way to see its impact is to have biological replicates, and
look for similarities of experimental conditions between the
replicates. Sample correlation is a simple but useful way to quickly
assess this.

Another approach to look at variation in your dataset is
to perform a principal component analysis (PCA). It tries to reduce
the number of variables in your dataset into a small set of features
(components) that could still describe the variation in the data. It
also enables visualization of the "spread" of samples based on various
principal components.

