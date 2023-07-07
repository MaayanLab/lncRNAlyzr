## About

lncRNAs (long non-coding RNAs) make up a large portion of the human genome but are relatively understudied and less well understood than protein-coding RNAs. While there exist many tools, such as Enrichr and Enrichr-KG, to perform enrichment analysis on protein-coding genes, lncRNAlyzr is a knowledge graph and web-server application that provides enrichment analysis for lncRNA gene set libraries and presents results to the user for visualization. Knowledge graph nodes in lncRNAlyzr are either lncRNAs or functional terms, while edges connect lncRNAs to their enrichment terms. This graphical representation of lncRNA libraries (based on existing Enrichr coding-gene set libraries) can illuminate hidden associations between lncRNAs and annotated terms from across multiple datasets. lncRNAylzr currently serves over 20 gene set libraries from different categories that include transcription, pathways, ontologies, diseases/drugs, and cell types. lncRNAylzr is still under development.

---
## Background Information
### What is a gene set?
A gene set is a group of genes that share a common biological function. A gene set can be the product of a high-throughput experiment such as differential expression analysis of microarray or RNA-Seq data or it can be an annotated set created from prior knowledge.

### What is enrichment analysis?
Enrichment analysis is a computational method for inferring knowledge about an input gene set by comparing it to annotated gene sets representing prior biological knowledge. Enrichment analysis checks whether an input set of genes significantly overlaps with annotated gene sets.

### What is an enrichment term?
Each gene set is associated with a functional term or an enrichment term such as a pathway, cell line, or disease. The most highly ranked enrichment terms for the user's input gene set provide knowledge about the input set.

### What is a gene set library?
A gene set library is a set of related gene sets or enrichment terms.

### What are the enrichment result scores?
The p-value is computed using a standard statistical method used by most enrichment analysis tools: Fisher's exact test or the hypergeometric test. This is a binomial proportion test that assumes a binomial distribution and independence for probability of any gene belonging to any set.

The q-value is an adjusted p-value using the Benjamini-Hochberg method for correction for multiple hypotheses testing.

---
## Using lncRNAlyzr
### Performing Enrichment Analysis

A typical analysis with lncRNAlyzr begins by inputting a gene set in the main text box and selecting up to 5 lncRNA libraries to query. You can click "Try an Example" to populate the text box with an example gene set. You can further control the results by tweaking the following parameters:

Minimum libraries per gene: Filters out genes that are not enriched in multiple libraries.
Minimum links per gene: Filters out genes that do not overalap with multiple terms.
Minimum links per term: Filters out terms that only overlap with few genes.
Subgraph size limit: Controls the size of the subgraph by only keeping the top genes that are connected to multiple terms across libraries.

Furthermore, users can add a description to their gene set and control the number of terms returned per library. By default this is set to 5.

Upon clicking submit, the user is redirected to the results page. Nodes are colored based on their type. The results can be displayed as a bar chart showing the top enriched terms ordered by p-value. The icons on the upper right corner enable users to: (1) display the legend; (2) refresh, re-orient, or clear the graph; (3) display the edge labels; (4) download the graph as an image (JPG, PNG, or SVG); (5) share a permanent link; (6) enter full screen mode; and (7) summarize the results in text form.

Selecting the "Show Tooltip" option and then clicking on a node invokes a text box containing the metadata of the node. This has buttons to: (1) delete a node from the subnetwork; (2) go to the node's page to view its immediate neighbors; and (3) close the box.

### Querying Terms or Genes

lncRNAylzr also implements Enrichr's gene and term search functionality. This enables viewing the immediate neighbors for a gene, i.e., what annotated gene sets include that gene; or the immediate neighbors of a term, i.e., the genes associated with the term. Control icons in this display are similar to ones that are present in the enrichment results interface. Importantly, the user can control how many neighbors to display.

Furthermore, users can view selected relationships of interest by using the relations filter (if adding multiple relations, it may be necessary to increase the size of the graph using the slider to see the results).

lncRNAylzr also provides the ability to perform two term/gene search. This function finds all the shortest paths between any two entities within the lncRNAylzr knowledge graph. This fucntionality facilitates the discovery of hidden connections between functional terms and genes.

### Note: these instructions are adapted from https://maayanlab.cloud/Enrichr/help#background and https://maayanlab.cloud/enrichr-kg/tutorial
