# Homework 2 (deadline 9 March 2018 @ 11:59PM)

## Task 1: Exploratory data analysis (1.5  points)
**Learning objective**: Learn how to use exploratory data analysis techniques to detect issues with data quality.

The [gene expression data tutorial](https://github.com/kauralasoo/MTAT.03.239_Bioinformatics/blob/master/gene_expression/Exploring_gene_expression.md) tells you how to get started with analysing gene expression data in R. The dataset used in the tutorial has already been cleaned, but this is usually not the case for real biological data. For example, sometimes samples can get accidentally mis-labeled in the laboratory. A common occurence (that has happened to me me as well!) is that different treatments from the same individual are accidentally swapped. 

In this exercise, your task is to download a 'dirty' [gene expression dataset](https://courses.cs.ut.ee/2018/bioinfo/spring/uploads/Main/RNA_SummarizedExperiment_swapped.rds.gz) and use exploratory data analysis techniques (heatmap, PCA) to identify which (if any) of the samples have been swapped. In your report, please include the plots that you created, the code that you used to generate these plots and the names of the samples that have been swapped and what should be their correct names.

## Task 2: Differential expression analysis (2 points)
**Learning objective**: Learn how to identify genes that are significantly differentially expressed between two conditions.

 1. Following the gene expression tutorial, identify genes that are significantly differentially expressed between the naive and interferon-gamma (IFNg) conditions (false discovery rate (FDR) < 0.01). How many genes are there? How many genes have absolute log2 fold-change > 1? How many genes are upregulated (increase in expression after stimulation) by IFNg stimulation at these fold-change and FDR thresholds? How many genes are downregulated (decrease in expression after stimulation)? (NOTE: the sign of the log2 fold-change depends on the factor levels of the conditions that you put into the model, always check that the sign is what you expect it to be using raw counts!)
 2.  Repeat the same differential expression analysis on the naive *versus* *Salmonella* (SL1344) conditions. Answer the same questions that you answered in point 1. 
 3. Make a scatter plot of the shrunken log2 fold changes from the two comparisons (naive vs IFNg on one axis and naive vs SL1344 on the other axis) and add it to your report. Make sure to include all gene in the scatter plot. What is the correlation? Are there any other patterns of interest?

## Task 3: Functional enrichment analysis (1.5 points)
**Learning objective:** Learn how to interpret the differentially expressed gene lists that you generated in Task 2.

 1. Identify genes that are **upregulated** after IFNg stimulation (FDR < 0.01, log2 fold-change > 1). Copy this gene list into [g:Profiler](https://biit.cs.ut.ee/gprofiler/), disable "Hierarchical sorting" under the options and run the analysis. Report the top 20 most strongly enriched terms. Can you find evidence that this gene list corresponds to response to interferon-gamma? 
 2. Repeat the same g:Profiler analysis for genes differentially expressed after Salmonella infection (FDR < 0.01, log2 fold-change > 1). Report the top 20 most enriched terms. How do the results compare to the IFNg response? Are there specific enrichments that you did not see in the IFNg results?

# Bonus tasks 1 (deadline 16 March 2018 @ 11:59PM) 

 1. How many principal components of the [full gene expression dataset](https://courses.cs.ut.ee/2018/bioinfo/spring/uploads/Main/RNA_SummarizedExperiment.rds.zip) (336 samples) can you 'explain' by known sample metadata? You can view the sample metadata using the colData() function of the SummarizedExperiment class and you can find a longer description of the metadata columns in [here](https://zenodo.org/record/1188300/files/RNA_metadata_columns.txt). In your report, provide evidence (e.g. scatter plot) for each principal component that you think can be explained by known metadata. (2 point)
 3. How many biological replicates do you need to detect detect 80% of the genes that are at least 2-fold differentially expressed in the full dataset of 84 individuals (336 samples in total)? Perform this analysis both for the naive vs IFNg comparison as well as the naive vs Salmonella comparison. This task is inspired by a recently published [paper](http://rnajournal.cshlp.org/content/22/6/839). (2 points)

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4MjA2MjA2NDldfQ==
-->