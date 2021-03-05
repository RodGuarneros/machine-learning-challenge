# Machine Learning  - Exoplanet Exploration

### By Rodrigo Guarneros

## Objective

This project aims to create machine learning models capable of classifying candidate exoplanets from the raw dataset built based on the NASA Kepler space telescope observations.

The machine learning model is looking to classify candidates exoplanets from the raw dataset. In other words, it aims to predict a category based on the following labels or strings: Confirm, false positive or candidate.

## Dataset

The Kepler Space Observatory is a NASA-build satellite that was launched in 2009. The telescope is dedicated to searching for exoplanets in star systems besides our own, with the ultimate goal of possibly finding other habitable planets besides our own. The original mission ended in 2013 due to mechanical failures, but the telescope has nevertheless been functional since 2014 on a "K2" extended mission.

The dataset is available at: https://www.kaggle.com/nasa/kepler-exoplanet-search-results.

![exoplanets.jpg](https://github.com/RodGuarneros/machine-learning-challenge/blob/main/Images/exoplanets.jpg)

## Main data process

1. [Preprocess the raw data](#Preprocessing)
2. [Tune the models](#Tune-Model-Parameters)
3. [Compare two or more models](#Evaluate-Model-Performance)

### Preprocess the Data

* Preprocess the dataset prior to fitting the model.
* Perform feature selection and remove unnecessary features.
* Use `MinMaxScaler` to scale the numerical data.
* Separate the data into training and testing data.

### Tune Model Parameters

* Use `GridSearch` to tune model parameters.
* Tune and compare at least two different classifiers.


## Analysis

Based on ten features (inputs), three labels (CONFIRMED, CANDIDATE AND FALSE POSITIVE) and also 6,991 observations, the next step was use supervise learning models so as to look for patterns based on exploratory data analysis.

![presentatonGuarneros.jpg](https://github.com/RodGuarneros/machine-learning-challenge/blob/main/Images/presentationGuarneros.png)

The main hypothesis is based on the analysis of the available data and the relevance of transit movements for the detection of planets, so it is reasonable to consider as key inputs (for more details about the meaning of the following variables, please visit the document "Notes and details" in this repository): koi_fpflag_ss, koi_fpflag_nt, koi_fpflag_co, koi_fpflag_ec.

![presentatonGuarneros.jpg](https://github.com/RodGuarneros/machine-learning-challenge/blob/main/Images/waystoGuarneros.jpg)

All the proposed models here consider transit variables as the most relevant, even above radial velocity (rad, in the database).

The main approach is incremental, I mean from the simplest to the most elaborate and complex model, with the following performance metrics, such as "Accuracy" defined as TP+TN/Total observations: 

- Logistic Regression Model presents an accuracy of .72 and a hyperparameter tunning of 0.79. The confusion matrix looks like this:

![LogisticGuarneros.jpg](https://github.com/RodGuarneros/machine-learning-challenge/blob/main/Images/LogisticGuarneros.png)

- Support Vector Model presents an accuracy of .79 and a hyperparameter tunning of 0.78. The confusion matrix looks like this:

![SVM.jpg](https://github.com/RodGuarneros/machine-learning-challenge/blob/main/Images/SVM.png)

- K Nearest Neighbor Model presents an accuracy of .82. The confusion matrix looks like this:

![KNNGuarneros.jpg](https://github.com/RodGuarneros/machine-learning-challenge/blob/main/Images/KNNGuarneros.png)

- Random Forest Model presents an accuracy of .82 and a hyperparameter tunning of 0.8159 Their confusion matrix looks like this:

![RFGuarneros.jpg](https://github.com/RodGuarneros/machine-learning-challenge/blob/main/Images/RFGuarneros.png)

- Deep Learning Neural Network Model presents an accuracy of .827 and a hyperparameter tunning of 0.78 with 10,000 epochs. 


## Conclusion

The best model to predict the class of the Kepler Object of Interest regarding new observations is the Neural Network Model following really near for Random Forest Model. 

If you need more details about this analysis, please visit the PDF document in this repository.


## Resources

* [Prepossing targets](https://scikit-learn.org/stable/modules/preprocessing_targets.html#preprocessing-targets)

* [Exoplanet Data Source](https://www.kaggle.com/nasa/kepler-exoplanet-search-results)

* [Scikit-Learn Tutorial Part 1](https://www.youtube.com/watch?v=4PXAztQtoTg)

* [Scikit-Learn Tutorial Part 2](https://www.youtube.com/watch?v=gK43gtGh49o&t=5858s)

* [Grid Search](https://scikit-learn.org/stable/modules/grid_search.html)

