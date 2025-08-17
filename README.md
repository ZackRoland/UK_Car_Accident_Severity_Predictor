# CSE151A-Project-1
## Dataset
[Link to dataset](https://www.kaggle.com/datasets/daveianhickey/2000-16-traffic-flow-england-scotland-wales?resource=download&select=accidents_2005_to_2007.cs)!
## Environment setup requirements (2 points) 

## Data Exploration (4 points)

1. How many observations does your dataset have?
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
    Note: For image data you can still describe your data by the number of classes, size of images, are sizes uniform? Do they need to be cropped? normalized? etc.

## Data Plots (4 points)

1. Plot your data with various types of charts like bar charts, pie charts, scatter plots etc. and clearly explain the plots.
    For image data, you will need to plot your example classes.

## Data preprocessing

1. How will you preprocess your data? Handle data imbalance if needed. You should only explain (do not perform pre-processing as that is in MS3) this in your README.md file and link your Jupyter notebook to it. All code and  Jupyter notebooks have be uploaded to your repo. (3 points)
