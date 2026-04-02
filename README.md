# KNN Implementation using MapReduce in Spark

This repository presents the implementation of K Nearest Neighbors (KNN) in MapReduce using Spark. We implement both an RDD and a DataFrame methodology. This is an application of the paper *"A MapReduce-based k-Nearest Neighbor Approach for Big Data Classification"* by Maillo et al. (2015), which can be found [here](https://sci2s.ugr.es/sites/default/files/files/TematicWebSites/BigData/A%20MapReduce-based%20k-Nearest%20Neighbor%20Approach%20for%20Big%20Data%20Classification-IEEE%20BigDataSE-2015.pdf). 
---

## Files Overview

- **knn-mr-rdd.ipynb**: KNN MapReduce using the Spark RDD API.
- **knn-mr-df.ipynb**: KNN MapReduce using the Spark DataFrame API.
- **rdd** and **df**: Results of RDD and DataFrame implementations.
---

## Algorithm

The MR-KNN algorithm splits the training set into `m` partitions. Each map task independently computes the `k` nearest neighbors of all test points within its partition. The reduce phase merges the partial neighbor lists from all map tasks and selects the globally closest `k` neighbors. A final majority vote determines the predicted class.

---

## Dependencies

- Apache Spark 4.1.1 (PySpark)

---

## Setup

1. Download the Poker Hand dataset from the [UCI ML Repository](http://archive.ics.uci.edu/ml) and place it in a folder named `Dataset/` at the root of the repository.
2. Run **knn-mr-rdd.ipynb** and/or **knn-mr-df.ipynb** in a Jupyter environment with PySpark configured.
