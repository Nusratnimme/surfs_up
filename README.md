# Work hard, play included: my Surf n' Shake business

## Overview

I need funds from investor W. Avy, known for his love of surfing, to open a surf n' shake shop in Hawaii. This can turn my passion for surfing into my profession while allowing me to live in the sunny and warm Hawaii. W. Avy, however, would like some more insights into the feasibility of the business. He had previously invested in a similar business which was rained out of existence. He has some data on temparature and precipitation of the island of Oahu that he wants me to analyze and present findings on.

### Data Source

- Data Source: hawaii.sqlite database

- Query Tool: SQLAlchemy

- Softwares:Python 3.9.7, Jupyter Notebook 6.4.5, VSCode


## Purpose

The main objective of this exercise is to analyze the temperature patterns of Oahu for the months of June and December. Using Python, Pandas functions and methods, and SQLAlchemy, the date column of the Measurements table will be filtered on from the **hawaii.sqlite** database to retrieve recorded temperatures for both months.


## Results

### Statistics on temperature

- Temperature was retrieved from the data by creating two separate queries for the month of June and December.
```
june_temps = session.query(Measurement.date, Measurement.tobs).filter(extract('month', Measurement.date) == 6).all()

```
```
dec_temps = session.query(Measurement.date, Measurement.tobs).filter(extract('month', Measurement.date) == 12).all()

```

- The output was converted to lists and two separate DataFrames were created for each of the month. Next, summary statistics were calculated.

**June temperatures**

![June_temps](https://github.com/Nusratnimme/surfs_up/blob/main/Resources/June_Temp_df.png)

**December temperatures**

![Dec_temps](https://github.com/Nusratnimme/surfs_up/blob/main/Resources/Dec_Temp_df.png)


**Summary statistics for temperature in June**

![June_statistics](https://github.com/Nusratnimme/surfs_up/blob/main/Resources/June_Temp_Stat.png)

- From the above table it can be seen that in the month of June, only **one-fourth of the days were colder than 73 fahrenheit**. Considering the mean, median and standard deviation, it's evident that the temperature didn't change much over the period.

**Summary statistics for temperature in December**

![December_statistics](https://github.com/Nusratnimme/surfs_up/blob/main/Resources/Dec_Temp_Stat.png)


- In the month of December, **half of the days were warmer than 71 fafrenheit**. The standard deviation indicates that temparatures can indeed vary a little bit..

- With the help of the summary statistics for both months, it can be concluded that **June has consistent warmer weather** and relatively less rise and fall in temparature.


## Summary

In order to determine if the surfing and ice cream shop business will be sustainable year-round, it is important to look at **precipitation** in addition to temparature for both months. We can expect to see **good business on warm days with little or no rain**. Anything different will impact business negatively.

To this end, two DataFrames were created containing both precipitation and temperatures. Next, summary statistics was calculated.

**Summary statistics of precipitation and temperature for June**

![June-prcp_temp](https://github.com/Nusratnimme/surfs_up/blob/main/Resources/June_prcp_temp.png)

**Summary statistics of precipitation and temperature for December**

![Dec_prcp_temp](https://github.com/Nusratnimme/surfs_up/blob/main/Resources/Dec_prcp_temp.png)


As can be seen from the tables above, mean precipitation are higher in December than in June indicating a more rainy weather in the former. Combining this with findings for temparature, we can conclude that December will have fewer days suitable for surfing, as well as ice-cream, than in June.

But the question is, how many days in each month can be considered _surfing-friendly_?. If we arbitrarily decide that temparature above 70 fahrenheit and precipitation less than 1 inch are conducive to surfing and enjoying ice-cream, we find that, on an average, **26 days in June and 19 days in December are surfing-friendly** (see "SurfsUp_Challenge.ipynb").

To conclude, Oahu definitely offers an ideal weather for a surf n' shake business!
