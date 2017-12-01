# NBAY6170_project
Final project for Designing Data Products class

Initial Approach - 
We attempted to use K-Prototypes algorithm (a substitute for K-Means) as our dataset mainly had Categorical data except for Latitude and Longitude. We hoped to cluster similar incidents to see if there were distinct pattern or similarities within each cluster. The results so obtained seemed extremely vague and could not be validated in any way. There were similarities within clusters and without. So we ditched this line of thinking and adopted a more traditional, "data-sciency" approach.

Our goal was to figure out two things - 
1. The Zipcodes where crime was pre-dominantly higher than other Zipcodes
2. Where the Precincts were NOT effective in curbing the increasing criminal activity

Taking a deeper dive into the Dataset, we saw that none of the features were really indicative of either of our goals.
We began with feature engineering to expose the information belied in our dataset. We generated two different datasets and
ran a clustering algorithm - K-Means on both of them Independently.

A. All the features we intuitively thought would be informative in the dataset for clustering Zipcodes (zip_df Pandas dataframe):

    1. Zipcode - Descriptive feature representing every Zipcode. This is categorical in nature and not 
                 used in KMeans, only used for understanding.
    2. Borough - Descriptive feature representing the Borough. This is again categorical and not 
                 used in KMeans, only used for understanding.
    3. Avg_timezone0 - This represents the average number of monthly crimes (all categories) within 
                       the hours of 00:00 - 06:00AM
    4. Avg_timezone1 - Same as above except for hours of 06:00AM to 12:00PM
    5. Avg_timezone2 - Same as above except for hours of 12:00PM to 18:00PM
    5. Avg_timezone3 - Same as above except for hours of 18:00AM to 00:00AM
    6. Avg_month - Monthly average of all crimes for every Zipcode
    7. Monthly_trend - Linear correlation coefficient of the number of crimes committed every month 
                       over the year
    8. Avg_felony - Monthly average of all Felonies for every Zipcode
    9. Felony_trend - Linear correlation coefficient of the number of Felonies committed every month 
                      over the year
    10. Avg_misdem - Monthly average of all Misdemeanors for every Zipcode
    11. Misdem_trend - Linear correlation coefficient of the number of Misdemeanors committed every 
                       month over the year
    12. Avg_vio - Monthly average of all Violations for every Zipcode
    13. Vio_trend - Linear correlation coefficient of the number of Violations committed every 
                    month over the year
    14. Threat_to_PB - Separately calculated the number of crimes committed against the Person 
                       such as Homicide, Assualt, Kidnapping and the number of crimes committed against the 
                       belongings such as Theft, Fraud, Burglary, etc. The taking a ratio of these values 
                       to get a sense of if the area poses a threat to the person or to their belongings.

A. All the features we intuitively thought would be informative in the dataset for clustering Precincts 
   (pre_df Pandas dataframe):
    
    1. Precinct - Descriptive feature representing every Precinct. This is categorical in nature and not 
                 used in KMeans, used for reference.
    2. Borough - Descriptive feature representing the Borough. This is again categorical and not 
                 used in KMeans, only used for understanding.
    3. 3. Avg_timezone0 - This represents the average number of monthly crimes (all categories) within 
                       the hours of 00:00 - 06:00AM
    4. Avg_timezone1 - Same as above except for hours of 06:00AM to 12:00PM
    5. Avg_timezone2 - Same as above except for hours of 12:00PM to 18:00PM
    5. Avg_timezone3 - Same as above except for hours of 18:00AM to 00:00AM
    6. Avg_month - Monthly average of all crimes for every Zipcode
    7. Monthly_trend - Linear correlation coefficient of the number of crimes committed every month 
                       over the year
    8. Avg_felony - Monthly average of all Felonies for every Zipcode
    9. Felony_trend - Linear correlation coefficient of the number of Felonies committed every month 
                      over the year
    10. Avg_misdem - Monthly average of all Misdemeanors for every Zipcode
    11. Misdem_trend - Linear correlation coefficient of the number of Misdemeanors committed every 
                       month over the year
    12. Avg_vio - Monthly average of all Violations for every Zipcode
    13. Vio_trend - Linear correlation coefficient of the number of Violations committed every 
                    month over the year
    14. Threat_to_PB - Separately calculated the number of crimes committed against the Person 
                       such as Homicide, Assualt, Kidnapping and the number of crimes committed against the 
                       belongings such as Theft, Fraud, Burglary, etc. The taking a ratio of these values 
                       to get a sense if the area poses a threat to the person or to their belongings.

    15. Success_rate - This columns takes into account how many crimes were foiled as against the total 
                       number of crimes that were handled by this particular Precinct to get information 
                       as to how effective the Precinct is.
   






