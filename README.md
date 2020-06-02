# **Cluster credibility function for R**

The cluster credibility (Jardim de Queiroz et al. 2020) allows to test explicitly different hypotheses of species (or clusters) based on the STACEY's output (Jones, 2017).

The function requires 
(1) the clustering output (*txt format) obtained after running SpeciesDelimitationAnalyser (Jones et al., 2015).
and
(2) a list of vectors containing the different clustering hypotheses.

How to run:

```
#Upload SpeciesDelimitationAnalyser output:
clustering_matrix <- read.table(paste("clusterings.txt", sep=""), header=TRUE)

#Create a list of clustering:
clusters <- list() 

clusters$cluster1 <- c("specimen1",
		       "specimen2")

clusters$cluster2 <- c("specimen1",
 		       "specimen3")	
											
clusters$cluster3 <- c("specimen1",
		       "specimen2",
		       "specimen3")
                       
clusters$cluster4 <- c("specimen1")


#Run CC:
source("cluster_credibility.R", chdir = TRUE)

cc(clustering_matrix, clusters)

#It returns a data frame containing two columns: name of the clustering hypothesis and the value of CC
```

## **References**

Jardim de Queiroz et al. 2020. *Mol Phyl Evol*. https://doi.org/10.1016/j.ympev.2019.106711.

Jones, G., 2017. *J. Math. Biol.* https://doi.org/10.1007/s00285-016-1034-0

Jones, G. et al. 2015. *Bioinformatics.* https://doi.org/10.1093/bioinformatics/btu770
