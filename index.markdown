---
layout: continous
title: "Home"
---

<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
</script>

## Introduction

In this article, we will explore the relationship between crime density and the socioeconomic status of San Francisco districts during the 2012-2016 period. By drawing demographic statistics for each district, we will calculate an index to represent the socioeconomic status. We will focus particularly on the Tenderloin district, as it represents a notable example of a low socioeconomic status combined with a high crime density.

## Crime Density
Crime numbers vary for each district, but not all districts have the same size and population density. Therefore, it's essential to consider crime density for these areas. Since San Francisco is densely populated, we will focus on the size of each district as the primary factor for this analysis, rather than incorporating population density.

To calculate the size of each district, we used geodata from district shapefiles. We simplified the process by treating each district as a rectangle, with its edges determined by the minimum and maximum latitude and longitude values.

With the area for each district calculated, we then determined crime density by dividing the total number of crimes in a given district by its area resulting to the following table, sorted by crime count.

| Districts  | Crimes | Area (km^2) | Crime Density |
|------------|--------|-------------|---------------|
| Southern   | 221507 | 16.62       | 13328         |
| Northern   | 167984 | 17.94       | 9364          |
| Mission    | 159065 | 13.14       | 12105         |
| Central    | 135864 | 10.74       | 12650         |
| Bayview    | 109603 | 53.05       | 2066          |
| Tenderloin | 103369 | 1.79        | 57748         |
| Ingleside  | 99392  | 32.03       | 3103          |
| Taraval    | 86292  | 46.34       | 1862          |
| Park       | 66385  | 17.00       | 3905          |
| Richmond   | 65291  | 29.77       | 2193          |

Following our calculation of crime density, we have created a bar chart to better visualize the data. The chart clearly illustrates that the Tenderloin district has the highest crime density compared to the other districts. This striking difference emphasizes the need to further explore the factors contributing to crime rates in the city and particularly in the Tenderloin district.

<img src="/images/BarChart.png"  width="1000" height="400">

## Socioeconomic Status
San Francisco is well-known for its significant socioeconomic disparities between its districts, ranking high among other US cities in this regard. To measure these differences, we computed a socioeconomic index for each district, where a higher index represents a lower socioeconomic status.

By examining [this report of demographic statistics](https://default.sfplanning.org/publications_reports/SF_NGBD_SocioEconomic_Profiles/2012-2016_ACS_Profile_Neighborhoods_Final.pdf) for each district in San Fransico , we derived rough yet valuable estimations of crucial factors that characterize the socioeconomic status of each district for 2012-2016. In the following table, we have statistics about median household income and unemployment rates for each district:

| Districts  | Household Income | Unemployment Rate (%) |
|------------|------------------|-----------------------|
| Tenderloin | 23500            | 9                     |
| Southern   | 40000            | 8                     |
| Central    | 65000            | 5                     |
| Mission    | 55000            | 6                     |
| Northern   | 90000            | 4                     |
| Park       | 75000            | 4                     |
| Ingleside  | 60000            | 5                     |
| Richmond   | 80000            | 4                     |
| Bayview    | 45000            | 7                     |
| Taraval    | 70000            | 4                     |

Additionally, we also have information about education and poverty rates of each district.

| Districts  | Higher Education (%) | Poverty Rate (%) |
|------------|----------------------|------------------|
| Tenderloin | 10                   | 20               |
| Southern   | 15                   | 16               |
| Central    | 35                   | 12               |
| Mission    | 25                   | 14               |
| Northern   | 55                   | 8                |
| Park       | 45                   | 10               |
| Ingleside  | 30                   | 12               |
| Richmond   | 50                   | 9                |
| Bayview    | 20                   | 15               |
| Taraval    | 40                   | 11               |

To calculate the index for each district, we normalized factors that positively influence the status and inverse normalized factors with a negative impact. Then, we applied this formula:

$$status = 0.4*In+0.2*Po+0.2*Ed+0.2*Un $$ 

with varying weights for each factor. The outcomes of our calculations are displayed on the below choropleth map.

<img src="/images/Map.png"  width="1000" height="400">

Upon examining the map, it becomes apparent that the Tenderloin district has the lowest socioeconomic status(biggest index) compared to the other districts.

## Results
Now that we can see that Tenderloin is the district with the lowest socioeconomic status and highest relative crime rate in regards to the aforementioned index, we want to investigate whether there has been taken action against the high crime rate. We can figure this out through the data by plotting the crime rate in Tenderloin throughout the years.

We will limit the years used in this plot to the same range used in the report, which is from 2012 to 2016. This plot will be made with Bokeh and it's interactive plotting Rangetool, so that we can see how the amount of crimes per week evolves over the years and so that we can see any possible trends. Since the data curve will be very noisy, we will plot an additional line where we have applied a Savitzky–Golay filter in order to smooth the curve.

{% include interactive_small_tenderloin.html %}

Using this tool we can see that the overall trend is negative which indicates that even though Tenderloin is the district in San Fransico with the highest socioeconomic index, efforts are being made into reducing the amount of crimes in the district.


## Conclusion

In this article, we have studied the crime rates of each district in San Fransico in regards to their size, and found that Tenderloin is the district with the highest crime density. We then investigated the socioeconomic status of each district in San Fransico, and calculated an index that is indicative of this status. Through this index we found that Tenderloin was also the district with the lowest amount of socioeconomic status.

We also investigated whether action had been taken to reduce the amount of crime in Tenderloin through interactive plotting, and we discovered that there is a negative trend in crime rates in Tenderloin, indicating that it is indeed the case.