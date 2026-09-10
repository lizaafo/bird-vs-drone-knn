# Bird or Drone? Image Classification Using KNN

## Student

- **Name:** Elizabetha A.
- **Last four digits of ID:** 1642

## Project

This project classifies images as Bird or Drone using handcrafted image color and edge features with KNN.

## Dataset

- **Source:** Kaggle
- **Link:** [Drone vs Bird: Aerial Object Classification Dataset](https://www.kaggle.com/datasets/muhammadsaoodsarwar/drone-vs-bird?resource=download)
- **Images:** 4,106 total - 1,607 Bird and 2,499 Drone

The dataset is not stored in this repository.
Exact duplicates were removed, and related images were kept in the same data split to reduce leakage.

## Method

Four feature representations and 80 KNN configurations were compared using five-fold group-aware cross-validation. Bird F1-score was the main metric. Random undersampling was tested but not selected.

## Results

The final model used combined HSV-and-edge features, k=1, uniform voting, Manhattan distance and no undersampling.

| Evaluation | Accuracy | Bird F1 |
|---|---:|---:|
| Five-fold CV | 0.8876 | 0.8304 |
| Held-out test | 0.8874 | 0.8247 |

The model correctly classified 470 of 497 Drones and 200 of 258 Birds.

## Running the Notebook

Download the dataset from Kaggle and place the class folders in `dataset/bird` and `dataset/drone`.
