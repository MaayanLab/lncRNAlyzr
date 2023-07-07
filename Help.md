### lncRNAlyzr
## About
lncRNA are an understudied part of the human genome 
Gene and protein enrichment analysis is a critical step in the analysis of data collected from omics experiments. Enrichr is a popular gene set enrichment analysis web-server search engine that contains hundreds of thousand annotated gene sets; it provides a comprehensive resource for annotated gene sets based on existing biological knowledge. While Enrichr has been useful in providing enrichment analysis against many gene set libraries from different domains, integrating enrichment results across libraries and domains of knowledge can further hypothesis generation. To this end, Enrichr-KG is a knowledge graph and web-server application that combines selected gene set libraries from Enrichr and presents these to the user for integrated analysis and visualization. Nodes in Enrichr-KG are either genes or functional terms, while edges connect genes to their enriched terms. This graphical representation of Enrichr libraries can illuminate hidden associations between genes and annotated terms from across multiple datasets. Enrichr-KG currently serves over 20 gene set libraries from different categories that include transcription, pathways, ontologies, diseases/drugs, and cell types. Enrichr-KG is freely available at https://maayanlab.cloud/enrichr-kg.

## Please note: lncRNAlyzr is in development

Background Information
What is a gene set?
A gene set is a group of genes that share a common biological function. A gene set can be the product of a high-throughput experiment such as differential expression analysis of microarray or RNA-Seq data or it can be an annotated set created from prior knowledge.

Gene sets can be fuzzy or crisp. In a crisp set, an element is either a member of the set or not. In a fuzzy or quantitative set, an element has an associated value indicating a degree of membership. Enrichr accepts both crisp and fuzzy gene sets as input.

With fuzzy set input the membership is defined as 1 for full membership, and 0 for no membership. Hence if you have a ranked set of differentially expressed genes with p-values or fold-change values, you would need to convert these to membership values between 0 and 1, keeping the ranks and scaling as appropriate. In general, it is recommended that non-computational users should always submit crisp sets; this is because preparing a proper fuzzy set as input requires some computational skills and submitting a fuzzy set with the data not correctly transformed can lead to erroneous results.

What is enrichment analysis?
Enrichment analysis is a computational method for inferring knowledge about an input gene set by comparing it to annotated gene sets representing prior biological knowledge.

Enrichment analysis checks whether an input set of genes significantly overlaps with annotated gene sets.

For more information, you can read this excellent review about enrichment analysis [1].

What is an enrichment term?
Each gene set within the Enrichr database is associated with a functional term or an enrichment term such as a pathway, cell line, or disease. The output of Enrichr are ranked sets of terms, one set for each gene set library. The most highly ranked enrichment terms for the user's input gene set provide knowledge about the input set.

What is a gene set library?
A gene set library is a set of related gene sets or enrichment terms.

Each enrichment term in Enrichr's results pages is organized by its gene set library. These libraries have been constructed from many sources such as published studies and major biological and biomedical online databases. Others have been created for and only available through Enrichr. For example, the ChEA 2015 library is a set of functional terms representing transcription factors profiled by ChIP-seq in mammalian cells. Each term is associated with a collection of putative targets inferred from the peaks identified in each ChIP-seq study.

What are the four enrichment result scores?
Enrichr implements four scores to report enrichment results: p-value, q-value, rank (Z-score), and combined score.

The p-value is computed using a standard statistical method used by most enrichment analysis tools: Fisher's exact test or the hypergeometric test. This is a binomial proportion test that assumes a binomial distribution and independence for probability of any gene belonging to any set.

The q-value is an adjusted p-value using the Benjamini-Hochberg method for correction for multiple hypotheses testing.
