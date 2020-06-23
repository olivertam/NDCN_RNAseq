# NDCN_RNAseq
NDCN RNAseq compbio office hour

## Performing QC of your raw data

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

### Sample correlation

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
