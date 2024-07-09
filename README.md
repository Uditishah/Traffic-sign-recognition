# Image Processing Project
## Project Name: Traffic sign recognition method for intelligent vehicles
This project implements a new approach for traffic sign recognition, the image pre-processing approach is referenced from the paper ['Traffic sign recognition method for intelligent vehicles'](https://www.researchgate.net/publication/328418844_Traffic_sign_recognition_method_for_intelligent_vehicles), SVM classifiers and MLP classifiers are used to compare the performance.
## Proposed Method

<img width="826" alt="Screenshot 2024-07-08 at 11 15 08 PM" src="https://github.com/Uditishah/Traffic-sign-recognition/assets/157534932/afa65a2b-4624-4157-93c2-ebb2a1750271">


The process has three steps. 
1. Transform the image from the Cartesian coordinate system to the log-polar one with post-processing. 
2. Feature extraction, histogram of oriented gradients (HOG) and local binary pattern (LBP) are used to represent the image in the log-polar coordinate system. 
3. Classification using support vector machines (SVM) and multilayer perceptron (MLP) classifiers.

## Dataset
This project uses [German Traffic Sign Recognition Benchmark (GTSRB)](http://benchmark.ini.rub.de/?section=gtsrb&subsection=dataset#Overview) , which is a Large, lifelike traffic signs database that many people used to compare and illustrate the single-image, multi-class classification problem. Specifically, we used [GTSRB_Final_Training_Images dataset](http://benchmark.ini.rub.de/?section=gtsrb&subsection=dataset#Downloads), which has 39209 images of 43 classes in total. For simplicity, we split this dataset into 26465 of training data points, 2941 validation data points and 9803 testing data points.
The following part we run different experiments to compare different methods. Specifically, we compare the cartesian coordinate and log-polar transform, HOG, LBP and combining features, different classifiers in terms of accuracy and time. The experiments are done on a computer with 8th Gen Intel® Core™ i7-8650U 1.90GHz.

## Performance analysis
1.	Cartesian vs. Log-polar

First, we test the performance of cartesian and log-polar transform on combining features using the SVM classifiers.
<img width="829" alt="Screenshot 2024-07-08 at 11 19 03 PM" src="https://github.com/Uditishah/Traffic-sign-recognition/assets/157534932/ee46465e-91d6-423d-8580-fe94ced7cbfe">

From the result, we can see that log-polar transform improves the accuracy.

2.	HOG, LBP and Combining features

Then, we make comparison between different feature extraction. The tests are run on SVM classifiers with log-polar transformation step.
<img width="827" alt="Screenshot 2024-07-08 at 11 20 21 PM" src="https://github.com/Uditishah/Traffic-sign-recognition/assets/157534932/094df57e-c2ee-46f6-97a3-10ae7dc34dc1">
From the result, we can see that by combining feature of HOG+LBP, we enhance the performance.

3.	SVM classifier vs. MLP classifier

The following tests are run on combining feature extraction with log-polar transformation.
<img width="823" alt="Screenshot 2024-07-08 at 11 20 53 PM" src="https://github.com/Uditishah/Traffic-sign-recognition/assets/157534932/349ed715-2868-455d-aea9-a502b2230de0">
From the results above we can see that, both two classifiers have good performance,

SVM have a better accuracy while MLP is faster in terms of recognition speed as well as the training speed.

In a word, the proposed method of have a good performance in terms of time and accuracy. It is feasible to implement in a simple, low-cost application.
