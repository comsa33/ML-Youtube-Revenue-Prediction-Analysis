# [ML] YOUTUBE revenue prediction
youtube daily estimated revenue prediction with machine-learning (tree-based models)
- [프로젝트 레포트](https://github.com/comsa33/ML-Youtube-Revenue-Prediction-Analysis/blob/main/Ai07_S2_Project2_%EC%9D%B4%EB%A3%A8%EC%98%A4.ipynb)
- [데이터셋](https://www.kaggle.com/datasets/kristhecoder/youtube-revenue-data-20182021)

## Introduction
> - Interest & Inspirations
> - Is it possible to predict a daily revenue of a certain youtuber with his/her channel's daily view, subscribers gained, average viewed duration, etc...?
> - Which factor is most related with increasing daily Revenue?
> - How much can Total Views of videos devote to actual Monetizing?
> - If one has more videos posted on his/her channel, would she/he happen to earn more?

## Environment & Skills
> - Google Colab | Jupyter Notebook
> - Python 3.9
>   - Library for EDA & Data Preprocessing : Pandas, Numpy
>   - Library for Statistics & Data Analysis : Scipy.stats, sklearn
>   - Library for Data Visualization : Matplotlib, Seaborn
>   - Library for ML Models : sklearn, xgboost, lightgbm
>   - Library for Model Interpretation & Insight : eli5, pdpbox, shap
> - Jamobi
> - STATISTIC TEST
>     -Anova (one-way) Test, Variance Inflation Factor Check, F-Statistics(p-value)
> - ML MODELS
>    - Linear-Models : LinearRegression, Ridge, Lasso, ElasticNet
>   - Tree-based-Models : RandomForest Regressor, Xgboost Regressor, Lightgbm Regressor
>   - TransformedTargetRegressor : Log Transformed Linear Regression
> - Miri Canvas
> - OBS

## Evaluations
|MODELS     |MAE        |RMSE       |R2       |
|-----------|-----------|-----------|---------|
|Log Transforemed Linear|$717.946   |$1319.06     |-2815.379|
|Log Transformed Ridge|$132.31|$177.49|-49.99|
|Log Transformed Lasso|$99.75|$135.58|-28.75|
|Log Transformed ElasticNet|$91.33|$121.91|-23.06|
|Log Transformed RF Regressor|$17.13|$20.68|0.307|
|Log Transformed XGB Regressor|$10.28|$13.51|0.704|
|Log Transformed LGBM Regressor|$16.93|$21.10|0.279|
|Combined Model(XGB:0.8, RF:0.1, LGBM:0.1)|$10.11|$13.15|0.72|
