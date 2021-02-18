# Introduction
These folders are the data analysis for the paper ''My Soul Got a Little Bit Cleaner'': Art Experience in Videogames

# Read use:

Each main analysis folder contains an html file (knitted from an RMD file of the same name in the same folder). These files contian an easily readable breakdown of all analyses we conducted.

For more information please refer to the paper and/or it's corresponding author; For reproducing the results please refer to below:


# Reproducing the results:

Start by running the GamesAsArt_DataPreparation.rmd file in the DataPreparation Folder. This will turn the raw data into subset data files for each of the Main Analyses.

Proceed then to the Main Analyses Folder which includes a dedicated folder for each analysis. Each folder includes an RMD analysis file which produces all outputs from the dedicated Data file created during Data Preparation.

## Required Software:
Most analysis can be done using R 3.6.3

- R can be found here: https://www.r-project.org/
- We recommend using R Studio: https://rstudio.com/
- all required packages are listed in (and automatically installed by) each .Rmd File.

The Latent Class analysis requires Jupyter

- Jupyter can be found here: https://jupyter.org/install

## Usage:
First run GamesAsArt_DataPreparation.rmd in the DataPreparation Folder.
This takes the RawData and prepares cleaned sub DataSets for the Network, qualitative, and demographic analysis.

## Latent Class Analysis in Jupyter:
This jupyter notebook reads in the file "NetworkAnalysis_DataFile.csv" performs a k-means cluster algorithm with 2 clusters and writes the following three csv-files:
ID_ClusterAssignmentOriginal.csv, AesthemosAveragebyCluster.csv, and AesthemoSTDbyCluster. In ID_ClusterAssignmentOriginial.csv you can find the assigment for each participant ID (id. Response_ID) to their cluster (0 or 1). The latter two files contain the mean of the items per cluster andn the standard deviation of the items per cluster respectively. They have the following structure: the columns represent the 42 aesthemos items and the rows represent cluster 0 and 1. The entries are the average (standard deviation) of the aesthemos items with respect to the cluster.

Cluster, IntellectualChallenge_1_AESTHEMOS, Relaxation_1_AESTHEMOS,...
0, 3.5, 3,6,...
1, 2.6, 2,4,...

The jupyter notebook also produces an elbow plot to analyze the fitting number of clusters. It also plots the items and the average per item per class and the standard deviation per item per class. In the last part (commented out), a principal component analysis is performed for 2 dimenstions and the result is visualized according to the clusters.

It uses the following imports:
import re
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.cluster import KMeans
from sklearn.decomposition import PCA
import numpy as np

