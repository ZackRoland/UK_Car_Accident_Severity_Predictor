# CSE151A-Project-1

1. Finish major preprocessing, this includes scaling and/or transforming your data, imputing your data, encoding your data, feature expansion, Feature expansion (example is taking features and generating new features by transforming via polynomial, log multiplication of features).  (10 points)

	Naive Bayes Training Report <br>
	<img width="430" height="192" alt="image" src="https://github.com/user-attachments/assets/4903b2e5-6f63-4702-bc70-6b037855e032" />
	<br>
	Naive Testing Report <br>
	<img width="434" height="137" alt="image" src="https://github.com/user-attachments/assets/8939a515-acd5-4749-9946-0d538196b4e7" />
	<br>


2. Train your first model and analyze your model's performance. Evaluate your model and compare training vs. test error. (10 points)
When it comes down to accuracy both training and testing models came out to be around 65%. This is also the case for Precision, Recall, and F1 score for each accident severity class. In addition, both models also agree that the scores for class 1 and 2 are both significantly lower than class. This could be due to the fact that we have a lot more samples that have a class 3 accident severity. This also means we are experiencing a lot more false positives for class 1 and 2 and missing a lot of true positives. 
	
3. Answer the questions: Where does your model fit in the fitting graph? (Build at least one model with different hyperparameters and check for over/underfitting, pick the best model). What are the next models you are thinking of and why? (5 points)
Our model lies on the left end of the fitting curve, based on how low our train and test accuracy were underfitting our model. Increasing our learning rate results in a slightly better fit as represented by the var_smotting vs accuracy graph, so our best model is the one with the var smoothing of 1e-6. The next model we were thinking of is a KNN because upon initial testing with a KNN provided better accuracy report, the only downside is that it takes a very long time to run, even on SDSC.

<img width="1109" height="660" alt="image" src="https://github.com/user-attachments/assets/fcacf9ac-e79d-4c61-b46c-e4ac05461ca2" />
<img width="1092" height="679" alt="image" src="https://github.com/user-attachments/assets/1be80902-a884-43ca-b1df-f843708c8ecc" />


4. Conclusion section: What is the conclusion of your 1st model? What can be done to possibly improve it? (5 points)
		Our Naive Bayes has an accuracy of around 65% which means it does better than guessing what the accident severity is. Some ways that we can improve it is by conducting hyperparameter tuning specifically on our alpha and var_smoothing.  We can also drop more features. Another way that we can improve is by building our own Naive Bayes model from scratch that uses both numerical and categorical data. Analyzing our classification report, we see that we are getting the good accuracy for accident severity 3, but low and very low accuracies for accident severity 2 and 1. Taking a look at our data, around 85% of our data was accident severity 3 which could be a cause of the low accuracies for accident severity 2 and 1. This means we could improve it by using SMOTE or ADASYN oversampling to get more data for accident severity 2 and 1 and improve its accuracy and the accuracy of the whole model.

5. Update your README.md to include your new work and updates you have all added. Make sure to upload all code and notebooks. Provide links in your README.md <br>
	All our code and images/graphs are from here with the Milestone 3 things closer to the bottom. https://github.com/ZackRoland/CSE151A-Project-1/blob/Milestone3/model_exploration_sdsc.ipynb

