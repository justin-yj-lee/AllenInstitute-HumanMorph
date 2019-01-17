# AllenInstitute-HumanMorph
## Project Overview
Spent winter break at summer internship site (Allen Institute for Brain Science, Seattle, WA) analyzing the Allen's Human Cell Morphological Data. Ran clustering analyses on human aspiny and spiny cell data sets, trying to verify clusters with qualitative calls of morphological type. In the co-clustering analysis for morpho type identification, hierarchical clustering has been used for each subsampled data set. There are various other methods for clustering available; therefore, **the purpose of this project was to compare different clustering methods as applied to the human morphology data and verify whether it is ok for us to use hierarchical clustering or ideal to use another method.**

## Data Description
The Allen Human Morphological (ME) Data (project H301) contains 40 aspiny/inhibitory and 108 spiny/excitatory neurons with 45 and 42 morphological features, respectively. Also provided are the qualitative call assignments for the morphological type of the neurons determined by researchers at the Allen Institute.

## Strategies
Clustering Methods (k-Means, Mean Shift, Hierarchical, Spectral*)
Rand Index (a similarity measure between two clusterings; applied to compare qualitative call clusters with calculated clusters)
*See Jupyter Notebooks*

## Pre-processing Data
Cleaned initial data set for highly correlated features and filtering through qualitative calls (excluding apical truncated neurons and 

## Dimensional Reduction
Used PCA for dimensional reduction and used loading scores of the morphological features in principal component 1 to find which features contributed most significantly to the overall variation. PCA also revealed any outliers in the data sets.

## Clustering
> How do we determine the number of clusters for certain algorithms? 
>> Elbow method, silhouette analysis, and gap statistic were used to optimize the number of clusters for k-Means analysis. 

>> Mean-shift analysis estimates the number of clusters within the algorithm.

>> Hierarchical analysis yields a dendrogram where we can visually determine an optimal number of clusters.

> Comparing Clustering Methods
>> Comparing Rand Indices of the results for each clustering analysis with the qualitative calls supports the use of Hierarchical Clustering for Morpho Type Identification.

## Discussion and Conclusion
The overall low similarity between the calculated clusters and the qualitative calls means the algorithms are defining distance between and within clusters on different criteria than our own calls. It also means, certain subtypes of qualitative calls may be less similar to other major types and thus, more significant labels in distinguishing morpho type. The limitations in our impure data set may have contributed to the low similarity between the quantitative and qualitative clusters. Overally, hierarchical clustering is shown to be relatively strong compared to different clustering methods, besides K-Means being the strongest.

## Next Steps
1. Use the major principal components as the new set of features (i.e. first 10) and cluster again
2. Conduct co-clustering to increase robustness of results for each method.
3. Consider qualitative subtypes in light of yielded clusters
