# Multi-label classification for Satellite Images

## Introduction
In this notebook we are going to build a multi-label classification model, where given a specific image the model will associate the labels belonging to it. Thus, each image can have multiple labels and there are 17 possible labels: agriculture, artisinal_mine, bare_ground, blooming, blow_down, clear, cloudy, conventional_mine, cultivation, habitation, haze, partly_cloudy, primary, road, selective_logging, slash_burn, water.

### Data source and description
In order to train our model we are going to use 
The dataset contains the list of labels and satellite images. Images have four bands of data: red, green, blue, and near infrared
The data comes from Planet (https://www.planet.com/) and its Brazilian partner SCCON (https://www.sccon.com.br/)
Data list:
- train.csv - a list of training file names and their labels, the labels are space-delimited
- [train/test]-jpg - jpg files for the training/test set

### What is a Multi-Label Classification
Multi-label classification is task of finding multiple key features from one specific satellite image.

## Challenges
- Images be classified into several classes, i.e. Multi-Label classfication
- Noisy images
- Large Dataset, the training data has over one million rows 
- Imbalanced Dataset

### Methodology 
-  Apply several approaches
  - Baseline Approach: Use scikit-learn Classifiers to build a multi-label model 
  - Second Approach: Use CNN and Transfer Learning neural networks to build a multi-label model 
  - Third Approach: Feature Engineer the predefined classes
-  Load a subset of data with 10000 samples and have a first overview of the labels distribution
-  Preprocess Data, e.g. preformat images for scikit-learn Classifiers, vectorize the labels, etc.
-  Select scikit-learn Classfiers that handle multi-label classification
-  Select the best metric for the project
-  Hyperparameter optimization and select the best paramter for each classifier 
-  Use the selected parameters and score each classfier
-  Select the classifier obtaining the best score
-  Score selected classifier using the test data set

### Metric to be used
**F2 Score**
When plotting the labels distribution we could observed that we have very unbalance. In this case one the most commonly use metrics is  the F2 score. The Fβ score, measures accuracy using the precision and recall. Precision is the ratio of true positives (tp) to all predicted positives (tp + fp). Recall is the ratio of true positives to all actual positives (tp + fn). The F2 score is given by (1+β2)prβ2p+r  where  p=tptp+fp,  r=tptp+fn, β=2. Note that the F2 score weights recall higher than precision.

**Confusion Matrix**
A breakdown of predictions into a table showing correct predictions (the diagonal) and the types of incorrect predictions made (what classes incorrect predictions were assigned).

## Overview of differents strategies
## Baseline approach
For the Baseline approach, we are going to proceed to a comparison analysis, based on the F2 score, among the following classifiers:
  - KNN Classifier
  - MLKNN Classifier
  - RandomForestClassifier
  - OneVsRestClassifier
  
## Second approach
For the second approach, we are going to proceed to a comparison analysis, based on the F2 score, among the following neural networks:
- CNN
- MobileNet
- VGG16

## Third approach
For the Third approach, we are going to proceed to a comparison analysis, based on the F2 score, among the the best classifier and the best neural network.

## Results
**Baseline Approach** 
Overall results
- KNN                   : 0.712568
- MLKNN                 : 0.747465
- RandomForestClassifier: 0.698658
- OnevsRestClassifier   : 0.681306

Results per Classes
Even if we obtained reasonables scores when analysing the results per label, without surprise all Classifiers missed to predict labels having under-sampled data, i.e. conventional_mine, selective_logging, blow_down, blooming, artisinal_mine

**Class KNN_F2  MLKNN_F2	RF_F2	OnevsRest_F2**
primary 0.962596	0.974540	0.984648	0.977333
clear	0.900151	0.900151	0.909475	0.901057
cloudy	0.639671	0.683140	0.575080	0.556274
haze	0.580357	0.562023	0.256776	0.339045
agriculture	0.340069	0.551331	0.225664	0.212685
partly_cloudy	0.279859	0.407035	0.206186	0.062298
road	0.139544	0.297704	0.098711	0.062138
water	0.135495	0.239018	0.007065	0.045956
cultivation	0.040323	0.135495	0.000000	0.039370
bare_ground	0.019455	0.040323	0.000000	0.011614
habitation	0.008503	0.034483	0.000000	0.003743
slash_burn	0.000000	0.019455	0.000000	0.000000
***conventional_mine	0.000000	0.000000	0.000000	0.000000
selective_logging	0.000000	0.000000	0.000000	0.000000
blow_down	0.000000	0.000000	0.000000	0.000000
blooming	0.000000	0.000000	0.000000	0.000000
artisinal_mine	0.000000	0.000000	0.000000	0.000000***

**Second Approach**
- CNN                   : 0.732413
- MobileNet             : 0.702046
- VGG16                 : 

**Third Approach**
Classifiers
- KNN                   : 0.774087
- MLKNN                 : 0.816947
- RandomForestClassifier: 0.814515
- OnevsRestClassifier   : 0.778788

Results per Classes
When analysing the results per label, all Classifiers were able to predict all labels

**Class	KNN_F2	MLKNN_F2	RF_F2	OnevsRest_F2**
primary	0.960843	0.973451	0.984508	0.975881
clear	0.896977	0.896977	0.914872	0.900551
weather_label	0.664444	0.734949	0.784028	0.648861
agriculture	0.328051	0.669029	0.541190	0.337408
road	0.116971	0.283803	0.066964	0.206831
land_over_label	0.085227	0.250162	0.057950	0.131764

Neural Networks
- CNN                   : 
- MobileNet             : 
- VGG16                 : 

## Conclusion
From this decrease in F2 score we can assume our models are not generalizing well to the unseen validation data. We definitely have a lot of room for improvement!
