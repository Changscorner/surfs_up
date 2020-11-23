# surfs_up

## Overview
Analysis of the temperature in Hawaii from the months of June to December in order to determin if a surf and ice cream shop business is sustainable outside of the summer months.

### Results

#### June and December Temperatures
<p align = "center">
<img src ="https://github.com/Changscorner/surfs_up/blob/main/Resources/Table%202.png"> 
<img src = "https://github.com/Changscorner/surfs_up/blob/main/Resources/Table%201.png">

- In June the temperature averaged around 74.9F with the lows around 64F and high around 85F while for December the average temperature was around 71F with the lows around 56F and the high at 83F.
- Around 50% of the daily temperature in June was around 75F while in December it was at 71F.
- The standard deviation of temperature in December is approximately 0.75 higher than in June which accounts for the larger range in temperatures in the first and third quartile.


### Summary

The difference in standard deviation from close to the peak during summer and the cold months during the winter is not as large as one would think. 
With the STD being around only 0.75 between the two months and the max temperature having a difference of only 2 degrees F.

With this information we can make a reasonable conclusion that an ice cream and surf business would definitely be viable year round in Hawaii. 
 
#### Additional Queries
There are additional queries that we can make to further assist in assessing if this type of business would be viable.

1.) Most Active Stations in June and December

The code should look like this:
	
	session.query(Measurement.prcp).filter(Measurement.station == 'USC00519281').filter(extract('month', Measurement.date) == 6).all()
	
	session.query(Measurement.prcp).filter(Measurement.station == 'USC00519281').filter(extract('month', Measurement.date) == 12).all()

This code will take a look at the most active weather measuring stations and look at the precipitation amounts at those stations.

2.) Total Precipitation Measurement

The code that would be used should look like this:
	
	session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 6).all()
	
	session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 12).all()
	
This should assist in seeing how much rain the months June and December receive.
