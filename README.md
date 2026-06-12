# Netflix Recommendation System

## Project Overview

This project implements and compares two collaborative filtering approaches on the Netflix Prize dataset:

* Item-Based Collaborative Filtering (Item-CF)
* Singular Value Decomposition (SVD)

The objective is to predict user preferences and generate personalized movie recommendations. The models are evaluated on both rating prediction accuracy and recommendation ranking quality.

---

## Dataset

Netflix Prize Dataset

Dataset Characteristics (working subset):

| Property     | Value     |
| ------------ | --------- |
| Ratings      | 1,175,260 |
| Users        | 2,634     |
| Movies       | 1,287     |
| Rating Scale | 1–5       |

To make computation feasible, only highly active users and popular movies were retained.

---

## Methodology

### Item-Based Collaborative Filtering (Item-CF)

* Builds a user-item rating matrix
* Computes cosine similarity between movies
* Predicts ratings using the 30 most similar movies previously rated by the user
* Generates Top-K recommendations from predicted ratings

### Singular Value Decomposition (SVD)

* Matrix factorization approach
* Learns latent user and movie factors
* Captures hidden preference patterns
* Generates personalized recommendations based on factor interactions

---

## Evaluation Metrics

### RMSE (Root Mean Squared Error)

Measures rating prediction accuracy.

Lower values indicate better performance.

### MAP@10 (Mean Average Precision @ 10)

Measures recommendation ranking quality.

Higher values indicate better performance.

A movie is considered relevant if its actual test rating is **≥ 3.5**.

---

## Experimental Results

| Metric               | Item-CF | SVD      |
| -------------------- | ------- | -------- |
| RMSE                 | 0.9823  | 0.8455   |
| MAP@10               | 0.0632  | 0.1717   |
| Training Time        | ~0 s    | 25.3 s   |
| Prediction Time/User | 5.55 ms | 7.25 ms  |
| Memory Usage         | 7.72 MB | 27.83 MB |

### Key Finding

SVD significantly outperformed Item-CF in both rating prediction accuracy and recommendation ranking quality, making it the stronger recommendation model.

---

## Recommendation Analysis

| Measure                  | Item-CF | SVD   |
| ------------------------ | ------- | ----- |
| Average Top-10 Hits/User | 1.44    | 2.91  |
| Users with ≥ 1 Hit       | 62.0%   | 91.5% |

SVD generated more personalized recommendations and consistently surfaced more user-preferred movies.

---

## Repository Structure

```text
Netflix-Recommendation-System/
│
├── notebooks/
│   └── code Recommendation.ipynb
│
├── Results/
│   ├── model_comparison.csv
│   └── scaleup_comparison.csv
│
├── Report/
│   └── Technical_Report.pdf
│
├── Presentation/
│   └── Presentation.pdf
│
└── README.md
```

---

## Technologies Used

* Python
* Pandas
* NumPy
* SciPy
* Scikit-learn
* Surprise
* Jupyter Notebook

---

## Future Improvements

* Hybrid recommendation systems
* Cold-start handling
* Content-based features
* Additional ranking metrics (NDCG, Coverage, Diversity)
* Full Netflix Prize dataset evaluation

---

## Author

**Velamala Pujitha**
BSMS Mathematics and Computing
Indian Institute of Technology Roorkee
