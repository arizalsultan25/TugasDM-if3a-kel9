#Set Working Directory
wd <- "D:/Tugas Kelompok Data Mining (IF 3A) - Kelompok 9"
setwd(wd)
getwd()

#Insert dataset
dataset <- read.csv("buddymove_holidayiq.csv", header = TRUE, sep = ",")
#seleksi dataset hanya dari kolom 2-7
input=dataset[,2:7]

#Kmeans Clustering

#install library
install.packages("tidyverse")
install.packages("gridExtra")
install.packages("ggplot2")
install.packages("factoextra")
install.packages("cluster")
library(cluster)
library(ggplot2)
library(factoextra)
library(tidyverse)
library(gridExtra)

#mencari jumlah cluster yang ideal
fviz_nbclust(input,kmeans,method = "silhouette")
#membuat variable kmeans
k3 <- kmeans(input,centers=3,nstart = 25)
#menampilkan hasil cluster
fviz_cluster(k3,geom = "point",data=input)+ggtitle("Data Holiday jika dibagi 3 Cluster")
#melihat rangkuman variable k3
k3


#Agglomerative Hierarchical Clustering
#Install Package Dependency
install.packages("colorspace")
install.packages("maggritr")
library(colorspace)
library(magrittr)

#scaling dataset di cluster
sc <- input %>% scale() %>% dist(method = "euclidean") %>%  hclust(method = "ward.D2")
#melihat model
sc
#membuat model virtual
fviz_dend(sc,k=3,
          cex = 0.5,
          k_colors = c("#2E9FDF","#FC4E07","#00AFBB"),
          color_labels_by_k = TRUE,
          rect = TRUE)

#melihat isi dari cluster
k3$size
