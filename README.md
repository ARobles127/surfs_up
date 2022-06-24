# Surfs_Up
SQLite 


## Overview of the analysis
Investing on a new business requires a deep analysis that encloses multiple factors like the demand for that product or service, climate, natural resources, a market analysis, etc. Backing a decision on a well structured investigation is crucial for the success of any business. For this project we are going to analyze the climate factor to determine if opening a surf shop in Oahu, Hawaii is a viable option for W.Avy in his team of investors. To start up we will analyze a data file containing information about Oahu’s weather for the past twelve months. To do so we will use Pandas, Python and SQLite queries.  



## Results
To help W.Avy accomplish his goal of opening a surf shop that also serves ice cream we focus our efforts on analyzing the climate in Oahu from two specific months, June and December. This investigation allowed us to conclude the following:


### June Temperature
Weather temperatures in Oahu are well known for being steady all year round with sunny and warm days and low chances of rain during the spring and summer season, making this place a perfect destination for a summer break. As the table shows the highest temperature is 85° F, while the lowest could be 64°F.  The precipitation percentages are  the lowest during these months, being less than 0.7”. 

![June_data](https://github.com/ARobles127/surfs_up/blob/main/June_data.png) 


### December Temperature
The winter temperature in Oahu is constant and  averages about 70°F to 75°F, just 10 degrees cooler than the summer season, though  the months of  October through March usually bring more rain than the rest of the year. However the winter season is considered the best time of the year to surf in Hawaii. 

![Dec_data](https://github.com/ARobles127/surfs_up/blob/main/Dec_data.png) 


###  Average Temperature
Temperatures in Oahu have not much variation and it is worth to say that even when the winter temperatures cool down, this time of the year is the best time for more experienced surfers to visit the island, which means that surfers and tourists will be visiting the island all  year round. 


## Summary
To conclude our analysis we are including two queries that will help W.Avy back his decision of opening a surf shop in Hawaii. The first query will allow him to see the number of stations being used to collect climate data to make sure there is a fair number of stations as well as enough data to make an informed decision. The second query will be crucial when W.Avy shows these findings to the stakeholders. This query will show the precipitation scores for any month of the previous year. 

#### Number of stations from which the precipitation data is being collected  
```
session.query(func.count(Station.station)).all()
```

#### Query that retrieves precipitation scores
```
dec_prep =  session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 6 ).all()
print(dec_prep)
```
