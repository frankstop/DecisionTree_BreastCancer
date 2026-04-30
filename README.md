# DecisionTree_BreastCancer

Decision Tree classification pipeline for the Wisconsin Diagnostic Breast Cancer dataset. This project compares Gini and entropy splitting criteria, explores tree-depth tuning, evaluates train/test split behavior, and renders the notebook output through GitHub Pages.

## Project Overview

This repository demonstrates a supervised machine learning workflow for binary tumor classification:

- **Input:** Wisconsin Diagnostic Breast Cancer measurements
- **Target:** `diagnosis`
  - `0` = Benign
  - `1` = Malignant
- **Model:** `DecisionTreeClassifier` from scikit-learn
- **Main goals:**
  - Train an interpretable decision tree classifier
  - Compare Gini impurity vs. entropy
  - Evaluate precision, recall, F1-score, and accuracy
  - Study how `max_depth` affects bias and variance
  - Test how different train/test split sizes affect generalization

## Repository Contents

```text
.
├── DecisionTree_BreastCancer.ipynb   # Main notebook with model training, evaluation, and plots
├── index.html                        # Rendered notebook output for GitHub Pages
└── README.md                         # Project documentation
```

## Dataset

The notebook uses the **Wisconsin Diagnostic Breast Cancer** dataset format, loaded from `wdbc.data`.

Each observation includes:

- An ID column
- A diagnosis label
- 30 numerical features describing cell nuclei characteristics

Feature groups include mean, standard error, and worst-value measurements for:

- Radius
- Texture
- Perimeter
- Area
- Smoothness
- Compactness
- Concavity
- Concave points
- Symmetry
- Fractal dimension

## Methodology

### 1. Data Loading and Preprocessing

The dataset is loaded with `pandas`, assigned explicit column names, and split into:

- `X`: numeric predictor features
- `y`: binary diagnosis target

The diagnosis values are mapped as:

```python
{'B': 0, 'M': 1}
```

### 2. Exploratory Visualization

The notebook includes histogram visualizations for selected features such as:

- `radius_mean`
- `texture_mean`

These plots help show distributional differences between benign and malignant cases.

### 3. Gini Decision Tree

A default decision tree using the Gini criterion is trained and evaluated.

**Observed performance:**

| Class | Precision | Recall | F1-score |
|---|---:|---:|---:|
| Benign | 0.97 | 0.95 | 0.96 |
| Malignant | 0.90 | 0.94 | 0.92 |

Overall accuracy: **94%**

The Gini tree provided the stronger overall precision-recall balance.

### 4. Entropy Decision Tree

A second decision tree is trained using the entropy criterion.

**Observed performance:**

| Class | Precision | Recall | F1-score |
|---|---:|---:|---:|
| Benign | 0.97 | 0.90 | 0.94 |
| Malignant | 0.84 | 0.95 | 0.89 |

Overall accuracy: **92%**

The entropy model produced slightly higher malignant recall but lower malignant precision, meaning it caught more malignant cases while increasing false positives.

### 5. Tree Depth Tuning

The notebook evaluates multiple `max_depth` values to study model complexity.

| max_depth | Accuracy | Precision | Recall | F1-score |
|---:|---:|---:|---:|---:|
| 3 | 0.9404 | 0.9175 | 0.9082 | 0.9128 |
| 5 | 0.9263 | 0.8667 | 0.9286 | 0.8966 |
| 7 | 0.9193 | 0.8378 | 0.9490 | 0.8900 |

Key finding:

- `max_depth=3` gives the best accuracy and F1-score.
- `max_depth=5` improves malignant recall and is used as a balanced default.
- `max_depth=7` maximizes recall but increases false positives.

### 6. Train/Test Split Experiment

Using `max_depth=5`, the notebook tests different training-set sizes.

| Train % | Train Samples | Test Samples | Train Accuracy | Test Accuracy |
|---:|---:|---:|---:|---:|
| 20% | 113 | 456 | 1.0000 | 0.8969 |
| 30% | 170 | 399 | 1.0000 | 0.9098 |
| 40% | 227 | 342 | 1.0000 | 0.9298 |
| 50% | 284 | 285 | 0.9859 | 0.9263 |
| 60% | 341 | 228 | 0.9912 | 0.9605 |
| 70% | 398 | 171 | 0.9925 | 0.9532 |
| 80% | 455 | 114 | 0.9934 | 0.9474 |

Best observed split: **60% train / 40% test**

Test accuracy at this split: **96.05%**

## Key Results

- The **Gini** criterion achieved the best overall accuracy in the initial model comparison.
- The **Entropy** criterion improved malignant recall but reduced precision.
- Shallower trees reduced overfitting and gave stronger generalization.
- `max_depth=5` was selected as a practical trade-off between recall and precision.
- A **60/40 train/test split** produced the highest test accuracy in the split experiment.

## Technologies Used

- Python
- pandas
- NumPy
- Matplotlib
- scikit-learn
- Jupyter Notebook
- GitHub Pages

## How to Run

1. Clone the repository:

```bash
git clone https://github.com/frankstop/DecisionTree_BreastCancer.git
cd DecisionTree_BreastCancer
```

2. Install dependencies:

```bash
pip install pandas numpy matplotlib scikit-learn jupyter
```

3. Add the dataset file if it is not already present:

```text
wdbc.data
```

4. Launch Jupyter Notebook:

```bash
jupyter notebook DecisionTree_BreastCancer.ipynb
```

5. Run all cells from top to bottom.

## GitHub Pages

The rendered notebook is available through GitHub Pages:

```text
https://frankstop.github.io/DecisionTree_BreastCancer/
```

## Future Improvements

Potential next steps include:

- Add k-fold cross-validation
- Add cost-complexity pruning
- Evaluate ROC AUC and confusion matrices
- Add feature importance visualizations
- Compare against Random Forest and Gradient Boosting models
- Package the workflow into reusable Python scripts

## License

No license file is currently included. Add a license if you intend others to reuse, modify, or distribute this project.
