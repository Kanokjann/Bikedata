# Cyclists Bike Share Analysis
## Table of Contents
- [Project_Overview](#project-overview)
- [Data_Sources](#data-sources)
- [Recommendations](#recommendations)
  
### Project Overview

The purpose of this project is to consolidate downloaded Divvy data into a single dataframe and then conduct simple analysis to help answer the key question: “In what ways do members and casual riders use Divvy bikes differently?", we seek to identify trends, make data-driven recommendations, and gain a deeper understanding of the company's performance.

### Data Sources

This analysis is based on the Divvy case study "'Sophisticated, Clear, and Polished’: Divvy and Data Visualization" written by Kevin Hartman (found here: https://artscience.blog/home/divvy-dataviz-case-study)

### Tools
- R RStudio

### Data Cleaning/Preparation
In the initial data preparation phase, we performed the following tasks:
1. Data loading and inspection
2. Handling missing values
3. Data cleaning and formatting

### Exploratory Data Analysis
- In what ways do members and casual riders use Divvy bikes differently?
- How many members vs casual?
- What are the peak usage periods?
- What is the over usage trend weekday-wise?
- How long customer normally use the bike?

### Data Analysis
Interesting code worked with
Add a ride_length calculation to all_trips (in mins) using "difftime"
```{r}
all_trips$started_at <- as.POSIXct(all_trips$started_at, format = "%m/%d/%Y %H:%M")
all_trips$ended_at <- as.POSIXct(all_trips$ended_at, format = "%m/%d/%Y %H:%M")

all_trips$ride_length <- difftime(all_trips$ended_at, all_trips$started_at, units = "mins")
```

### Results/Findings

The analysis results are summarized as follows:
1. The number of casual and member are 725,635 and 2,502,456 respectively.
2. The casual and member both ride on weekday (Monday, Tuesday, Wednesday, Thursday and Friday) more than weekend.
3. The average ride duration for casual is above 50 mins throughout the whole week while for member is below 20 mins.

### Recommendations

Based on the analysis, we recommend the following actions:
- Invest in marketing and promotions during weekday to maximize revenue and gain more member rider.
- Focus on expanding and promothing campaign for a short ride type (less than 20 mins).
- Implement a new segmentation especially for long duration ride (above 50 mins) to attract casual to become a membership.

### Limitations
This study is using the data from 2019Q2 - 2020Q1.
I had to remove bad data as the dataframe includes a few hundred entries when bikes were taken out of docks and checked for quality by Divvy or ride_length was negative.

### References
This project is part of capstone project from Google Data Analytics Professional Certificate.







