Capstone Project: Can severness of an air crash be predicted? 

General Assembly - DSI: 03/22/22 - 06/13/22
Author: Chenhao (Andy) Xu 

*** The Reasons ***
Why do I want to explore this problem? 
Air travel by statistics is considered one of the safest transportion nowadays. However, people often treat air crashes as the most terrible accident among all types of accidents. Why? Air crash may lead to high fatality rate than all other accidents, like railroad, bus, personal vehicle. Although a lot of airplane accidents did not happen in air, air crash still draw the public attention over the world. The question is if we are able to find out any similarities among the past accidents in order to prevent future airplane accidents. 

*** Problem Statement *** 
As an airplane fan, it is both my personal and public attention about the air travel safety. Although air travel is one of the safest transportation nowadays, the risk still exist, especially the high injury and mortality rate when single accident occurred. In order to help publics to understand more about the plane crashes, this study utilizes the features of aircraft type and age, operator, flight phase, crash site and time in the historical airplane crash records and explores the severeness of crash, whether there is survivor or not. 

*** Dataset used ***
https://www.kaggle.com/datasets/abeperez/historical-plane-crash-data
(Originally, I planned to use NTSB official data. After downloading the data, I noticed the NTSB data contains not only crashes but all other reported emergency during flights. The NTSB data also contains a lot of missing values and a lot of features that would not help the model. Instead, I decided to use the dataset from Kaggle. )

1. Data Cleaning
The main goal of data cleaning is to prepare the dataset ready for analysis. There were four major subdatasets:

A. df_crash (26438 rows): The dataset includes all crash records.
B. df_comm (11354 rows): The dataset only includes the crashes of commercial flights.
C. df_jet (8936 rows): The dataset only includes the crashes of commercial flights in jet age (after 1952).
D. df_time (13566 rows): The dataset only includes the crashes with the records of crash time HH:MM.

new columns created:
A. aircraft age when crash happened
B. total people on board
C. total fatality (not include the ground fatality)
D. number of survivors

columns removed due to useless or missing values
Registration, Schedule, MSN, Flight no., YOM, Crew on board, Crew fatalities, Pax on board, PAX fatalities, Other fatalities, Total fatalities

Reduce column features: 
A. Flight type: I reduced the flight type into three major categories, Commercial, General Aviation, Military
B. Aircraft type: Instead of aircraft type, I simplified to aircraft manufacturer

2. EDA
raw data graphs were made
A. All Flight Crashes Since 1918
B. Commercial Flight Crashes Since 1918
C. Number of Deaths in Air Crahses Since 1918
D. Crashes by flight phase
E. Crashes by crash location
F. Crashes by crash cause
G. Crashes by Airlines in Jet Era
H. Crashes by type of aircraft manufacturer
I. Number of crashes during a day ( 0 - 24h)

3. Analysis
Methods: 
SimpleImputer, OneHotEncoder, StandardScaler

3.0. Baseline Model
Accuracy: 63.7%

3.1. Logistic Regression
Accuracy: 66.7%
Precision: 70.2%
Major issue: FP (there were 31% of the FPs)

3.2. KNN
Accuracy: 65.8%
Precision: 66.3%
Major issue: FP (there were 42% of the FPs)

3.3. Random Forest
Accuracy: 73.4%
Precision: 74.3%
Major issue: FP (there were 27% of the FPs)

3.4. Neural Network
Val_accuracy: 66%

*** NLP ***
Accuracy: 94.8%
Precision: 96.4%

4. Conclusion and Recommandation

A. Air travel is still one of the safest transportation. 
B. It is difficult summarizing the major causes of one accident. 
C. It is difficult predicting whether an air crash would lead to no survivors. 