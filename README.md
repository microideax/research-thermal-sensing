# Thermal Sensing Data Classification Research
  This repository contains the collected dataset, and developed source code in the research "Human-Sensing: Low Resolution Thermal Array Sensor Data Classification of Location-Based Postures", which will be published at the 5th International Conference on Distributed, Ambient and Pervasive Interactions. 

## Abstract
  Ambient Assisted Living (AAL) applications aim to allow elderly, sick and disabled people to stay safely at home while collaboratively assisted by their family, friends and medical staff. AAL, recently empowered by the Internet of Things, introduces a new healthcare connectivity paradigm that interconnects mobile apps and sensors allowing constant monitoring of the patient. Preserving privacy in the course of recognition of postures and classification of activities is one of the challenges for human-sensing and a critical factor of user acceptance, so there is a demand for solutions that do not require real live imaging in AAL.
  This paper addresses this challenge through the usage of a low resolution ther- mal sensor and machine learning techniques, discussing the feasibility of low cost and privacy protecting solutions. We evaluated decision tree models in two tasks of human-sensing, presence and posture recognition, using data of different days and volunteers. We also contribute by providing public domain datasets, collected in a bedroom and a bathroom, which are described in this paper.
  
## Keywords
Household Monitoring, Human-Sensing, Machine Learning, Privacy, Thermal Sensors, Low Resolution.

# Repository
## Code-Arduino
This program reads OMRON D6T-44L sensor data and sends it via serial port. 

## Code-Processing
This program communicates to the Arduino program, label each temperatures' matrix and persists it in a text file. This program also shows the temperatures on a 4x4 matrix layout. 

## Code-R
The program developed in R reads the labeled text files, that contains the raw temperatures' matrix data from OMRON D6T-44L, pre processes it extracting some features, and outputs text files in order to generate/validate machine learning models. 

## Dataset
Inside Dataset folder there are 8 folders from 7 different days of data collection. Each of these folders contains .csv files with the collected thermal data.

The structure of folder names is Data-{Room}-Day{#}, where {Room} can be Bathroom or Bedroom and {#} can be 1-7.

Within each data folder contains the respective .csv files with the sensor data. The structure of file names is {Room}-Day{#}-{Volunteer}-{Posture}.csv, where {Volunteer} can be A-E and {Posture} can be 1-16. Postures 1-8 were performed in the bedroom and postures 9-16 in the bathroom. The postures are:
1: Lying on the bed;
2: Sitting on the bed;
3: Lying on the bed using blanket;
4: Sitting on the floor;
5: Standing;
6: Lying on the floor;
7: Standing wearing winter clothes;
8: None (No volunteer in the sensor field of view);
9: Lying in the shower box;
10: Standing in the shower box;
11: Standing in front of the sink;
12: Standing in front of the toilet wearing winter clothes;
13: Standing in front of the toilet;
14: Sitting on the toilet wearing winter clothes;
15: Sitting on the toilet;
16: None (No volunteer in the sensor field of view);

The column headers of the .csv files are: TPTAT, T1, T2, ..., T16, CheckPEC, Delta t from last measure in Miliseconds and Time Stamp. 
TPTAT = Ambient temperature measured from the thermal sensor.
Tn = The sixteen sensor field of view temperatures.
CheckPEC = 
