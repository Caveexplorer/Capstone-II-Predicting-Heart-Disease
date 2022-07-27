# What are the Greatest Risk Factors for Heart Disease?

Cardiovascular diseases are the leading cause of death worldwide, accounting for about 18 million, or about 1 in 3 deaths yearly. Heart diseases are a subcategory of cardiovascular disease, and include things like coronary heart disease and heart failure. In our analysis of a heart disease data set we found that a portion of the electrocardiogram (ECG) called the ST segment was by far the most important feature for predicting heart disease. Specifically, an upward facing ST slope, combined with its position below the baseline, were the most important features for predicting heart disease.

![ST_slope](ST-segment-depression-upsloping-downsloping-horizontal.png)

# The Data

This is a composite data set of heart disease data that comes from the United States, Hungary, and Switzerland which we found on Kaggle. It consists of 918 patients with information across twelve features. Our dependent variable is heart disease (HD). This is the variable we'd like to predict. Some of the independent variables of this data set are a little less straightforward than others. Age and sex, for example, are self explanatory, while ST_Slope is a little less straightforward. All non self explanatory features are explained in the final project report document. 

https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction

In the raw_data folder you'll find a csv file called heart_data_raw.csv. This is the original combined data set taken from Kaggle. Each of the other .data files in that folder are the individual datasets which came from their respective hospitals around the world. They were found at this repository:

https://archive.ics.uci.edu/ml/machine-learning-databases/heart-disease/

The Data folder contains any version of the data we change. heart_data_cleaned.csv and heart_data_dropped_chol.csv are the clean versions of the data we made after our data wrangling. We tried two versions of this project: one with Switzerland's cholesterol values dropped and one with the median cholesterol value imputed. The preprocessed data will also be paired similarly. full_test.csv and full_train.csv, and no_swiss_test.csv and no_swiss_train.csv are the preprocessed versions of the data tables, ready for modeling.

# Modeling

There is a large variety of ML models available to use through scikit-learn's API. All have their strengths and weaknesses, and most will only work with certain kinds of data. Your data set, the nature of your data and the variable you're trying to predict, matters greatly for which ML model or models you should try and use. Thus, we feel it is appropriate to give a short justification for which models we will attempt to use for our data set and for our present goals.

Firstly, our problem is a supervised learning problem. We already know what we're trying to predict (heart disease yes or no) and have the appropriate labels for this target variable. Therefore, our problem is a supervised learning problem. Secondly, our problem is a problem of classification, since the variable we're trying to predict, the presence of heart disease, is a categorical variable (yes or no). We are not trying to predict something continuous like height or weight, which can be anything from a continuous range of numbers. Therefore, we select classification models. 

In the preprocessing stage of our capstone we OneHot encoded all our non-numeric variables specifically to prepare for using a Logistic Regression ML model, which is a derivative of the Linear Regression ML family adapted specifically for predicting categorical outcomes. We will also use a random forest of decision tree models, which is an ensemble method for classification. We feel decision trees are a good point of comparison to other ML models because they're simpler to explain. Both of these models are classification models, and so are suitable for our purposes.

# Packages/Libraries

- numpy 1.21.2
- pandas 1.3.3
- matplotlib 3.4.3
- seaborn 0.11.2
- scikit-learn 0.24.2