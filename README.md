#Processing of RNA-seq data with aim to define functions of Pcbp1 protein  in mouse emrionic stem cells

## **Project goals and objectives**
Aim of this project is to study the expression profiles of mouse ESCs in the initial pluripotent state("Naive") and early primed state (EpiLC) with knockouts of the _pcbp1_ gene. 

**Tasks:**
1) Processing and evaluating the quality of raw reads
2) Alignment to the mouse reference genome
3) Visualization of the received data
4) Differential analysis of gene expression
5) Analysis of the results obtained


## Materials and methods
The cDNA libraries were prepared with 3 replicas of each of the 4 cell types: Naive _pcbp1_-KO, Naive WT, EpiLC _pcbp1_-KO, EpiLC WT. Sequencing was performed by Illumina NovaSeq 6000 (single-end 100bp). Raw reads were uploaded to the **Galaxy web platform**, and a public server was used on usegalaxy.org for further analysis. The data was processed with **Trimmomatic**  Galaxy Version 0.38.0 with arguments: -SE SLIDINGWINDOW:4:20 HEADCROP:13. Alignments were performed with **RNA STAR** tool Galaxy Version 2.6.0b-1 with arguments: outFilterMultimapNmax 1, -- outReadsUnmapped Fastx, -- outSAMtype BAM SortedByCoordinate, -- twopassMode Basic. Programs from the RseQC package were used for more detailed evaluation of alignments: **ReadDistribution** Galaxy Version 2.6.4.1, **Gene Body Coverage(BAM)**  Galaxy Version 2.6.4.3. Then the number of reads associated with each gene was calculated using the **featureCounts** Galaxy Version 1.6.4+galaxy1 utility. Differential expression analysis of two groups (KO samples and Non-KO samples) was performed using the DESeq2. Genes with FDR (false discovery rate) < 0.01 found by DESeq2 were assigned as differentially expressed. 

## Results
In the issue, the tables of differentially expressed genes for Naive and EpiLC _pcbp1_-KO cells were obtained. Analysis of these tables allowed us to acquire schemes of the signaling pathways affected at knockout of this gene. Next is planned a detailed analysis of the genes involved in the signaling pathways responsible for maintaining the  mouse embryonic stem cell pluripotency.