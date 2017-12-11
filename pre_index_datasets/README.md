# Overview

An automation that pre-indexes datasets whenever one of the following events happens:

1) A new version of the alignment tool is installed
2) A new version of the dataset is downloaded

## Alingment Tools
* Bwa  -- http://bio-bwa.sourceforge.net/bwa.shtml 
```
Usage: $path2/bwa  index <reference_fasta>

Notes:
This gives .pac, .bwt, .ann, .amb and .sa index files that all have the same reference_fasta basename. 
Tools recognize index files within the same directory by their identical basename.

See: http://www.htslib.org/workflow/#mapping_to_variant
     https://github.com/lh3/bwa#type
   
```
* Bowtie -- http://bowtie-bio.sourceforge.net/manual.shtml
```
Usage: $path2/bowtie-build  <reference_fasta> <index_prefix>
See: http://bowtie-bio.sourceforge.net/tutorial.shtml#newi

```
* Bowtie2 -- http://bowtie-bio.sourceforge.net/bowtie2/manual.shtml
```
Usage: $path2/bowtie2-build [options]* <reference_in> <bt2_base>
Where:
<reference_in>
A comma-separated list of FASTA files containing the reference sequences to be aligned to,
or, if -c is specified, the sequences themselves. E.g., <reference_in> might be chr1.fa,chr2.fa,
chrX.fa,chrY.fa, or, if -c is specified, this might be GGTCATCCT,ACGGGTCGT,CCGTTCTATGCGGCTTA.

<bt2_base>
The basename of the index files to write. By default, bowtie2-build writes files named NAME.1.bt2,
NAME.2.bt2, NAME.3.bt2, NAME.4.bt2, NAME.rev.1.bt2, and NAME.rev.2.bt2, where NAME is <bt2_base>.

See: http://bowtie-bio.sourceforge.net/bowtie2/manual.shtml#the-bowtie2-build-indexer
```

* Hisat2  -- http://ccb.jhu.edu/software/hisat2/manual.shtml#the-hisat2-build-indexer
```
Usage: $path2/hisat2-build [options]* <reference_in> <ht2_base>

Notes:
If you use --snp, --ss, and/or --exon, hisat2-build will need about 200GB RAM for the human genome size 
as index building involves a graph construction.  Otherwise, you will be able to build an index 
on your desktop with 8GB RAM.

Main arguments:

<reference_in>
A comma-separated list of FASTA files containing the reference sequences to be aligned to, or, 
if -c is specified, the sequences themselves. E.g., <reference_in> might be chr1.fa,chr2.fa,chrX.fa,
chrY.fa, or, if -c is specified, this might be GGTCATCCT,ACGGGTCGT,CCGTTCTATGCGGCTTA.

<ht2_base>
The basename of the index files to write. By default, hisat2-build writes files named NAME.1.ht2, 
NAME.2.ht2, NAME.3.ht2, NAME.4.ht2, NAME.5.ht2, NAME.6.ht2, NAME.7.ht2, and NAME.8.ht2 where NAME is <ht2_base>.
```
* kallisto
* Salmon
* Star

## Datasets
### Genomes
### Transcriptomes
