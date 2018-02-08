# Bwa Indexer

A reusable module that uses bwa index program to pre-index the reference before running a given data pipeline.
Each run generates a unique log file that contains useful information about the dataset and the alignment tool
used to generate the indexes.

The module was created to run either as a standalone application or to be called by index trigger applications. 


A set of scripts and config files to create indexes in Bwa

To prepare the reference for mapping you must first index it by typing the following command
```
  bwa index <ref.fa>
```
Where <ref.fa> is the absolute path to your reference file.
This gives .pac, .bwt, .ann, .amb and .sa index files that all have the same ref.fa basename. 
Tools recognize index files within the same directory by their identical basename. In the case of BWA, 
it uses the basename preceding the .
fasta suffix and searches for the index file, e.g. with .bwt suffix or .64.bwt suffix. Depending on which of
the two choices it finds, it looks for the same suffix for the other index files, e.g. .alt or .64.alt. 
Lack of a matching .alt index file will cause BWA to map reads without alt-handling.


Bwa maps the reads to the reference genome unsing one of the following three algorithms: 
1) BWA-backtrack, 
2) BWA-SW and 
3) BWA-MEM. 

For reads from 70bp up to a few megabases it is recommend using BWA MEM to map the data to a given reference genome
