---
layout: continous
title: "Home"
---

<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
</script>

## Introduction

In this article, we will explore the relationship between crime density and the socioeconomic status of San Francisco districts during the 2012-2016 period. By drawing demographic statistics for each district, we will calculate an index to represent the socioeconomic status. We will focus particularly on the Tenderloin district, as it represents a notable example of a low socioeconomic status combined with a high crime density.

## San Fransico, Tenderloin

$$scaled\;crime\;count = \frac{crime\;count}{socioeconomic\;index}$$

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
San Francisco is well-known for its significant socioeconomic disparities between its districts, ranking high among other US cities in this regard. To measure these differences, we computed a socioeconomic index for each district, where a higher index represents a lower socioeconomic status. By examining [this report of demographic statistics](https://default.sfplanning.org/publications_reports/SF_NGBD_SocioEconomic_Profiles/2012-2016_ACS_Profile_Neighborhoods_Final.pdf) for each district in San Fransico , we derived rough yet valuable estimations of crucial factors that characterize the socioeconomic status of each district. The results can be in the two following tables.

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

Fusce vel elit id tellus consequat ullamcorper. Donec sollicitudin sapien vitae fermentum ornare. Donec laoreet ullamcorper tellus, ac bibendum ipsum molestie ut. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Etiam suscipit dolor a odio lobortis, in consequat odio viverra.

{% include interactive_small_tenderloin.html %}


## Conclusion

Quisque bibendum, mauris id ullamcorper hendrerit, odio mauris facilisis elit, sit amet consectetur nisi neque in ligula. Sed laoreet fermentum arcu, a aliquam dui vehicula vitae. Duis bibendum justo vitae mi bibendum, eu eleifend lacus pulvinar. Morbi ullamcorper bibendum nunc, vitae vestibulum odio pellentesque ac.

Fusce eu porttitor odio. Vestibulum eget elit sem. Interdum et malesuada fames ac ante ipsum primis in faucibus. Morbi placerat sem et eros egestas, non congue massa efficitur. Sed pharetra ligula efficitur nunc mollis suscipit. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Proin maximus molestie consequat. Donec justo urna, consectetur a nulla at, rutrum dapibus metus. Mauris lacinia arcu elementum sem bibendum viverra.

Proin sit amet ante purus. Integer tincidunt venenatis ligula eget porttitor. Suspendisse potenti. Mauris tincidunt massa sit amet mi ultrices efficitur. Curabitur ac eros in dui posuere semper. Sed iaculis ipsum at est tincidunt faucibus. Nam lacus massa, aliquet at urna sed, scelerisque viverra quam. Vestibulum id lacus ut diam lobortis pellentesque tincidunt interdum eros.

Aliquam auctor tortor neque, ac viverra mauris porta ac. Fusce eu ullamcorper nisi. Nam enim felis, posuere mollis ante in, faucibus convallis sem. Aenean quis mollis ante. In interdum nulla at augue euismod, vel rutrum turpis ultricies. Maecenas eget mollis metus. Ut lacinia massa non semper semper. Fusce interdum posuere erat pulvinar bibendum. Nunc vestibulum eros et lacus elementum, in tristique nibh feugiat. Aenean suscipit libero et magna pellentesque viverra. Etiam sagittis, elit in congue lacinia, neque dui convallis nunc, vitae faucibus augue magna vitae lorem. Duis dapibus, lorem sed imperdiet elementum, purus justo euismod sapien, sit amet eleifend ipsum justo ac nisi. Suspendisse eget sodales quam, et mollis elit. Etiam efficitur tincidunt rhoncus.

Nam volutpat sapien eget quam dapibus ornare. Nullam eleifend justo porta magna tincidunt, ut vestibulum mi aliquet. Morbi in risus tortor. Donec a elit eu ex interdum convallis vel vitae arcu. Morbi in dui vel odio feugiat suscipit tristique quis turpis. Mauris ut risus vel odio ultrices vehicula quis eget velit. In hac habitasse platea dictumst. Donec nec efficitur felis. Vivamus tincidunt tempus metus eget rutrum. Pellentesque fermentum aliquam accumsan. Quisque non leo vitae magna posuere elementum eu nec leo. Ut rutrum neque quis ante ornare, ac placerat massa sodales.

Nulla a fringilla erat, ac maximus turpis. Mauris bibendum tempor gravida. Ut blandit elit sit amet sollicitudin gravida. Nam dolor tellus, posuere ut mi nec, rutrum viverra sem. Cras sed risus a sem ultrices malesuada vitae eget urna. Nulla maximus sapien maximus est aliquet pulvinar. Duis ligula eros, aliquam at risus a, fermentum vulputate leo. Pellentesque eu pharetra ex. Quisque eleifend sit amet dui a semper. Quisque sem risus, suscipit et orci malesuada, ultrices tincidunt justo. Nunc id nisi a ante sagittis tincidunt. Nulla euismod turpis metus, vel sagittis metus sodales in. Vivamus iaculis efficitur justo, eu venenatis est. Vestibulum vitae risus nulla. Vivamus consequat lorem at neque imperdiet feugiat. In sed bibendum ligula.

