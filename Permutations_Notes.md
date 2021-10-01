# Run spin permutations

### Set working directory
setwd("C:/Users/Angelika/Dropbox/PhD/EXPERIMENTS/04_StructureFunction/SCRIPTS") 

###  Load necessary functions
library(matrixStats)
source("rotate.parcellation.R")
source("perm.sphere.p.R")

### Load coordinates as arrays
###### left coordinates
coord_l = scan("C:/Users/Angelika/Dropbox/PhD/EXPERIMENTS/OTHER/YAS_genes_09.04.21_with_mp/SpherePermutations/Schaefer114_coordinates_lh.txt")
coord_l = matrix(coord_l, ncol = 3, byrow = TRUE)
###### right coordinates
coord_r = scan("C:/Users/Angelika/Dropbox/PhD/EXPERIMENTS/OTHER/YAS_genes_09.04.21_with_mp/SpherePermutations/Schaefer114_coordinates_rh.txt")
coord_r = matrix(coord_r, ncol = 3, byrow = TRUE)

### Run 1000 spin permutations
perm_matrix = rotate.parcellation(coord.l = coord_l,coord.r = coord_r,nrot = 1000)

### Export to txt
write.table(perm_matrix, file="C:/Users/Angelika/Dropbox/PhD/EXPERIMENTS/OTHER/YAS_genes_09.04.21_with_mp/SpherePermutations/permutations_Schaffer114.txt", row.names=FALSE, col.names=FALSE)