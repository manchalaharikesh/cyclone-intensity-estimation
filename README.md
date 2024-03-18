# Cylone_Detection_Intensity_Estimation

Developing a Convolutional Neural Network (CNN) method for estimating cyclone intensity using infrared band satellite images sourced from the INSAT-3D satellite.

## Dataset

The dataset consists of the images of various cyclones (of 30-minute intervals) of the Indian peninsula and its cyclone intensities estimated at every 6hr interval. The collection is of IR images that are suitable for collecting images of cyclones even at night. The missing cyclone intensity values are imputed by time-series data analysis.  The dataset is collected from the Meteorological and oceanographic Satellite data archive center (MOSDAC) of ISRO. The dataset consists of 17112 images. 

Visit MOSDAC at: https://www.mosdac.gov.in/


## Methodology

The approach is divided into 3 parts:

i.   Detect the cyclone from the satellite image using the YOLOv5 object detection model.

ii.  Extract the Region of interest (ROI) from the detected cyclone.

iii.  Trained various architectures like VGG16, VGG19, ResNet50 with various FCL setups like 128×1, 128×64×1, 128×64×32×1.

iv.  Achieved best result for VGG16-128×64×1 model.

v.  This architecture is further used with Neural Architecture Search (NAS) to find optimal FCL setup. Among the suggested FCL setups by NAS we achieved best performance for VGG16-128×128×1. 

<img src="https://github.com/manchalaharikesh/cyclone-intensity-estimation/blob/main/Cyclone-Intensity-Estimation-Backend/static/Methodology_Cyclone_Intensity_Estimation.png?raw=true">

## Results

After training the model in a transfer learning (TL) and NAS + TL sense we have achieved below results:

**Results of VGG-16-128×64×1**
1. Mean Absolute Error(MAE): 7.51
2. Root Mean Absolute Error(RMSE): 9.63
3. R2 Score: 0.92

**Results of VGG-16-128×128×1**
1. Mean Absolute Error(MAE): 6.77
2. Root Mean Absolute Error(RMSE): 8.88
3. R2 Score: 0.945

## Further Scope
A fusion model approach can be used with BT / Microwave and IR images as both produce distinct features of cyclone.
