# Galaxy_EUserver_Feline_Nanopore
This GitHub contains the following:

Nanopore workflow: 
- A .ga file of the Nanopore promethION analysis pathway.
- A .ga file of the Nanopore GridION analysis pathway.
- Some example files. ([Galaxy](Galaxy))

Sequencing Metrics: 
- The PNG images of the outputs from MutliQC based on the sequencing metrics 

Differential Expression: 
- The output files of the limma-voom analysis

Variant Calling: 
- The VCF files on the output of SnpEff
- The VCF files on the output of SnpEff based on HCM-specific genes

Transcript detection: 
- The output files of StringTie based on catID
- The output merged file of StringTie

## Overview of the project

### Feline cardio-RNA sequencing analysis  
The direct RNA-sequencing analysis workflow in Galaxy starts by uploading the base called fastQ format files divided into two groups. The input data consists of single-end reads sequenced with a PromethION.  
* The read quality of the FastQ file will be assessed and filtered using FastQ. After filtering of the reads, the reads will be mapped against the reference genome, which in this case is FelCat9, by using Minimap2 to figure out where the sequences originated from in the genome.
* A sequencing metric analysis will be performed using the Samtools stats tools, and MultiQC will be used to make an overview of the results by creating a report. 
* To quantify the number of reads mapping to the exons of each gene, featureCounts will be used.
* FreeBayes will be used to call variants, followed by SnpEff to annotate said variants. 
* Limma-voom will then be used for the differential expression analysis. After this, the results will then be visualised through a heatmap and a volcano plot.

For more information, please contact:
* Frank van Steenbeek https://www.uu.nl/medewerkers/FGvanSteenbeek.
* Magdalena Harakalova https://www.umcutrecht.nl/en/research/researchers/harakalova-magdalena-m.

### Workflow Overview
