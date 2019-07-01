# Multi-label Classification for satellite imagery

This project is about labeling satellite images chips with various atmospheric conditions and rare land cover/land use phenomena. This images are segments of a larger image of the Amazon Rainforest

## Data source and description

The dataset contains the list of labels and satellite images. Images have four bands of data: red, green, blue, and near infrared
The data comes from Planet (https://www.planet.com/) and its Brazilian partner SCCON (https://www.sccon.com.br/)
Data list:
- train.csv - a list of training file names and their labels, the labels are space-delimited
- tif-v2.tar.7z - tif files for the training/test set
- [train/test]-jpg[-additional].tar.7z - jpg files for the trainin/test set

```
Give examples
```
## Labels description

- Each image can have multiple labels
- There are 17 possible tags: agriculture, artisinal_mine, bare_ground, blooming, blow_down, clear, cloudy, conventional_mine, cultivation, habitation, haze, partly_cloudy, primary, road, selective_logging, slash_burn, water

# What is a Multi-Label Classification
TBD

# Expected Challenges
Large Dataset
The training data has over one million rows. I expect there will be challenges in dealing with the large dataset. Challenges may include running into memory errors and excessive processing times.

To combat the large size of the dataset, there are several techniques to try, including using smaller samples of the data for training and dimensionality reduction. I anticipate feature selection and engineering as well as model optimization will be important.

Imbalanced Dataset
The dataset is highly imbalanced, with only 6% of samples belonging to the target (insincere) class. I anticipate this will cause challenges with recall. Maximizing recall, or true positive rate, could be a difficulty here due to the small number of insincere samples. I anticipate resampling techniques and data augmentation could improve model performance.

# Metric to be used
Submissions will be evaluated based on their mean (F_{2}) score. The F score, commonly used in information retrieval, measures accuracy using the precision p and recall r. Precision is the ratio of true positives (tp) to all predicted positives (tp + fp). Recall is the ratio of true positives to all actual positives (tp + fn). The (F_{2}) score is given by

(1+β2)prβ2p+r  where  p=tptp+fp,  r=tptp+fn, β=2.
Note that the (F_{2}) score weights recall higher than precision. The mean (F_{2}) score is formed by averaging the individual (F_{2}) scores for each row in the test set.

Precision is the number of true positives divided by all positive predictions. Precision is also called Positive Predictive Value. It is a measure of a classifier’s exactness. Low precision indicates a high number of false positives.
Recall is the number of true positives divided by the number of positive values in the test data. Recall is also called Sensitivity or the True Positive Rate. It is a measure of a classifier’s completeness. Low recall indicates a high number of false negatives.

Precision is the number of true positives divided by all positive predictions. Precision is also called Positive Predictive Value. It is a measure of a classifier’s exactness. Low precision indicates a high number of false positives.
Recall is the number of true positives divided by the number of positive values in the test data. Recall is also called Sensitivity or the True Positive Rate. It is a measure of a classifier’s completeness. Low recall indicates a high number of false negatives.
F1-Score is the harmonic mean of precision and recall.
Support is the number of true results for each class.

Confusion Matrix: A breakdown of predictions into a table showing correct predictions (the diagonal) and the types of incorrect predictions made (what classes incorrect predictions were assigned).

# Handeling the Unbalanced data
TBD

# Baseline Models
Gor our analysis we will compare different classifiers and neural networks
## Classifiers
  - One versus Rest using Logistic Regression: A linear model for classification. They are fast to train and predict, scale well, and are easy to interpret, and are therefore a good choice for a baseline model
  - KNN
  - MLKNN
  - RainForest
  
# Baseline Test Set Results
**Classifiers**
- OnevsRestClassifier: 
- KNN       : 
- MLKNN     : 
- RainForest: 

**Neural Networks**
- CNN       : 
- MobileNet : 
- VGG16     : 

From this decrease in F2 score we can assume our models are not generalizing well to the unseen validation data. We definitely have a lot of room for improvement!

# How to improve the performance?
## options
There are various techniques involved in improving the performance of imbalanced datasets.

Re-sampling Dataset
To make our dataset balanced there are two ways to do so:

Under-sampling: Remove samples from over-represented classes ; use this if you have huge dataset
Over-sampling: Add more samples from under-represented classes; use this if you have small dataset

Feature Engineering

Add bias to classes overrepresented: Since classes are imbalanced, what about providing some bias to minority classes ? We can estimate class weights

## What was implemented
TBD
# Conclusion
TBD
