# ist_workshop006

# NOTES REGARDING NGS WORKSHOP 
REPORT ON 10 DAYS NGS WORKSHOP
# Author-Arijeet ball
Student of first year, b.tech biotechnology, Shoolini university

# WHAT IS NGS ?
Next-Generation Sequencing (NGS) is a high-throughput technology that sequences millions of DNA fragments simultaneously, accurately determining nucleotide sequences (A, T, C, G) faster and more cost-effectively than traditional Sanger sequencing.

# HOW NGS WORK:
Next-Generation Sequencing (NGS) determines the sequence of DNA through a series of coordinated steps:
.Library Preparation: DNA is fragmented into small pieces, and specialized adapters are attached to the ends to enable sequencing.

.Amplification: The fragments are amplified, often using PCR, to generate millions of copies for reliable detection.

.Sequencing: Each fragment is sequenced in parallel using platforms that detect the incorporation of nucleotides (A, T, C, G) in real-time or through imaging methods.

.Data Analysis: Advanced computational tools align the reads to a reference genome or assemble them de novo, producing a complete sequence and identifying variants, mutations, or other genomic features.

# What is Galaxy software?
Galaxy is a web-based, open-source bioinformatics platform that allows users to analyze biological data without needing programming or command-line skills. It provides a simple graphical interface where complex analyses can be performed by selecting tools and setting parameters through clicks instead of writing code.

Galaxy is mainly used for NGS data analysis, including RNA-seq, variant analysis, and functional annotation. Users upload their data (such as FASTQ files), run different analysis tools step by step, and view the results in the same interface. Every step is automatically saved in a workspace called a history, which makes the analysis easy to reproduce and share.

One of Galaxy’s biggest advantages is that it removes the need for software installation and dependency management, as all tools are already available on public servers. Because of this, Galaxy is widely used by students, researchers, and beginners to perform reliable and reproducible bioinformatics analyses efficiently.

# What are the different sites for data base extraction ?
There are several commonly used databases for biological data extraction, depending on what type of information you need. For gene and sequence data, the most widely used database is NCBI, which provides access to DNA, RNA, protein sequences, gene information, and genomes. Closely related to this are Ensembl, which focuses on genome annotation for many organisms, and UCSC Genome Browser, which is mainly used for genome visualization and annotation.

For protein-related information, databases like UniProt are used to extract detailed protein sequences, functions, domains, and annotations. If you are interested in pathways and functional information, KEGG is commonly used to understand metabolic and signaling pathways, while Reactome provides curated biological pathway data with detailed molecular interactions.

For gene expression and functional enrichment analysis, databases such as Gene Ontology (GO) are used to describe gene functions, biological processes, and cellular components. In addition, GEO (Gene Expression Omnibus) and ArrayExpress are popular databases for extracting publicly available RNA-seq and microarray datasets.

In summary, NCBI, Ensembl, and UCSC are mainly used for sequence and genome extraction, UniProt for protein information, KEGG and Reactome for pathways, and GEO or ArrayExpress for expression datasets.

