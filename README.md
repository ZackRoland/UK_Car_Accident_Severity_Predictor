# UK Car Crash Severity Predictor
## Introduction:
This project explores machine learning approaches to predicting the severity of car crashes in the United Kingdom using a large-scale accident dataset. Road safety is a critical public concern, and by analyzing key factors such as road type, weather, speed limits, and time of day, we aim to uncover patterns that contribute to different crash outcomes. Our objective is to build a robust predictive model that can classify crash severity levels, offering insights into which features play the most significant role in accident outcomes.

Throughout the milestones, we follow a structured ML pipeline that starts with dataset exploration and preprocessing, then moves into feature engineering and visualization, and finally applies supervised and unsupervised learning models to evaluate performance. Through documenting each stage of this process, we provide our reasoning and methodology for tackling a real-world predictive modeling problem.
## Milestone 1:
#### In this milestone we indentfied an adequate data set for our goal we drafted an Abstract to layout our plans for building our model
[Milestone 1](milestone_1.md)

## Milestone 2:
#### In this milestone we first did data exploration which entailed detailed descriptions of the features in the data set and identification of our target feature. To further understand the relationships of our data we constructed some inital plots and correlation matrices. Finally we discussed and executed inital preprocessing plan.
[Milestone 2 File](milestone_2.md)<br>
[Corresponding Code](milestone_2.ipynb)


## Milestone 3:
#### In this milestone, we finished any major preprocessing of our data. We then trained our first supervised learning model through Naieve Bayes and evaulated its preformance. Finally we compared our training and test error to determine if we was overfitting and discussed next steps.
[Milestone 3 File](milestone_3.md)<br>
[Corresponding Code](milestone_3.ipynb)



## Final Milestone:
#### 1-3 Summary of Final Milestone
[Final Milestone File](final_milestone.md)<br>
[Corresponding Code](final_milestone.ipynb)

