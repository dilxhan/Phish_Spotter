# Phishing Website Detection by Machine Learning Techniques

## Objective
A phishing website is a popular social engineering technique that imitates reliable URLs and online sites. The goal of this research is to use the dataset produced to detect phishing websites to train machine learning models and deep neural networks. In order to create a dataset from which the necessary URL- and website content-based attributes may be extracted, both phishing and benign URLs of websites are collected. Each model's performance level is assessed and contrasted.

## Data Collection
The collection of phishing URLs comes from the open-source tool **PhishTank**. This site offers a collection of phishing URLs that are updated hourly in a variety of forms, including csv, json, etc. Visit https://www.phishtank.com/developer_info.php to obtain the data. To train the ML models, 5000 random phishing URLs are collected from this dataset.

The authentic URLs were extracted from the University of New Brunswick's open datasets at https://www.unb.ca/cic/datasets/url-2016.html. This dataset contains a collection of URLs that aren't malicious, spammy, phishing, or defacement. The benign url dataset is taken into consideration for this study out of all of these categories. To train the ML models, 5000 random genuine URLs are obtained from this dataset.

The above mentioned datasets are uploaded to the '[DataFiles](https://github.com/dilxhan/Phish_Spotter/tree/main/DataFiles)' folder of this repository.

## Feature Extraction
The below mentioned category of features are extracted from the URL data:

1.   Address Bar based Features <br>
          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In this category 9 features are extracted.
2.   Domain based Features<br>
          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In this category 4 features are extracted.
3.   HTML & Javascript based Features<br>
          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In this category 4 features are extracted.

*The details pertaining to these features are mentioned in the [URL Feature Extraction.ipynb.](https://github.com/dilxhan/Phish_Spotter/blob/main/URL%20Feature%20Extraction.ipynb)

So, all together 17 features are extracted from the 10,000 URL dataset and are stored in '[5.urldata.csv](https://github.com/dilxhan/Phish_Spotter/blob/main/DataFiles/5.urldata.csv)' file in the DataFiles folder.<br>


## Models & Training

The data is separated into 8000 training samples and 2000 testing samples before beginning the ML model training. This is an obvious supervised machine learning challenge based on the dataset. Classification and regression are the two main subtypes of supervised machine learning issues.

Due to the input URL being either legitimate (0) or phishing (1), this data set has a categorization issue. The supervised machine learning models (classification) taken into account in this research to train the dataset are:

* Decision Tree
* Random Forest
* Multilayer Perceptrons
* XGBoost
* Autoencoder Neural Network
* Support Vector Machines

All these models are trained on the dataset and evaluation of the model is done with the test dataset. The elaborate details of the models & its training are mentioned in [Phishing Website Detection_Models & Training.ipynb](https://github.com/dilxhan/Phish_Spotter/blob/main/Phishing%20Website%20Detection_Models%20%26%20Training.ipynb)

## End Results
From the obtained results of the above models, XGBoost Classifier has highest model performance of 86.4%. So the model is saved to the file '[XGBoostClassifier.pickle.dat](https://github.com/dilxhan/Phish_Spotter/blob/main/XGBoostClassifier.pickle.dat)'

