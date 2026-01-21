# ist_workshop006

# NOTES REGARDING NGS WORKSHOP 
REPORT ON 10 DAYS NGS WORKSHOP
Author-Arijeet ball

# WHAT IS NGS ?
Next-Generation Sequencing (NGS) is a high-throughput technology that sequences millions of DNA fragments simultaneously, accurately determining nucleotide sequences (A, T, C, G) faster and more cost-effectively than traditional Sanger sequencing.

# HOW NGS WORK:
Next-Generation Sequencing (NGS) determines the sequence of DNA through a series of coordinated steps:
.Library Preparation: DNA is fragmented into small pieces, and specialized adapters are attached to the ends to enable sequencing.

.Amplification: The fragments are amplified, often using PCR, to generate millions of copies for reliable detection.

.Sequencing: Each fragment is sequenced in parallel using platforms that detect the incorporation of nucleotides (A, T, C, G) in real-time or through imaging methods.

.Data Analysis: Advanced computational tools align the reads to a reference genome or assemble them de novo, producing a complete sequence and identifying variants, mutations, or other genomic features.

All analyses were conducted using Galaxy, a robust, open-source, web-based platform tailored for data-intensive biomedical research. Raw mouse mammary RNA-Seq data in FASTQ format were retrieved from Zenodo https://zenodo.org/records/4249555. The four FASTQ files were uploaded to Galaxy, where they were processed and analyzed using a series of specialized bioinformatics tools to ensure accurate and reproducible results.
https://github.com/arijeet006/ist_workshop006/blob/6eb1eaefca0ca9eb9e013dedb52d79574bb42fe8/536233173-39372ef4-d8f7-492a-8f1f-b536a73683a8.png


# 1.FASTQC TOOL
FastQC is a tool used to check the quality of sequencing data before analysis. It evaluates key aspects like per-base sequence quality, GC content, sequence duplication, adapter contamination, and overrepresented sequences, helping ensure the data is clean and reliable for downstream analyses such as genome assembly or mutation detection.
https://github.com/arijeet006/ist_workshop006/blob/b09d965094139cb522596a2243f928873aa814cc/536280521-b51d3368-dbef-4f83-97fa-273d96c9c3c9.png
https://github.com/arijeet006/ist_workshop006/blob/95379e5a48635821ea964f655095a0086eb70c4e/536343367-6b37194e-b360-4c61-a24d-19810988ddfd.png
https://github.com/arijeet006/ist_workshop006/blob/d0a4e26eab16c3467920e3111b9abdec7b3393f7/536349647-4fb5b494-71f5-4168-8023-20e28c1bdb57.png



# 2.TRIM GALORE
Trim Galore is a Perl-based wrapper script widely used in bioinformatics to automate the quality control and trimming of high-throughput sequencing (NGS) data. It integrates the functionality of Cutadapt, which removes adapter sequences and low-quality bases from the reads, and FastQC, which performs post-trimming quality checks. By combining these tools into a single streamlined workflow, Trim Galore simplifies the preprocessing of NGS data and ensures that the resulting reads are clean, high-quality, and ready for downstream analyses.


# 3.BOWTIE2
After cleaning the sequencing data with Trim Galore, you are left with millions of short DNA fragments, or reads. The next step is to determine their exact origin within the genome, a process known as read alignment. Bowtie2 is a tool designed for this purpose, efficiently mapping each read to its corresponding location in the reference genome.


# 4.FEATURECOUNTS
FeatureCounts is a tool used for quantifying gene expression. After aligning your reads to the genome with Bowtie2, it counts how many reads map to each gene. This allows you to determine the expression levels of different genes, indicating which genes are highly active and which are less expressed.


# 5.DEseq2
DESeq2 represents the final and most crucial step in the RNA-Seq analysis pipeline. It is used to perform Differential Gene Expression (DGE) analysis, identifying genes whose expression levels significantly differ between experimental conditions.


# 6.HEATMAP2
heatmap.2 is a specialized R function from the gplots package, used to generate one of the most informative and visually appealing representations in RNA-Seq analysis: the heatmap. It allows for the visualization of gene expression patterns across samples, highlighting similarities, differences, and clusters in the data.


# 7.KYOTO ENCYCLOPEDIA OF GENES AND GENOME (KEGG)
KEGG (Kyoto Encyclopedia of Genes and Genomes) is a bioinformatics resource used to interpret gene lists in the context of biological pathways. After completing DESeq2 analysis and generating a heatmap, you may have a list of significant genes. Instead of viewing them as isolated names (e.g., PFK1, HK2, LDHA), KEGG maps these genes onto pathways, illustrating how they interact and function together within biological systems.








