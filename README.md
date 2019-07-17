# Multi-label classification for Satellite Images

## Introduction
In this project we are going to build a `multi-label classification model`, where given a specific satellite image the model will associate all labels belonging to it. The labels associated to the satellite images describe differents atmospheric conditions and various classes of land cover/land use. 

There are `17 possible labels`: agriculture, artisinal_mine, bare_ground, blooming, blow_down, clear, cloudy, conventional_mine, cultivation, habitation, haze, partly_cloudy, primary, road, selective_logging, slash_burn, water.

### Data source and description
The dataset contains the list of labels and satellite images. Images have four bands of data: red, green, blue, and near infrared
The data comes from [Planet](https://www.planet.com/) and its Brazilian partner [SCCON](https://www.sccon.com.br/)
Data list:
-  train.csv             : contains the training file names and their labels, the labels are space-delimited
-  sample_submission.csv : contains the test set names and their labels
-  train-jpg.zip         : Train set images
-  test-jpg.zip          : Test set images

All details about this project can be found [here](https://brunildacity01.github.io/MyProjects/MultiLabel_ClassificationProject.html)
