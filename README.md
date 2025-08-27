# Scottish Munros - Tidy Tuesday - 19.08.2025
This is my first ever Tidy Tuesday project. In this project we are looking at the data provided as part of the challenge and revolves around Scottish Munros and their classification. 

## Dataset
* **Source:** [Tidy Tuesday - 19.08.2025](https://github.com/rfordatascience/tidytuesday/tree/main/data/2025/2025-08-19)

## Tech Stack
* `pandas`
* `matplotlib`
* `math`
* `requests`
* `folium`
* `pyproj`
* `Overpass API`

## Key Steps
1. **Step 1. Explore the data**
2. **Step 2. Cleaning data**
3. **Step 3. Answering Questions**
4. **Step 4. Creating Power BI Dashboard**

## Project Objective
As this is my first challenge initially i will try to answer questions stated in the description of the Tidy Tuesday project. Once i've answered initial challenges i can further explore the dataset and perhaps find some other interesting insights.

* How many peaks currently listed as Munros have always been included on the list?
* Which year saw the largest number of changes to the classification?
* Which Munro is the most remote?

## Dataset overview
The dataset contains information about Scottish Munros, their classification, coordinates, names and height. 

## Data cleaning
In this step i've cleaned the dataset to make it easier to work with. 

* **Removing Last Row** There was a row of unrelated data which had to be removed as it did not contain any information relating to munros
* **Removing Comments Column** Comments column removed due to not providing any value and containg comments about classification changes. I've decided to remove this as majority of entries were NA and would not provide any value.
* **Replacing NA values in classification** This is the most labor intensive part. Classifications in some years were missing. I've decided to directionally fill classifications. For example if there was a classification in 1891 but the values in subsequent years are missing it would be safe to assume that classification is still the same. Where there is no earlier classification we would replace our missing values with unclassified to remove NA values from the dataset. 
* **Making column names lowercase** This is matter of preference, i prefer to work with columns with lower case names.

## Answering questions
* **How many peaks currently listed as Munros have always been included on the list?** In this step we need to check our early classification to establish which record has consistently remained a Munro over the years and have always been included (there is no gaps in classification, and the record is remained a Munro)

* **Step 3.2 Which year saw the largest number of changes to the classification?** In this step we need to compare classification changes by year to establish which year had the most classification changes in a year. 

* **Step 3.3 Which Munro is the most remote?** In this step we need to establish which munro can be considered as the most remote. However there is no one acceptable way of calculating remotness. As this is my first project part of Tidy Tuesday i would prefer to keep things relatively simple. I will calculate the remotness of the Munro as the distance between Munro and the closest population center. To do this i have to do a couple of things with our dataset, first we need a way of converting existing coordinate data to latitude and longitude, second i need a method of calculating distance that takes account of the earth curvature and third i need data about population centers in Scotland ( this will be achievied using Overpass API). 

## Creating a Power BI Dashboard
In this step i've used the data prepared with python to create a power bi dashboard. 

![Dashboard classificaiton tooltip](/dashboard_screenshot/yearly_classification_tooltip.JPG "Dashboard classificaiton tooltip")
![Dashboard start schema ](/dashboard_screenshot/data_modelling.JPG "Star schema")
![Filtering by population center ](/dashboard_screenshot/filtering_population_center.JPG "Filtering by population center")