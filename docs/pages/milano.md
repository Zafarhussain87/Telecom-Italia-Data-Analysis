---
layout: default
---

[Introduction](./../index.html) | [Milano Data Analysis](./../pages/milano.html) | [Trento Data Analysis](./../pages/trento.html) | [Weather Correlation](./../pages/correlation.html)

As per the already defined queries, the telecommunication data was merged before applying the analysis techniques. Data was given with an interval fo 10 minutes for sms in and out, call in and out, and internet activity.

#### Milano Congested Hours

I merged all this data on the basis of timestamp. Then the data was grouped together for the same hours. The same approach has been applied for the data of each day for November and December. In the end, the hours with maximum telecommunication congestion were filtered out. 

![Milano Cog Hours](./assets/images/milano_cong_hours.png)


#### Most Called Province From Milano

I read all the csv files from the directory through GraphLab as one single frame. The GraphLab makes it easy to read hundreds and thousands of files in parallel and returns them as a single frame. The returned frame 

[back](./../pages/index.html)