All analyses were conducted using Galaxy, a robust, open-source, web-based platform tailored for data-intensive biomedical research. Raw mouse mammary RNA-Seq data in FASTQ format were retrieved from Zenodo https://zenodo.org/records/4249555. The four FASTQ files were uploaded to Galaxy, where they were processed and analyzed using a series of specialized bioinformatics tools to ensure accurate and reproducible results.
![Screenshot](https://github.com/arijeet006/ist_workshop006/blob/6eb1eaefca0ca9eb9e013dedb52d79574bb42fe8/536233173-39372ef4-d8f7-492a-8f1f-b536a73683a8.png)


# 1.FASTQC TOOL
FastQC is a tool used to check the quality of sequencing data before analysis. It evaluates key aspects like per-base sequence quality, GC content, sequence duplication, adapter contamination, and overrepresented sequences, helping ensure the data is clean and reliable for downstream analyses such as genome assembly or mutation detection.
![Screenshot](https://github.com/arijeet006/ist_workshop006/blob/b09d965094139cb522596a2243f928873aa814cc/536280521-b51d3368-dbef-4f83-97fa-273d96c9c3c9.png)
![Screenshot](https://github.com/arijeet006/ist_workshop006/blob/95379e5a48635821ea964f655095a0086eb70c4e/536343367-6b37194e-b360-4c61-a24d-19810988ddfd.png)
![Screenshot](https://github.com/arijeet006/ist_workshop006/blob/d0a4e26eab16c3467920e3111b9abdec7b3393f7/536349647-4fb5b494-71f5-4168-8023-20e28c1bdb57.png)



# 2.TRIM GALORE
Trim Galore is a Perl-based wrapper script widely used in bioinformatics to automate the quality control and trimming of high-throughput sequencing (NGS) data. It integrates the functionality of Cutadapt, which removes adapter sequences and low-quality bases from the reads, and FastQC, which performs post-trimming quality checks. By combining these tools into a single streamlined workflow, Trim Galore simplifies the preprocessing of NGS data and ensures that the resulting reads are clean, high-quality, and ready for downstream analyses.
![Screenshot](https://github.com/arijeet006/ist_workshop006/blob/73dba9fffa1281cbae93676af3b1ff89e73457eb/536813611-5053677d-69e9-49a0-b32c-aaca1d45c3e4.png)
![Screenshot](https://github.com/arijeet006/ist_workshop006/blob/04822420bbc72c0ca3f991aefe8ce5a89c6ab75d/536815888-5e1ee64d-665f-429d-bcdd-7892e0edf142.png)


# 3.BOWTIE2
After cleaning the sequencing data with Trim Galore, you are left with millions of short DNA fragments, or reads. The next step is to determine their exact origin within the genome, a process known as read alignment. Bowtie2 is a tool designed for this purpose, efficiently mapping each read to its corresponding location in the reference genome.
![Screenshot](https://github.com/arijeet006/ist_workshop006/blob/3e84968012ffeec6032693f94aa01cd7b3d50ed6/536839670-2910fa35-7822-4cc7-b3fa-76692e093dbc.png)
![Screenshot](https://github.com/arijeet006/ist_workshop006/blob/5b364063499f51424ce4cebae000a35acc2375e9/536845657-be3c45ed-e4f1-435e-8994-185758556c98.png)



# 4.FEATURECOUNTS
FeatureCounts is a tool used for quantifying gene expression. After aligning your reads to the genome with Bowtie2, it counts how many reads map to each gene. This allows you to determine the expression levels of different genes, indicating which genes are highly active and which are less expressed.
![Screenshot](https://github.com/arijeet006/ist_workshop006/blob/b2ca8e8accda0ade9f6890ad2f76f9e33c5ec1e0/536866744-0ceb7d79-e4ff-400b-b4f2-dcd0914df77a.png)


# 5.DEseq2
DESeq2 represents the final and most crucial step in the RNA-Seq analysis pipeline. It is used to perform Differential Gene Expression (DGE) analysis, identifying genes whose expression levels significantly differ between experimental conditions.
![Screenshot](https://github.com/arijeet006/ist_workshop006/blob/f81f713c797c32f933dcef6b4de20b02aed0877e/537448798-8b59986b-7f5e-478f-8b2a-4c0346ea38d0.png)
![Screenshot](https://github.com/arijeet006/ist_workshop006/blob/5c52cb17f2de21976f1823aa7fb5bd748c19c9bd/537493549-877b7d88-0a37-405e-9e2b-575e75371c05-2.png)

# 6.HEATMAP2
heatmap.2 is a specialized R function from the gplots package, used to generate one of the most informative and visually appealing representations in RNA-Seq analysis: the heatmap. It allows for the visualization of gene expression patterns across samples, highlighting similarities, differences, and clusters in the data.
![Screenshot](https://github.com/arijeet006/ist_workshop006/blob/966d4489c1fa1dc3f89be292b3942c9d29583a7f/537577384-86a318cc-7cec-4cb7-8d29-b7532a6da93e.png)


# 7.KYOTO ENCYCLOPEDIA OF GENES AND GENOME (KEGG)
KEGG (Kyoto Encyclopedia of Genes and Genomes) is a bioinformatics resource used to interpret gene lists in the context of biological pathways. After completing DESeq2 analysis and generating a heatmap, you may have a list of significant genes. Instead of viewing them as isolated names (e.g., PFK1, HK2, LDHA), KEGG maps these genes onto pathways, illustrating how they interact and function together within biological systems.
![Screenshot](https://github.com/arijeet006/ist_workshop006/blob/98b136d1c901f4885bd21e6bbacea8d764250a8c/537704024-e8637b1b-06ae-43a7-be2f-d4cf78ff323f.png)








