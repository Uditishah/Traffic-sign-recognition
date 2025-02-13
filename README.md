# Image Processing Project
## Project Name: Traffic sign recognition method for intelligent vehicles
This project implements a new approach for traffic sign recognition, the image pre-processing approach is referenced from the paper ['Traffic sign recognition method for intelligent vehicles'](https://www.researchgate.net/publication/328418844_Traffic_sign_recognition_method_for_intelligent_vehicles), SVM classifiers and MLP classifiers are used to compare the performance.
## Proposed Method

<img width="823" alt="Screenshot 2024-07-08 at 11 32 53 PM" src="https://github.com/Uditishah/Traffic-sign-recognition/assets/157534932/06e42cbc-1fb5-4aec-b0d8-2c83701c6042">

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
<img width="830" alt="Screenshot 2024-07-08 at 11 33 14 PM" src="https://github.com/Uditishah/Traffic-sign-recognition/assets/157534932/2a2791ce-7097-4be4-a446-f6625c744a77">

From the result, we can see that log-polar transform improves the accuracy.

2.	HOG, LBP and Combining features

Then, we make comparison between different feature extraction. The tests are run on SVM classifiers with log-polar transformation step.
<img width="818" alt="Screenshot 2024-07-08 at 11 34 22 PM" src="https://github.com/Uditishah/Traffic-sign-recognition/assets/157534932/a9054abb-a7e5-48b2-9cc7-53e1088c620a">


From the result, we can see that by combining feature of HOG+LBP, we enhance the performance.

3.	SVM classifier vs. MLP classifier

The following tests are run on combining feature extraction with log-polar transformation.
<img width="823" alt="Screenshot 2024-07-08 at 11 35 07 PM" src="https://github.com/Uditishah/Traffic-sign-recognition/assets/157534932/803579e5-0f4c-417b-ada2-be09169da6e1">



From the results above we can see that, both two classifiers have good performance,

SVM have a better accuracy while MLP is faster in terms of recognition speed as well as the training speed.

In a word, the proposed method of have a good performance in terms of time and accuracy. It is feasible to implement in a simple, low-cost application.
