# Bird or Drone? Image Classification Using KNN

## Student

- **Name:** Elizabetha A.
- **Last four digits of ID:** 1642

## Project

This project examines whether handcrafted color and edge features can classify images as Bird or Drone. It includes data cleaning, group-aware splitting, feature engineering, a manual KNN implementation, five-fold cross-validation, test evaluation, explainability, and a K-Means extension.

## Dataset

- **Source:** Kaggle
- **Link:** [Drone vs Bird: Aerial Object Classification Dataset](https://www.kaggle.com/datasets/muhammadsaoodsarwar/drone-vs-bird?resource=download)
- **Images:** 4,106 total - 1,607 Bird and 2,499 Drone

The dataset is not stored in this repository. Exact duplicates were excluded, and related images were grouped to reduce leakage between data subsets.

## Method

Four feature representations were compared: grayscale pixels, HSV histograms, edge magnitude, and combined HSV-and-edge features. A grid of 80 KNN configurations tested several values of `k`, uniform or weighted voting, and Euclidean or Manhattan distance. Bird F1-score was the primary metric. Random undersampling was also evaluated for class imbalance.

K-Means was implemented as an unsupervised extension and evaluated with purity, NMI, silhouette score, and PCA.

## Results

The selected model used combined HSV-and-edge features, `k=1`, uniform voting, Manhattan distance, and random undersampling.

| Evaluation | Accuracy | Bird F1 |
|---|---:|---:|
| Five-fold CV | 0.9005 | 0.8587 |
| Held-out test | 0.9035 | 0.8555 |

On the test set, 480 of 524 drones and 222 of 253 birds were classified correctly. K-Means produced weak semantic separation: purity 0.651, NMI 0.0539, and silhouette score 0.0924.
