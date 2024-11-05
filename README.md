# Unsupervised ML Image Clustering

## Problem Statement

Evaluating unsupervised machine learning algorithms often requires manually inspecting the outputs to understand their performance and suitability for specific datasets. In this project, we compare three clustering algorithms – **K-Means**, **Agglomerative Clustering**, and **DBSCAN** – on the **wild dataset** to observe how each algorithm affects clustering outputs.

This project highlights that clustering evaluation is a largely qualitative procedure, making it especially useful during the exploratory phase of data analysis. We examine each algorithm's clustering granularity control:
- **K-Means** and **Agglomerative Clustering** let users define the number of clusters.
- **DBSCAN** uses an `eps` parameter to set proximity thresholds, indirectly controlling cluster size.

## Project Overview

In this analysis:
- **K-Means** provides relatively evenly sized clusters, with each point represented by its closest cluster center, making it a straightforward decomposition method.
- **DBSCAN** detects "noise points" (unclustered points) and can automatically determine the number of clusters. Unlike the other methods, DBSCAN supports complex cluster shapes, which we observed in the "two moons" example.
- **Agglomerative Clustering** builds a hierarchy of partitions, allowing for a detailed inspection of clustering structures through dendrograms.

Each algorithm has unique strengths and potential drawbacks, making them suitable for different types of datasets and clustering goals.

## Findings

Key observations from evaluating the clustering algorithms include:

1. **DBSCAN**: The clustering output varies with the `eps` parameter. An `eps` of 5 generated several small clusters and numerous noise points, while lower values resulted in all points being labeled as noise.
2. **K-Means**: Produced clusters of relatively similar sizes (ranging from 81 to 178), in contrast to DBSCAN’s results.
3. **Agglomerative Clustering**: Produced more evenly sized clusters than DBSCAN, though not as uniform as K-Means.
4. **ARI Score**: The Adjusted Rand Index (ARI) between `labels_agg` (Agglomerative Clustering) and `labels_km` (K-Means) was 0.25, indicating limited similarity. This discrepancy may arise because points farther from cluster centers do not align well with K-Means clustering assumptions.

## Conclusion

This project demonstrates that manual inspection of clustering outputs can reveal the relative strengths and limitations of different algorithms. Such insights are valuable, particularly in image clustering tasks where a specific clustering pattern may be desirable. The choice of clustering algorithm and its parameters can significantly impact the output and should be tailored to the dataset's characteristics and the specific requirements of the analysis.

## Usage

To replicate this analysis:
1. Clone this repository.
   ```bash
   git clone https://github.com/ibrahimbilal/Unsupervised-ML-image-clustering.git
   cd Unsupervised-ML-image-clustering

