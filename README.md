# Mushroom Classification: Edible or Poisonous?

Mission 1: Build a Simple Machine Learning Model.

## Project Overview

This project predicts whether a mushroom is **edible** or **poisonous** from its physical features (cap shape, odor, gill size, spore print colour, habitat and so on). I compare two beginner-friendly models:

- **Decision Tree**
- **K-Nearest Neighbors (KNN, k = 5)**

**Why it is useful:** wild mushroom poisoning is a real safety risk, and many edible and poisonous species look alike. The project also shows that different mistakes have different costs. Predicting "edible" for a poisonous mushroom is far more dangerous than the reverse, so the confusion matrix matters as much as accuracy.

## Dataset

UCI Mushroom dataset: https://archive.ics.uci.edu/dataset/73/mushroom

- 8,124 mushrooms, 22 categorical features, target `class` (`e` = edible, `p` = poisonous)
- The notebook downloads the data automatically from the UCI repository, so there is nothing to download by hand.

## What the Notebook Does

1. **The idea:** what the model predicts and why it is useful
2. **Data preparation:** loads the data, checks for missing values, and prepares features and target
   - Missing values are marked with `?` and appear only in `stalk-root` (about 30% of rows). They are kept as their own `missing` category rather than dropped.
   - Features are one-hot encoded. The target is `poisonous = 1`, `edible = 0`.
   - 80/20 stratified train/test split with a fixed random seed (42).
3. **Model building:** Decision Tree and KNN (k = 5)
4. **Evaluation:** test accuracy, a confusion matrix for each model, a classification report, 5-fold cross-validation, and the Decision Tree's top features
5. **Conclusion:** which model performed better and what I learned

## Setup Instructions

**Option A: Google Colab (easiest)**
1. Upload `mushroom_classification.ipynb` to https://colab.research.google.com
2. Choose **Runtime > Run all**

**Option B: Run locally**
```bash
git clone <your-repo-link>
cd <your-repo-folder>
python -m venv venv
source venv/bin/activate        # on Windows: venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook mushroom_classification.ipynb
```
Then choose **Kernel > Restart & Run All**. An internet connection is needed the first time to download the dataset.

## Results

> Fill this table in with the numbers from your own run (the notebook prints them).

| Model | Test accuracy | Poisonous predicted as edible | Edible predicted as poisonous | 5-fold CV mean accuracy |
|---|---|---|---|---|
| Decision Tree | _fill in_ | _fill in_ | _fill in_ | _fill in_ |
| KNN (k = 5) | _fill in_ | _fill in_ | _fill in_ | _fill in_ |

The confusion matrices are shown in the notebook.

## Conclusion

> Update this after running the notebook.

- **Better model:** _write which model scored higher and by how much, using your results above._
- **Key takeaway on errors:** the most important number is how many poisonous mushrooms were predicted as edible, not just overall accuracy.
- **What I learned:** one-hot encoding is needed for categorical data, treating missing values as a category kept about 30% of the rows, and a Decision Tree shows which features drive its decisions (for example odor), while KNN does not.
- **Caveat:** this dataset is very clean, so near-perfect scores do not mean the model is safe for real foraging. Never rely on a model alone to decide whether to eat a wild mushroom.

## Repository Structure

```
mushroom_classification.ipynb   # main notebook
requirements.txt                # dependencies
README.md                       # this file
```
