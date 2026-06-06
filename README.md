# 🏠 Boston House Price Prediction

Predicts Boston housing prices using XGBoost. Trained on the classic sklearn Boston Housing dataset.

## 📦 Dependencies

```bash
pip install numpy pandas matplotlib seaborn scikit-learn xgboost
```

## 📁 Structure

```
house-price-prediction/
├── house_price_prediction.ipynb
└── README.md
```

## 🗂️ Dataset

506 samples, 13 features. All from Boston-area neighborhoods.

| Feature | Description |
|---|---|
| CRIM | Crime rate per capita |
| ZN | Residential land zoned for 25k+ sq. ft. lots |
| INDUS | Non-retail business acres per town |
| CHAS | Bounds Charles River? (1 = yes) |
| NOX | Nitric oxide concentration |
| RM | Avg rooms per dwelling |
| AGE | Owner-occupied units built before 1940 |
| DIS | Distance to Boston employment centers |
| RAD | Highway accessibility index |
| TAX | Property tax rate per $10,000 |
| PTRATIO | Pupil-teacher ratio |
| B | Racial composition index |
| LSTAT | % lower-status population |
| **MEDV** | **Median home value in $1,000s — this is the target** |

## ⚙️ Pipeline

1. **Load data** — pulled from sklearn, dropped into a DataFrame
2. **EDA** — checked shape, nulls, and summary stats
3. **Correlation heatmap** — spotted which features matter most
4. **Train/test split** — 80/20, `random_state=2`
5. **Train XGBoost** — default hyperparameters
6. **Evaluate** — R² and MAE on both splits

## 📊 Results

| Split | R² | MAE |
|---|---|---|
| Train | 0.9733 | 1.145 |
| Test | 0.9116 | 1.992 |

~91% variance explained on unseen data. Average error of about $1,992.

## 🚀 Usage

```bash
jupyter notebook house_price_prediction.ipynb
```

## ⚠️ Note

This dataset is deprecated in newer sklearn versions due to ethical concerns around the `B` feature. If you hit an error, load it manually from the [UCI ML Repository](https://archive.ics.uci.edu/ml/machine-learning-databases/housing/) or swap in the California Housing dataset instead.
