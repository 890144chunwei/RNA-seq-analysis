# RNA-seq-Analysis
(RNA-seq pipeline used for publication at Chen et. al)

The pipeline aims to streamline processing raw fastq files, sequence alignment, reads counting, and downstream differential analysis, generating publication-ready plots. Most of the analyses are built on top of existing tools and/or packages publicly available. Please find the reference as indicated. Here, the pipeline demonstration consisits of two parts, seqeunce alignment and read count in Bash script (part I) and differential analysis and plotting in R script (Part II):

Part I. Alignment and read counting (Bash):
-----
- [bcl2fastq](https://support.illumina.com/sequencing/sequencing_software/bcl2fastq-conversion-software.html): Demultiplexing from raw sequencing reads in bcl files from the Sequencer.
- [fastqc](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/)/[multiqc](https://multiqc.info/): Quality control for sequencing reads
- [STAR](https://github.com/alexdobin/STAR): Read alignment sensitive for spliced transcripts to acquire BAM file
- [samtools](https://github.com/samtools/samtools): Sorting and indexing of mapped BAM file
- [featureCounts](https://academic.oup.com/bioinformatics/article/30/7/923/232889): Counting reads aligned to each transcript for downstream analysis
- [bamCoverage](https://github.com/deeptools/deepTools/blob/master/docs/content/tools/bamCoverage.rst): Normalization of mapped reads to generate bigwig file for visualization

Part II. Differential analysis (R):
-----
- [DESeq2](https://github.com/mikelove/DESeq2): Differential analysis taking counts file as input for normalization and statistical inference
- [ggplot2](https://github.com/tidyverse/ggplot2): For basic QC plotting
- [dplyr](https://github.com/tidyverse/dplyr): Organize count data for downstream analysis
- [clusterProfiler](https://github.com/YuLab-SMU/clusterProfiler): Gene set enrichment analysis (GSEA) to identify top-regulated pathways
- [enrichplot](https://github.com/YuLab-SMU/enrichplot): Figure plotting for GSEA results
- [EnhancedVolcano](https://github.com/kevinblighe/EnhancedVolcano): Figure plotting of log2-fold-change to P-value
- [pheatmap](https://github.com/raivokolde/pheatmap): Figure plotting and visualization for expression of specific gene sets 
