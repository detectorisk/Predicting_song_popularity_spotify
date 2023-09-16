# song_popularity_spotify
Through the following analysis we aimed at building a robust model through supervised learning to predict popularity of songs in a spotify dataset. We began by analyzing the train dataset, which had 438 rows and 15 columns, of which 1 was a random Id variable, 3 were string variables relating to song name, artist, and genre, and all other variables were numeric. Popularity variable among this was our variable of interest, and hence taken as our dependant variable in the model. We used primarily three supervised methods for our analysis, namely:
- Linear regression
- Random Forest regression
- Support vector regression

## Transformations
Now, since we can see from above that the top genre column has 86 categories within it, this will pose a problem when we encode the categorical column with one-hot encoding, to be then considered in our regression model. This is because, one-hot encoding will make as many additional columns in our explanatory dataset as there will be unique categories of top genre. This might lead to overfitting. Hence we decided to club together various genres into broader self-defined categories. However, we also acknowledge a drawback to this approach, which is that while these categories work fine in fitting the regression on the training dataset, when the testing dataset is employed, it will also have to be grouped into the same categories. This makes such a grouping less robust and adaptable to new training sets. Despite this, we believe genre to be a good predictor of popularity, and hence an important indicator to retain. 

## Regression analysis

For actual regression analysis we have taken 3 regression methods as mentioned before. We started with a simple linear regression model, and then moved to Support Vector regression, and finally employed a random forest regression model. We found that the random forest model gave us the best results in Kaggle, with a public score of 8.19. 

To begin with, we started by splitting the training data into testing and training data to validate our findings before fitting the regression model to the whole training data. We split the training data into 70:30 as training and validationing data. 

We first explored a linear regression model that models a plain linear relationship between the explanatory and the predicted variable. The purpose was to have a baseline model. Then we moved to a Support Vector Regression model. This was done to account for the possible non-linear nature of the relationship. Using a "rbf" kernel, and C=1, we employed a SVR model. In the validation data, it seems to have done slightly worse than the linear regression predictions. Finally, we employed a random forest model. Random forest regression is an ensemble learning, which combines multiple decision trees for its output. The idea behind choosing it was to limit the possible overfitness of the data and also to reduce its sensitivity to noise. As we saw earlier, there are unaddressed outliers in the data which might be affecting the performance of the regression analysis. 

