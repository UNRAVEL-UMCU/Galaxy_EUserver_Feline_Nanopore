# Galaxy_EUserver_Feline_Nanopore
This github contains:

Nanopore workfow: 
- a .ga file of the Nanopore analysis pathway
- a .svg image of the workflow 
- a .ga file of the alternative count analysis pathway
- Some example files. ([Galaxy](Galaxy)) 

## Overview of the project

### Feline cardio-RNA sequencing analysis  
The direct RNA-sequencing analysis workflow in Galaxy starts by uploading the basecalled fastQ format files divided into two groups. The input data consists of single-end reads sequenced with a PromethION.  
* The read quality of the FastQ file will be assessed and filtered using FastQ. After filtering of the reads, the reads will be mapped against the reference genome, which in this case is FelCat9, by using Minimap2 to figure out where the sequences originated from in the genome.
* A sequencing metric analysis will be perfomed using the samtools stats tools, and MultiQC will be used to make an overview of the results by creating a report. 
* To quantify the number of reads mapping to the exons of each gene, featureCounts will be used.
* FreeBayes will be used to call variants, follwed by SnpEff to annotate said variants. 
* Limma-voom will then be used for the differential expression analysis. After this, the results will then be visualized through a heatmap and a volcano-plot.
