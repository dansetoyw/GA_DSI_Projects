# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 2: Ames Housing Data and Kaggle Challenge

### Problem Statement

Real Sky Estate Development has been developing residential areas around Ames and is looking to procure and develop new housing in the area.

Previous housing developments were not returning favourable profits due to the recent pandemic and political tensions. It also caused a rise in the costs of living and building materials over the years.

Facing a forecasted recession in the upcoming year, Real Sky senior management team has reached out to our data science team to pinpoint factors that will direct towards revamping the company's focus structure to improve the attractiveness and sales price of new housing developments.

What core features should we focus on to increase the sale price of homes for our next development project?

### Datasets

#### Data Source
Source: Ames, Iowa Assessor's Office 

* [`train.csv`](./data/train.csv): Data set contains information from the Ames Assessor's Office used in computing assessed values for individual residential properties sold in Ames, IA from 2006 to 2010.

#### Data Dictionary

[AmesHousing_Data Dictionary](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt)

### Key Analysis

##### Comparing Linear , Ridge & Lasso Regression model with null model


|                       | Null Model | Linear Regression Model | Ridge Regression | Lasso Regression |
|-|-|-|-|-|
| Train R-squared score | -          | 0.88816                 | 0.88816          | 0.88816          |
| Train RMSE            | -          | 26256                   | 26256            | 26256            |
| Test R-squared score  | 0.0        | 0.86899                 | 0.86901          | 0.86898          |
| Test RMSE             | 79277      | 29765                   | 29763            | 29766            |

- For train dataset, all the regression  models gave same R2 score and RMSE.
- For the test dataset, Ridge Regression gave the highest R2 score, which is much higher than our baseline model whereby it uses the mean of the house's sale price as prediction. 
- Ridge regression also gave the lowest RMSE. 
- With these, the best estimator is Ridge Regression model and this will lead to better prediction to the property's sale price. 
- 89% of the variability in sale price can be explained by the selected features in our model. 

### Conclusion and recommendation:

- Ridge Regression model has acheived 89% R2 score. Relatively high accuracy in prediction of sale price with the selected features.
- Top 3 core features that impacts saleprice are ground living area, overall quality and total basement area. 

With this, we would like to recommend the following:
- Invest on the land and properties in north-west of Ames such as Northridge, Stone Brook and Northridge Heights
- Prioritise budget allocation on these core features to increase sale price. e.g. Building houses with dimensions above the median for the core features

|                    |    Median    |
|-|-|
|Ground Living Area  | 1444 sq.ft.  |
|Overall Quality     | Score 6      |
|Total Basement Area | 994 sq. ft.  |

- Channel additional budget for marketing on these core features to attract buyers once the properties built are ready for sale.
