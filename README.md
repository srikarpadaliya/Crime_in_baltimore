# Dataset: [Crime In Baltimore](https://www.kaggle.com/datasets/sohier/crime-in-baltimore)

## About Dataset
This dataset provides information about the crimes commited in Baltimore city. This dataset is accessible from the link provided above. The dataset covers crimes commited in the city between the years 2012-2017.

This project consists of 6 parts:
1. Introduction
2. Data Cleaning
3. Data visualization
4. Data Preprocessing
5. Modeling
6. Inference
7. Conclusion

# 1. Introduction

This data consists of total 15 columns and 2,76,529 observations.

## Attribute description:
* **CrimeDate:** Date of committed crime
* **CrimeTime:** Time of Committed crime
* **CrimeCode:** A unique code assigned to crime based of crime type and weapon used
* **Location:** Location of commited crime
* **Inside/Outside:** Flag shows whether crime was commited inside the house or not
* **Weapon:** Description of weapon used in crime
* **Post:** Code of nearby police station
* **District:** District of location of committed crime
* **Neighbourhood:** Neighborhood of place of incident
* **Longitude:** longitude of location of committed crime
* **Latitude:** latitude of location of committed crime
* **Location 1:** tuple of consisting longitude and latitude
* **Premise:** Premise
* **Total incidents:** No. of incident in a crime

# 2. Data Cleaning

There are **1,80,952 cells** which are **null** in the weapons column. This makes around **65% rows** of the whole data.
Dropping this rows can lead to loss of much significant data, which can reduce the quality of the dataset.

To deal with this null values, we can look at some other attributes, which can be related to this attribute. Like, *Crime type* can help to determine which type of weapon is used in a perticular crime.

## Crime type details:

* **Arson:** the criminal act of deliberately setting fire to property.
* **Assault by threat:** a threat or attempt to inflict offensive physical contact or bodily harm on a person that puts the person in immediate danger of or in apprehension
* **Auto theft:** the criminal act of stealing or attempting to steal a motor vehicle
* **Burglary:** llegal entry of a building with intent to commit a crime, especially theft.
* **Larceny:** theft of personal property
* **Rape:** to force someone to have sex when they are unwilling, using violence or threatening behaviour
* **Robbery:** the action of taking property unlawfully from a person or place by force or threat of force

It is observed that where ever weapon values are not available, the associated crime types are mostly:
1. Robbery
2. Theft
3. Arson
4. Larceny

In these types of crime most of the time there are not any weapon involved in crime.

The blank cells in weapon cells doesn't indicate that the data is missing, but we can conclude that *there could no weapons involved in the crime at the first place*. So, we can fill all this blank cells with the "No weapon" value.

In the **Total Incident** columns all the entries are filled with value 1. Which does not provide any value to the dataset. So, there is no loss in dataset quality in dropping this columns.

![This is the Screenshot of the Total Crime Incidents happened in Baltimore](https://github.com/PicantaData/Crime-in-Baltimore/blob/main/Images/Screenshot_Total_Incidents.png)

After this, the **Location 1** columns contains the tuple of ***(Longitude, Latitude)*** as values. There are also separate columns for Longitude and Latitude as well. So, dropping the Location 1 column also does not affect the dataset quality.

We will drop those rows with null column entries.
After making these changes, We got **2,63,118 rows** with **13 columns**.

# 3. Data Visualization
We have tried to made inference from this data by analysing the yearly, monthly, weekly, daily and hourly of the crime committed in Balimore. You can find scatter plots, pie charts and bar graphs of these inferences in the **Jupyter Notebook**.  

# 4. Pre-Processing
We have dropped certain columns such as 'Latitude', 'Longitude' for better preprocessing of data.

We have also converted the "Time Stamp" from Exact Time in HH:MM format to Minutes.

Feature Selection is done to avoid data redundancy by dropping highly correlated features. In our Dataset, there is no strong correlated features found.
With Box Plotting, we have identified the Outliers and removed them accordingly; Premise, Description and Crimecode.

The Final Pre-processed CSV file consist of **2,15,392 rows** and **12 columns**.

# 5. Modeling
Based on the following attributes we are going to predict time at which it is not safe to go out in that locality.
*   Crime Description
*   Weapon type
*   Crime category(inside/outside)
*   Crime district

## Model types for our Analysis:
1. Linear Regression
2. XGBoost 
3. Random Forest Regression  
4. Ridge Regression
5. Lasso Regression

This is the result of all the Regression Models:

![This is the Screenshot of the Model Results](https://github.com/PicantaData/Crime-in-Baltimore/blob/main/Images/Screenshot_Model_results.png)

# Contributors
* Krupesh Parmar (202101160) - Data Cleaning and Random Forest Regression
* Vrishin Shah (202101094) - Data Visualization and Linear Regression
* Srikar Padaliya (202101095) - Data Preprocessing and Ridge Regression
* Aditya Singhania (202101086) - Data Visualization and XGBoost Regression
* Kirtan Mevada (202101012) - Lasso Regression, Data Cleaning and Documentation