## Dataset
[Link to dataset](https://www.kaggle.com/datasets/daveianhickey/2000-16-traffic-flow-england-scotland-wales?resource=download&select=accidents_2005_to_2007.cs)!
## Environment setup requirements (2 points) 
Download the dataset above and extract it into the project folder. All the dataset files should automatically be in a folder name "archive", either copy or move that folder in the project folder.
## Data Exploration (4 points)

1. How many observations does your dataset have? <br>
    We have 33 Observations which we split into 32 Features and 1 Targeting Class.
2. Describe all columns in your dataset their scales and data distributions. Describe the categorical and continuous variables in your dataset. Describe your target column and if you are using images plot some example classes of the images.

| **Feature**                            | **Short Description**                                                                                     | **Variable**                                                                                      |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| **Accident_Index**                     | A unique identifier for each accident. Dropped because it is just an ID and is not informative for modeling | Categorical: 200XXXXXXXXXX or 201XXXXXXXXXX                                                        |
| **Location_Easting_OGSR**               | X/Y coords in the UK national grid reference system. Dropped because difficult to interpret without mapping/spatial analysis | Numerical: 3 - 559570                                                                             |
| **Location_Northing_OGSR**              | X/Y coords in the UK national grid reference system.                                                       | Categorical: 156110 - 656390                                                                       |
| **Longitude**                          | Local British geographical coordinates x-value.                                                           | Numerical: -3.954836 - 0.300802                                                                   |
| **Latitude**                           | Local British coordinates y-value.                                                                         | Numerical: 51.28906 - 55.80083                                                                     |
| **Police_Force**                       | Code representing which police force                                                                        | Categorical: 1 - 98                                                                                 |
| **Number_of_Vehicles**                 | Integer count of the number of vehicles involved in the accident                                          | Continuous: 1 - 28                                                                                 |
| **Number_of_Casualties**               | Integer count of people injured or killed in the accident                                                  | Continuous: 1 - 68                                                                                 |
| **Date**                               | Date (MM/DD/YYYY)                                                                                         | Categorical: 1/1/2005 - 12/31/2007, None                                                           |
| **Date_of_Week**                       | Date of Week that the accident occurred on                                                                 | Categorical: 1 - 7, None                                                                           |
| **Time**                               | Time that the accident occurred on (UTC+0)                                                                 | Categorical: 00:00 - 23:59                                                                          |
| **Local_Authority_(District)**         | Local government authority area codes.                                                                     | Numerical: 1 - 941                                                                                 |
| **Local_Authority_(Highway)**          | Local highway authority area codes.                                                                        | Categorical: EXXXXXXXX                                                                              |
| **1st_Road_Class**                     | Road classification                                                                                       | Numerical: -1 - 6                                                                                 |
| **1st_Road_Number**                    | Road number                                                                                               | Numerical: -1 - 9999                                                                                |
| **Road_Type**                          | Description of the road type                                                                                | Categorical: 'Single carriageway', 'Dual carriageway', 'One way street', 'Roundabout', 'Slip road', 'Unknown', None |
| **Speed_Limit**                        | Legal Speed limit at the location of the accident                                                          | Numerical: 10 - 70                                                                                 |
| **Junction_Detail**                    | Type of Junction                                                                                          | Null                                                                                               |
| **Junction_Control**                   | Type of traffic control present at the junction where the accident occurred                               | Categorical: 'Automatic traffic signal', 'Giveway or uncontrolled', 'Stop Sign', 'Authorised person', None |
| **2nd_Road_Class**                     | Road classification for an intersection                                                                   | Numerical: -1 - 6                                                                                 |
| **2nd_Road_Number**                    | Road number for an intersection                                                                            | Numerical: -1 - 9999                                                                                |
| **Pedestrian_Crossing-Human_Control**  | Identifies whether a pedestrian crossing was controlled by a human near the accident site                | Categorical: 'None within 50 metres', 'Control by other authorised person', 'Control by school crossing patrol', None |
| **Pedestrian_Crossing-Physical_Facilities** | Identifies the pedestrian crossing infrastructure near the site of the accident                       | Categorical: 'Zebra crossing', 'Pedestrian phase at traffic signal junction', 'No physical crossing within 50 meters', 'Central refuge', 'Non-junction pedestrian crossing', 'Footbridge or subway', None |
| **Light_Conditions**                   | Describes the lighting conditions at the scene of the accident                                            | Categorical: 'Daylight: Street light present', 'Darkness: Street lights present and lit', 'Darkness: Street lighting unknown', 'Darkness: Street lights present but unlit', 'Darkness: No street lighting', None |
| **Weather_Conditions**                 | Describes the weather conditions at the scene of the accident                                            | Categorical: 'Raining without high winds', 'Fine without high winds', 'Unknown', 'Snowing without high winds', 'Other', 'Fine with high winds', 'Raining with high winds', 'Fog or mist', 'Snowing with high winds', None |
| **Road_Surface_Conditions**            | Describes the road-surface conditions at the scene of the accident                                         | Categorical: 'Wet/Damp', 'Dry', 'Frost/Ice', 'Snow', 'Flood (Over 3cm of water)', None             |
| **Special_Conditions_at_Site**        | Any kind of conditions at the time of the accident                                                        | Categorical: 'Oil or diesel', 'Roadworks', 'Auto traffic signal partly defective', 'Road surface defective', 'Auto traffic signal out', 'Permanent sign or marking defective or obscured', 'Mud', None |
| **Carriageway_Hazards**                | Was there anything in the carriageway at the accident?                                                     | Categorical: None, pedestrian, Other object, Dislodged vehicle load in carriageway, Involvement with previous accident, Any animal (except a ridden horse) |
| **Urban_or_Rural_Area**                | Whether the Accident Occurred in an Urban or Rural Area                                                   | Categorical: 1 for Urban, 2 for Rural                                                               |
| **Did_Police_Officer_Attend_Scene_of_Accident** | Whether a Police Officer went to the accident or not                                                      | Categorical: Yes, No, Null                                                                          |
| **LSOA_of_Accident**                  | Lower Layer Super Output Area of Accident, basically the area of the accident                            | Categorical: E100XXXX indicating the Area Code of the accident                                    |
| **Year**                               | Year of Accident                                                                                          | Categorical: 2005, 2006, 2007, 2009, 2010, 2011, 2012, 2013, 2014                                |

### Targeting Class

| **Feature**                            | **Short Description**                                                                                     | **Variable**                                                                                      |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| **Accident_Severity**                  | Describes the severity level of the accident                                                                 | Categorical: 1 = Fatal, 2 = Serious, 3 = Slight                                                    |

3. Do you have missing and duplicate values in your dataset?
    Note: For image data you can still describe your data by the number of classes, size of images, are sizes uniform? Do they need to be cropped? normalized? etc. <br>
    We do have missing values that we plan to preprocess and we have a single duplicated row.
## Data Plots (4 points)

1. Plot your data with various types of charts like bar charts, pie charts, scatter plots etc. and clearly explain the plots.
    For image data, you will need to plot your example classes.

Correlation Matrix of Accident Data: Some interesting things to notice just from a quick inital glance is that most of the boxes on the matrix are grey in the sense that most things have very little correlation with each other. The factors that most influence Accident Severity which is what were most interested in are;Number of Casualties, Speed Limit, Urban or Rural Area, Junction Control, Daylight and Police Presence. Seems the features with the most solid coloring like Junction_Control_No_Junction and Junction_Control_Uncontrolled could be very similar and possibly duplicate which makes sense just off the name alone so one of those could be dropped.
<img width="1746" height="1542" alt="Untitled" src="https://github.com/user-attachments/assets/23b388ba-20e2-431e-837d-e1e37aeb1c3d" />

Accident Severity By Junction Type: This graph is separated by Junction control type and each bar is separated by Accident Severity. Looking at the graph we can see that the most accidents had an accident severity of 3 at a Giveaway/uncontrolled junction. We can also see that when there is an authorized personal present there was the least amount of accidents. We can also conclude that the least frequently occurring severity type is 1. 

<img width="629" height="468" alt="image" src="https://github.com/user-attachments/assets/eafa35de-56f1-4db5-b3ad-78a6dad18344" />

Numeric Columns only heatmap: Since we are trying to predict Accident Severity we can see that out of most of the Numeric columns the one that is going to be the most helpful is number of vehicles because out of all the other columns excluding Accident Severity itself it has the highest coefficient. Something else that is also interesting is that Urban_or_Rural_Area is closely correlated to Speed Limit. 

<img width="673" height="555" alt="image" src="https://github.com/user-attachments/assets/c0663964-5e58-46ca-ab54-005c785388d2" />

Accident Severity Histogram: Looking at the graph we can see that a class 3 Accident Severity is the most frequently occurring followed by Class 2 and 1 with class 3 being more than the sum of class 1 and 2. 

<img width="583" height="427" alt="image" src="https://github.com/user-attachments/assets/e5c67024-ee23-4054-98de-7422a1f7885c" />

Number_of_Vehicles vs. Number_of_Casualities: Looking at this graph we can see that we have a lot of outliers and most of our data is 5000 or below. However the most interesting part is that the majority of accidents happen when there are 2 or less vehicles involved with only 2 or less people dying.

<img width="557" height="427" alt="image" src="https://github.com/user-attachments/assets/7cd8111f-491f-4309-b2e9-238c847d5dc2" />

Accident Severity by Light Conditions: We can first notice that most accidents happen where there is daylight still present and it is classified as a class 3 accident severity. We can also see that relative to other light conditions when there is darkness present there have been a lot fewer accidents. 

<img width="625" height="467" alt="image" src="https://github.com/user-attachments/assets/ca22bc40-4efd-482b-9d36-1a734396217c" />

Longitude Vs. Latitude: As expected the output for this graph does look like the UK which confirms that are dataset is indeed real. 

<img width="537" height="401" alt="image" src="https://github.com/user-attachments/assets/5d34751e-98da-4ae9-8e39-f031443b2099" />

Weather Conditions Bar: The most amount of accidents happened when there was little to no wind only to be followed by rain present. We can also conclude that when the weather conditions get severer the number of accidents tends to decline. 

<img width="904" height="574" alt="image" src="https://github.com/user-attachments/assets/3eb3b24d-0284-48f0-a23f-1e080b622973" />

Road Conditions Bar: The most amount of accidents happen when the road is dry only to be followed by wet/damp roads. We can also see that the amount of dry accidents exceeds the amount of the sum of all other conditions. 

<img width="926" height="620" alt="image" src="https://github.com/user-attachments/assets/47f4e371-982c-47a2-a241-ac64d078577b" />


## Data preprocessing

Q: How will you preprocess your data? Handle data imbalance if needed. You should only explain (do not perform pre-processing as that is in MS3) this in your README.md file and link your Jupyter notebook to it. All code and  Jupyter notebooks have be uploaded to your repo. (3 points)
1. First step of preprocessing our data is to go through each column and do an inital filtering out of any columns
   that seem unappealing for modeling based our feature and variable descriptions.
   - This step got rid of columns such as 'Accident_Index','Location_Easting_OSGR', 'Location_Northing_OSGR','Date','LSOA_of_Accident_Location', 'Local_Authority_(District)','Local_Authority_(Highway)', '1st_Road_Number','Longitude','Latitude', '1st_Road_Class', 'Road_Type',
    'Police_Force','Junction_Detail','2nd_Road_Class', and '2nd_Road_Number' which are largely unique categorical variables that would provide little to no value
in predicting accident severity.                           
3. Next we do a deep dive into each of our remaining variables and see if they (1) have NaN values and (2) are in an undesirable format
4. If NaN values are present, we have to figure out what these NaN values mean in the context of our data. If the NaN indicates a missing value, then we have to find what is    represented by it and encode that. For example, 'Junction_Control' had over 40% of its value. If the quantity of the NaN in relation to the amount of total data present      is sufficently small enough then we can just drop all rows that contain NaN values for that feature. An example of thisis our 'Pedestrian_Crossing-Human_Control' column      which we found to have 17 NaN values.
5. Since our 'Time' column was in an undesireable format (Hour:Minute) we split the values just to represent the hour to make it easier for whatever categorial analysis we decide to do with that
6. For future steps we will normalize our data if we find that it is necessary for the model we decide we train. Also we need to go through our correlation matrix in depth and see what we need to drop if the features are essentially duplicates and provide no meaningful info
   
