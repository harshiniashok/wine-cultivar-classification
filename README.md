# Wine Cultivar Classification

Predicting which of three grape cultivars a wine comes from, using 13 chemical measurements (UCI Wine dataset, 178 samples).

Built as a college data science project following the data science life cycle: understand the problem, retrieve data, prepare and explore, train, evaluate.

## Results

| Model | 5-fold CV accuracy (train set) | Test accuracy (45 held-out wines) |
|---|---|---|
| Logistic regression (standardized) | 97.7% | 100% |
| Random forest | 98.5% | 100% |

The test set is small, so 100% should not be read as perfect performance on new data. The cross-validation numbers are the more stable estimate.

## What's in the notebook

- Data loading with `sklearn.datasets.load_wine` (no download needed)
- Data checks: missing values, class balance, summary statistics
- Correlation heatmap and pairplot by cultivar
- Stratified train/test split
- Model comparison with cross-validation, then evaluation with a classification report and confusion matrix
- Random forest feature importance

## Lessons learned

My first version of this project predicted `Alcohol` with linear regression and split the data sequentially. The dataset is sorted by class, so the test set contained almost only one cultivar and the R² came out at about -4.45. This version reframes the task as classification on the `Class` label and uses a shuffled, stratified split. The notebook documents both mistakes.

## Run it

```bash
git clone https://github.com/<harshiniashok>/wine-cultivar-classification.git
cd wine-cultivar-classification
pip install -r requirements.txt
jupyter notebook notebooks/wine_cultivar_classification.ipynb
```

Or open the notebook directly in Google Colab.

## Data

[UCI Machine Learning Repository: Wine](https://archive.ics.uci.edu/dataset/109/wine). Original data donated by Forina et al.
