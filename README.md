# Bank Marketing Campaign Analysis

I used 11,162 bank marketing records to predict term deposit subscriptions, estimate call duration, and group customers with similar profiles.

[Final report](project_report.pdf) · [Notebook](notebooks/Bank_Marketing_Campaign_Analysis.ipynb) · [Dataset on Kaggle](https://www.kaggle.com/datasets/janiobachmann/bank-marketing-dataset)

## Methods and results

I compared the classification and regression models using five-fold cross-validation, then evaluated each selected model on a separate 20% test set.

| Task | Method | Result |
| --- | --- | --- |
| Classification | I compared Logistic Regression and a Decision Tree. | Logistic Regression achieved 69.5% test accuracy and an F1 score of 0.651. It identified 60% of subscribers. |
| Regression | I compared Linear Regression and Random Forest. | The tuned Random Forest had the lowest validation error. Its test RMSE was 349 seconds and its R² was 0.015, so call duration was difficult to predict. |
| Clustering | I used K-Means with age, account balance, and previous contacts. | The elbow plot suggested four groups. The silhouette score was 0.44, indicating some overlap. |

## How to run

1. Clone the repository and open a terminal in the project folder.
2. Make sure the dataset is at `data/bank.csv`.
3. On Windows, run these commands to create an environment, install the packages, and open the notebook.

```powershell
py -m venv .venv
.\.venv\Scripts\python.exe -m pip install pandas numpy scikit-learn matplotlib seaborn jupyter
.\.venv\Scripts\jupyter.exe notebook notebooks/Bank_Marketing_Campaign_Analysis.ipynb
```

4. Select **Run All**. The notebook saves `data/bank_clean.csv` and generates the model results and plots.
