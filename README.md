# Data Processing Pipelines

```
 "Pipelines are composed of discrete steps that can represent an algorithm, 
 a software tool, or a file format manipulation. These steps are applied to the primary data
 (generated from an experimental assay) to produce visualizable data" ~ENCODE
 ```
 Pipeline-prep project creates a set of scripts used to execute the first two steps of data pipeline.
 These steps include  Pre-Indexing reference genome/transcripome and Pre-processing the reads.
 
 
  ## Pipeline Steps
  
 * Pre-Indexing reference genome/transcripome
 * Pre-processing the reads
 * Mapping reads to ref genome/transcriptome indexes
 * Features quantification
 * Features assembly
 * Features differenciation
 * Stats generation
 * Visualization
 
 ## Versioning Pipelines
 
 We run a given pipeline whenever one of the following conditions is met:
 
 * New release detected from input dataset source
 * New version detected for any alignment tool that is part of the pipeline 
 * New version detected for any file processing tool that is part of the pipeline
 * New version detected for any statistical analysis tool that is part of the pipeline
 
 Each run represents a version of a given pipeline. Some runs will require indexes be re-generated
 and some not. For example - new release of the reference dataset, or new release of the alignment tool
 both require re-indexing. But a new release of tools/datasets involved in post-indexing steps of a specific
 pipeline might not require re-indexing the reference dataset.
 
 
 
 ## Pipeline Tools
 ### Alingment tools - Short reads:
 * Bwa.    -- http://bio-bwa.sourceforge.net/bwa.shtml
 * Hisat2  -- http://ccb.jhu.edu/software/hisat2/manual.shtml#the-hisat2-build-indexer
 
 ### Alingment tools - Long reads:
 *	Bowtie2.  -- http://bowtie-bio.sourceforge.net/bowtie2/manual.shtml#getting-started-with-bowtie-2-lambda-phage-example
 *	Bwa(BWA-SW and BWA-MEM)
 *	Hisat2 (a replacement of Tophat)
 * Kalisto
 * Salmon

 ### File Processing:
 * Bamtools
 * Bedtools
 * Samtools
 
 ### Statistical Computing
 * R
 * Cufflinks : 
 ```
 Cufflinks assembles transcripts, estimates their abundances, and tests for differential expression and regulation in RNA-Seq samples. It accepts aligned RNA-Seq reads and assembles the alignments into a parsimonious set of transcripts. Cufflinks then estimates the relative abundances of these transcripts based on how many reads support each one, taking into account biases in library preparation protocols.
 ```
 * Samtools
 * Bedtools
 
 ## Input
 Data from major experimental assay types generated by the project: 
 * RNA-seq, 
 * RAMPAGE, 
 * ChIP-seq, 
 * DNase-seq, 
 * ATAC-seq ,
 * WGBS
 
 ## Type Of Pipelines
 
 * RNA-seq pipelines
 * RAMPAGE pipelines
 * Chromatin Immunoprecipitation pipelines 
 * DNA accessibility pipelines
 * DNA methylation pipeline
 
 ## RNA-Seq Pipelines
 * RNAs Long Reads - longer than 200 bp: for mRNAs (poly-A(+)), rRNA-depleted total RNA, or poly-A(-) RNA populations
     * Paired-end
     * Single-ended

 * RNAs Short reads - shorter than 200 bp: for mRNAs (poly-A(+)), rRNA-depleted total RNA, or poly-A(-) RNA populations
 * miRNA-seq: for microRNAs, around 22nt long, that are quantified from RNA-seq data
 * miRNA counts: a complement to miRNA-seq 

## RAMPAGE Pipelines

RAMPAGE (RNA Annotation and Mapping of Promoters for the Analysis of Gene Expression) is a very accurate sequencing approach to identify transcription start sites (TSSs) at base-pair resolution, to quantify their expression, and to characterize their transcripts. RAMPAGE uses direct cDNA evidence to link specific genes and their TSSs.

 ## USEFUL LINKS
 * Data Processing Pipelines: https://www.encodeproject.org/pipelines/
