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
## Data Description

- Each image can have multiple labels
- There are 17 possible tags: agriculture, artisinal_mine, bare_ground, blooming, blow_down, clear, cloudy, conventional_mine, cultivation, habitation, haze, partly_cloudy, primary, road, selective_logging, slash_burn, water

## Authors

* **Brunilda S.**
