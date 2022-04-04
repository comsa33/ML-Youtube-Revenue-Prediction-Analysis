# [ML] YOUTUBE revenue prediction
youtube daily estimated revenue prediction with machine-learning (tree-based models)
- [프로젝트 레포트(Kaggle Notebook)](https://www.kaggle.com/code/kristhecoder/youtube-revenue-prediction)
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

## DATA
> **Data from** : YouTube Studio (Youtuber - PoohinKorea)
**Data Size** : (1132, 16) / (rows, columns)
> 
> 
> 
> | Date | Column Names | Describtion |
> | --- | --- | --- |
> | 1 | Average_views_per_viewer | 시청자 당 평균 시청 횟수 |
> | 2 | Unique_viewers | 순 시청자 수 |
> | 3 | Click_rate | 노출 시 클릭율 |
> | 4 | Impressions | 노출 횟수 |
> | 5 | Comments | 댓글 수 |
> | 6 | Shares | 공유 수 |
> | 7 | Dislikes | 싫어요 수 |
> | 8 | Likes | 좋아요 수 |
> | 9 | Average_viewed | 평균 시청율 |
> | 10 | Videos_published | 새 영상 수 |
> | 11 | Subscribers | 구독자 순 증가수 |
> | 12 | Views | 조회수 |
> | 13 | Watch_hours | 하루 누적 총 시청시간 |
> | 14 | Average_view_sec | 영상 평균 시청시간(초) |
> | 15 | Revenue | 일일 예상 수익 |

## Correlations with Target
![0f9c0d99-0a70-4721-b64b-4a72d6435d37](https://user-images.githubusercontent.com/61719257/161459774-a916b9f4-b5df-4c98-a132-f4b14bad557e.png)

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

## Hyperparameters Tuning
- Log Transformed RF Regressor

|DATA     |MAE        |RMSE       |R2       |
|-----------|-----------|-----------|---------|
|TRAIN SET|$2.227|$4.509|0.967|
|TEST SET|$19.38|$22.19|0.20|

- Log Transformed XGB Regressor

|DATA     |MAE        |RMSE       |R2       |
|-----------|-----------|-----------|---------|
|TRAIN SET|$0.39|$0.66|0.999|
|TEST SET|$10.01|$13.33|0.71|

- Log Transformed LGBM Regressor

|DATA     |MAE        |RMSE       |R2       |
|-----------|-----------|-----------|---------|
|TRAIN SET|$1.03|$5.01|0.959|
|TEST SET|$17.01|$21.05|0.28|

- Tuned Combined Models (XGB:0.8, RF:0.1, LGBM:0.1)

|DATA     |MAE        |RMSE       |R2       |
|-----------|-----------|-----------|---------|
|TEST SET|$9.59|$12.94|0.728|

## Top Coef & Feature Importance
![42eb0d20-63d9-4161-9baa-b7c8e8ce6620](https://user-images.githubusercontent.com/61719257/161458455-14005702-a4e6-48db-aaf7-d1bb68771f93.png)
![e122b839-40ca-4449-b4b8-6da19c5ebba9](https://user-images.githubusercontent.com/61719257/161458501-4fff1f51-2a50-4909-b783-e92fef77c424.png)

## Top Permutation Importance
![Screen Shot 2022-04-04 at 10 23 20](https://user-images.githubusercontent.com/61719257/161459226-a1fe6cb9-b14c-4891-84b9-55a3cf204e96.png)

## Results
- SHAP values

![b96ee0d1-604d-401d-8974-bd55dcd16d20](https://user-images.githubusercontent.com/61719257/161459326-7b3d5eb9-91c7-44ae-89c9-c7a0c18b7784.png)
![f74a4ceb-05b8-44f4-9982-9146a830d949](https://user-images.githubusercontent.com/61719257/161459359-12ef7a67-15ff-41e2-b7af-e6121d19fb0f.png)
![Screen Shot 2022-04-04 at 10 26 35](https://user-images.githubusercontent.com/61719257/161459464-61b2d8d7-9f7f-414d-ac9e-77f2e216ea8b.png)



