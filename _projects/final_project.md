---
name: Final Project
tools: [Python - altair, pandas, vega-lite]
image: assets/pngs/chicago_trips.png
description: IS445 - Data Vizualization Final Project
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

## A comparison of EV trips across the US 
Authors: Vishnupriya Singh, Yash Wasnik

### Chicago
In a big city like Chicago, EV bikes make it very convenient to navigate around the city. Other advantages of EV include zero fuel cost, versatility
and environment friendly. Considering these benefits, we decided to plot the trip duration for EV bike rides in Chicago metroplolitan area using 
altair and matplotlib python libraries. We analyzed the dataset using pandas and found that 'Spin', 'Lime' and 'Bird' were the only bike providers in
our dataset. Hence, we first imported the data using pandas directly using the URL and filtered out Communities which had 5000 or less rows of data as
altair has a limit of 5000 rows. Keeping this limitation in mind, we chose 'Kenwood' as the start community which had 3344 rows of data. 

Plotting the trip end communitites (starting at Kenwood) was another challenge as we had no map data in our original dataset. Hence, we used chicago_zips_topojson
dataset (available on github) to plot all the ZIP codes in Chicago and this gave us the base map of Chicago region. Using the original Chicago EV dataset, we now
plotted the dots you see below using the Latitude and longitude data of End Community drop off locations. This gave us a beautiful density plot that you see below:

### Map

<vegachart schema-url="{{ site.baseurl }}/assets/json/chicago_map.json" style="width: 100%"></vegachart>
**Note: All rides start from 'KENWOOD' community (created by the authors)**


### Interactive Plot 

<vegachart schema-url="{{ site.baseurl }}/assets/json/final_interactive_plot.json" style="width: 100%"></vegachart>

**Note: Select a vendor from the bar graph to view trip duration from August to December (created by the authors)**

Above is an interactive dashboard which shows the distribution of electric bike (EV) rides in Chicago area. Left side is a map of Chicago metropolitan area with circles of different colors, density and size. The bike vendors in our dataset are represented by blue, orange and green colors and the size corresponds to duration of trip.

* Map - To view corresponding scatter and bar plots for a vendor, user needs to click on a circle from the map. For instance, clicking on a blue circle will only show plots for 'bird' vendor on all 3 visualizations. To reset the dashboard, the user can click anywhere on the map. Hovering over a dot will display the trip duration and name of the community where the ride was ended.

* Bar plot - A user can also click on the horizontal bar plot to view corresponding drop locations on map and start time of each ride.

* Scatter plot - This is static plot which shows the trip duration of EV rides from August 2020 to December 2020 with trip duration on y-axis. The plot changes as per selection from either the map or the bar plot. Points close to x-axis mean that shorter trip duration and viz. For instance, selecting bird vendor from bar plot show that more trip were taken from August - September but for short durations. The trips were very less in December.

### Austin

The dataset of Austin is same as Chicago with the only difference being that instead of vendor type, we have vehicle type as bike, scooter and moped. The entire dataset of Austin contained only 1000 rows for years 2021 and 2022 so it was easy to plot. The plot above represents the trip duration in Austin for each vehicle type. The data was summarised so that we can get average of trip duration across all vehicle types.
<vegachart schema-url="{{ site.baseurl }}/assets/json/austin_pie_plot.json" style="width: 100%"></vegachart>
**(Plot created by the authors)**

Pie chart is most easy and clear to represent the trip duration as we only have 3 vehicle types. Here, we added a base pie plot on top of which we defined the radius and added label (Trip Duration) for each part. As seen above, moped had the most trip duration out of all three.

### Washington 

This dataset shows the Battery Electric Vehicles (BEVs) and Plug-in Hybrid Electric Vehicles (PHEVs) that are currently registered through Washington State Department of Licensing (DOL). Since, EV were made mainly after 2010, only that was used for our plot. In the line plot, the distribution of maximum electric range was shown for top 5 manufacturers Tesla, Nissan, Ford, Chevrolet and BMW. Other cars started manufacturing EVs later. 
It is seen here that Tesla has always been the top manufacturer of EVs used.

<vegachart schema-url="{{ site.baseurl }}/assets/json/wash_line.json" style="width: 100%"></vegachart>
**Note: Click on each legend to view only that model's distribution (plot created by the authors)**

### Data Sources and Analysis: 

<!-- these are written in a combo of html and liquid --> 
<!-- [Chicago](https://raw.githubusercontent.com/lseemann/Chicago_ZIP_Codes/master/chicago_zips_topojson.json)  
[Austin](https://data.austintexas.gov/Transportation-and-Mobility/Shared-Micromobility-Vehicle-Trips/7d8e-dm7r) <br />
[Washington](https://data.wa.gov/api/views/f6w7-q2d2/rows.csv?accessType=DOWNLOAD) -->


<div>
  <a href="https://raw.githubusercontent.com/lseemann/Chicago_ZIP_Codes/master/chicago_zips_topojson.json" class="button">Chicago</a>
  <a href="https://data.austintexas.gov/Transportation-and-Mobility/Shared-Micromobility-Vehicle-Trips/7d8e-dm7r" class="button">Austin</a>
  <a href="https://data.wa.gov/api/views/f6w7-q2d2/rows.csv?accessType=DOWNLOAD" class="button">Washington</a>
  <a href="https://github.com/YashWasnik7/final_project_data_viz/blob/main/singh_vishnupriya_wasnik_yash_final_project.ipynb" class="button">Analysis</a>

</div>

<style>
  .button {
    display: inline-block;
    padding: 20px;
    background-color: white;
    color: blue;
    text-decoration: grey;
    border-radius: 5px;
    margin-right: 60px;
  }
</style>


## References:
1. <https://uiuc-ischool-dataviz.github.io/is445_oauoag_spring2023/nbv.html?notebook_name=%2Fis445_oauoag_spring2023%2Fweek03%2FinClass_week03.ipynb>

2. <https://towardsdatascience.com/3-ways-to-build-a-geographical-map-in-python-altair-77c8e0781538>

3. <https://altair-viz.github.io/altair-tutorial/notebooks/06-Selections.html>

4. <https://altair-viz.github.io/gallery/pie_chart_with_labels.html>

5. <https://data.wa.gov/Transportation/Electric-Vehicle-Population-Data/f6w7-q2d2>

6. <https://urbanmatter.com/electric-or-auto-discover-chicagos-best-commuter-ebike-ride/#:~:text=Benefit%20of%20commuting%20with%20Electric,town%20without%20a%20sweat%20easily.>