## Final Report
### Dataset:
[Link to dataset](https://www.kaggle.com/datasets/daveianhickey/2000-16-traffic-flow-england-scotland-wales?resource=download&select=accidents_2005_to_2007.cs)!
### Variables: 
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
### Intro:
Road traffic injuries are one of the leading public-health concerns in the UK, therefore we chose this as our topic of interest so that we could develop a model that could potentially have a significant positive impact on preventing tragedy from occurring. Subsequently, we built a machine learning model that can predict accident severity using the 2005–2014 data of the England–Scotland–Wales road collisions dataset. The reasoning behind predicting on accident severity is that if we were able to deduce the severity of an accident based on a number of different features, this would allow the optimal delegation of emergency resources. This could not only provide life saving measures but also provide cost effective solutions. For our implementation we ended up running Naive Bayes as a supervised learning approach and PCA for unsupervised learning. Naive Bayes was used to directly predict the accident severity using our labeled data while our PCA told us the underlying structure of our data and understood patterns in our features that correlate toward accident severity. Through the combination of both approaches we got a holistic story of our data and valuable insight into how to optimize our accident severity prediction.
### Methods:
 Our initial dataset had over a million datapoints with 33 features so our first step was to get a comprehensive understanding of each feature of our dataset. This involved constantly going back and forth between the notebooks and the original documentation to find the definitions of each feature. The next step was to understand how our features interacted with each other especially with our target column (Accident Severity). To do this we decided to create a correlation matrix represented by to see which features would be the most helpful to predict Accident Severity.
<img width="1746" height="1542" alt="Untitled" src="https://github.com/user-attachments/assets/23b388ba-20e2-431e-837d-e1e37aeb1c3d" />

  Some interesting things to notice just from a quick initial glance is that most of the boxes on the matrix are grey in the sense that most things have very little correlation with each other. The factors that most influence Accident Severity which is what we are most interested in are;Number of Casualties, Speed Limit, Urban or Rural Area, Junction Control, Daylight and Police Presence. Seems the features with the most solid coloring like Junction_Control_No_Junction and Junction_Control_Uncontrolled could be very similar and possibly duplicate which makes sense just off the name alone so one of those could be dropped. We decided to dive deeper and created a correlation matrix  just on the numerical columns. 
<img width="673" height="555" alt="image" src="https://github.com/user-attachments/assets/c0663964-5e58-46ca-ab54-005c785388d2" />

  We can see that out of most of the Numeric columns the one that is going to be the most helpful is number of vehicles because out of all the other columns excluding Accident Severity itself it has the highest coefficient. Something else that is also interesting is that Urban_or_Rural_Area is closely correlated to Speed Limit. Now let's move into some categorical data. 
<img width="673" height="555" alt="image" src="https://github.com/user-attachments/assets/c0663964-5e58-46ca-ab54-005c785388d2" />

Looking at the graph we can see that the most accidents had an accident severity of 3 at a Giveaway/uncontrolled junction. We can also see that when there is an authorized personal present there was the least amount of accidents. We can also conclude that the least frequently occurring severity type is 1. Some more important things to note is how some of our data is distributed. 
<img width="904" height="574" alt="image" src="https://github.com/user-attachments/assets/3eb3b24d-0284-48f0-a23f-1e080b622973" />

The most accidents happened when there was little to no wind only to be followed by rain present. We can also conclude that when the weather conditions get severer the number of accidents tends to decline. 
<img width="926" height="620" alt="image" src="https://github.com/user-attachments/assets/47f4e371-982c-47a2-a241-ac64d078577b" /> 

The most accidents happen when the road is dry only to be followed by wet/damp roads. We can also see that the amount of dry accidents exceeds the amount of the sum of all other conditions.
- Preprocessing steps:
  - The first step of preprocessing our data is to go through each column and do an initial filtering out of any columns that seem unappealing for modeling based on our feature and variable descriptions.
    - This step got rid of columns such as `Accident_Index`,`Location_Easting_OSGR`,`Location_Northing_OSGR`,`Date`,`LSOA_of_Accident_Location`,`Local_Authority_(District)`,`Local_Authority_(Highway)`,`1st_Road_Number`,`Longitude`,`Latitude`,`1st_Road_Class`,`Road_Type`,`Police_Force`,`Junction_Detail`,`2nd_Road_Class`,`2nd_Road_Number` which are largely unique categorical variables that would provide little to no value in predicting accident severity. [Corresponding Code](milestone_2.ipynb)
  - Next we do a deep dive into each of our remaining variables and see if they (1) have NaN values and (2) are in an undesirable format. [Corresponding Code](milestone_2.ipynb)
  - If NaN values are present, we have to figure out what these NaN values mean in the context of our data. If the NaN indicates a missing value, then we have to find what is represented by it and encode that. For example, 'Junction_Control' had over 40% of its value, and we realized that NaN in this case just meant there was no special junction, and so we replaced all NaN for ‘Junction Control’ with ‘No junction’. If the quantity of the NaN in relation to the amount of total data present is sufficiently small enough, then we can just drop all rows that contain NaN values for that feature. An example of this was with our 'Pedestrian_Crossing-Human_Control'column, which we found to have 17 NaN values.
  - To make sure that the scale of our features wasn’t affecting the model, we standardized all of our numerical values and to handle our categorical data, we one-hot encoded them to allow our models to interpret our categorical features.
  - Since our 'Time' column was in an undesirable format (Hour:Minute) we split the values just to represent the hour to make it easier for whatever categorial analysis we decide to do with that [Corresponding Code](milestone_2.ipynb)

- Model 1: Naive Bayes:
  - For our supervised model, we implemented a Naive Bayes classifier to predict accident severity . After one-hot-encoding our categorical features, we used the preprocessed data above and trained our model on a 80/20 test-train split. Since we had numerical values, we ran it through a Gaussian Naive Bayes which doesn’t require standardization of our numerical features (but we did it anyway for good measure). This provided us with a good baseline of a computationally efficient and easily interpretable model. Though we had reasonable accuracy, it was unable to capture a lot of the complexities of the data and as such highlighted the importance of our next unsupervised learning model PCA.
- Model 2: PCA + KMeans:
  - Our second model was using PCA first to compress our dimensions to 2 dimensions and then used KMeans to try to find clusters and learn about different subsets of our data. Our preprocessed data had 10+ features, which would’ve taken longer to run KMeans on and would’ve made visualizing these clusters basically impossible. By using PCA to compress it down to 2 principal components, we were able to speed up the KMeans and actually plot the clusters that we found.
### Results: 
<ins>Naive Bayes:</ins>
  - For our Gaussian Naive Bayes Model we had a training test error of 0.652 and a testing error of 0.650.
Naive Bayes Training Report <br>
	<img width="430" height="192" alt="image" src="https://github.com/user-attachments/assets/4903b2e5-6f63-4702-bc70-6b037855e032" />
	<br>
Naive Testing Report <br>
	<img width="434" height="137" alt="image" src="https://github.com/user-attachments/assets/8939a515-acd5-4749-9946-0d538196b4e7" />
	<br>
  - With the relatively lower accuracy and very close testing and training error, we felt like our model was underfitting. Varying our hyperparameter like the variance smoothing rate showed us that increasing our smoothing rate allowed use to incrementally get better accuracies.
<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/fcacf9ac-e79d-4c61-b46c-e4ac05461ca2" />
<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/1be80902-a884-43ca-b1df-f843708c8ecc" />

<ins>PCA:</ins>
Using PCA with KMeans, we observed that inertia decreased steadily as K increased, showing tighter clusters, with minimal differences between train and test sets beyond K=10. 

<img width="500" height="500" alt="Image" src="https://github.com/user-attachments/assets/7904e396-a4c6-410b-a7d3-62f12e48eda6" />

Silhouette scores generally ranged from 0.45–0.55, except for a sharp dip at K=6 and K=7 (down to 0.39), indicating reduced cluster separation in those cases. The near-identical curves for train and test demonstrate that our results are reproducible and consistent across datasets.

<img width="500" height="500" alt="Image" src="https://github.com/user-attachments/assets/65b49e6e-a02d-414c-a7f9-6a3857765682" />

### Discussion: 

When we first began this project we didn’t have much of an idea of what we wanted to do and were having a hard time trying to find a dataset that met the requirements. We eventually settled on traffic accidents and tried to predict their severity. Looking back at it now we all believe we should have spent more time trying to find a dataset that would have excited us more as it would have made us be more creative in the models that we have to choose. When we decided to explore further into our numeric and categorical data we noticed for the numerical data that most of the data was weakly correlated with the target column. For our categorical data we noticed that there was a massive skew in our dataset favoring one type of value more than another .When it came time to  preprocess our data we were initially surprised by how much of our data was uncorrelated with itself so the only logical explanation was to find the ones that would help us achieve our goals and get rid of the rest. Looking back at it now we were thinking rather than get rid of a lot of features we could have applied some sort of transformation function and see if that made some of our data more associated with itself. It could have also improved our accuracy. When it came time to choose our first model we decided to go with Naive Bayes  because we weren’t really ready for decision trees yet by the time our milestone was due.  KNN gave us the best accuracy but it was computationally exhaustive and Naive Bayes is insanely fast in comparison. Without any discretization it gives us similar results as a KNN so we stuck with it. When it came to the final model we decided to go with PCA + K means Clustering. We decided to go with PCA because we wanted to see if we could decrease the dimensionality of models to reach the goal of making better and faster predictions. We combined this with K-means Clustering because we thought it would be the best at trying to predict Accident Severity given our dimensionally reduced data. Overall we believe that this project meets all the requirements,  however we do wish we could have done things differently to make this a more fruitful venture. 

### Conclusion: 
  For Naive Bayes, some ways that we can improve it is by conducting hyperparameter tuning specifically on our alpha and var_smoothing. We can also drop more features. Another way that we can improve is by building our own Naive Bayes model from scratch that uses both numerical and categorical data as we realized that there isn't a Naive Bayes model in Scikit Learn that cause handle both. We could have also just discretized our numerical values and ran a categorical Naive Bayes which would’ve gotten a much better overall accuracy. Analyzing our classification report, we see that we are getting the good accuracy for accident severity 3, but low and very low accuracies for accident severity 2 and 1. Taking a look at our data, around 85% of our data was accident severity 3 which could be a cause of the low accuracies for accident severity 2 and 1. This means we could improve it by using SMOTE or ADASYN oversampling to get more data for accident severity 2 and 1 and improve its accuracy and the accuracy of the whole model.
  For PCA + KMeans, through this project, we saw that classification was not appropriate for our dataset. Even with scaling, the features we had did not separate well enough to support a supervised model. When we tried PCA + K-Means, the low accuracy showed that this pipeline also was not a good fit. One possible reason is that the dataset itself was not well-suited for a classification task; instead of clustering patterns, the problem should have been designed to capture clear cause-and-effect relationships.
### Future Changes:
If we could do this differently, we would redesign our approach around other unsupervised methods. In particular, we would look at:
- **Hierarchical Clustering:** This would let us explore the nested structure of the data and visualize how points group together at different levels. It avoids the rigid assumptions of K-Means and gives us more flexibility in choosing the number of clusters. It would have allowed us to possibly get clusters that made more sense by allowing us to isolate the outliers as their own clusters, rather than being a part of a cluster that didn’t feel like it made sense.
- **Spectral Clustering:** This method uses graph similarity and eigenvectors of the Laplacian to detect clusters that are not linearly separable. It would be especially useful if our data has a complex structure that K-Means could not capture.
By focusing on these alternatives, we could take better advantage of the features we have. Instead of forcing classification, our group would treat the problem as one of exploratory clustering, supported by evaluation metrics like silhouette score and Davies–Bouldin index.
Overall, this project showed us that method choice has to align with the dataset. In the future, we would place more emphasis on clustering methods like Hierarchical and Spectral Clustering, which are better suited to our data than classification or PCA + K-Means.

### Statement of Collaboration:
- Zack Roland: Leader/Coder/Writer/Researcher: Data preprocessing and picking out features. A lot of writing throughout various parts of all the milestones.  Testing for model 2.
- Sri Talari: Coder/Writer: Secured the initial data set. Some of the preprocessing and data exploration as well as worked on the final report.
- Gui Yang: Lead Dev/Coder/Writer: Organized the readme’s for the various milestones. Helped with preprocessing of the data and coded most of the initial versions of the models and their plots/graphs. Wrote and contributed to the writeups pertaining to the preprocessing and models.
- Hyungjun Doh: Project Manager/Coder/Writer: Facilitated team progress through organization and helped with any set up issues the team faced. Wrote


