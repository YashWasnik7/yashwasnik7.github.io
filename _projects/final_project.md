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

## A comparison of EV usage across the US 
##### Authors: Vishnupriya Singh, Yash Wasnik
In a big city like Chicago, EV bikes make it very convenient to navigate around the city. Other advantages of EV include zero fuel cost, versatility
and environment friendly. Considering these benefits, we decided to plot the trip duration for EV bike rides in Chicago metroplolitan area using 
altair and matplotlib python libraries. We analyzed the dataset using pandas and found that 'Spin', 'Lime' and 'Bird' were the only bike providers in
our dataset. Hence, we first imported the data using pandas directly using the URL and filtered out Communities which had 5000 or less rows of data as
altair has a limit of 5000 rows. Keeping this limitation in mind, we chose 'Kenwood' as the start community which had 3344 rows of data. 

Plotting the trip end communitites (starting at Kenwood) was another challenge as we had no map data in our original dataset. Hence, we used chicago_zips_topojson
dataset (available on github) to plot all the ZIP codes in Chicago and this gave us the base map of Chicago region. Using the original Chicago EV dataset, we now
plotted the dots you see below using the Latitude and longitude data of End Community drop off locations. This gave us a beautiful density plot that you see below:

#### Chicago Map

<vegachart schema-url="{{ site.baseurl }}/assets/json/chicago_map.json" style="width: 100%"></vegachart>
Note: All rides start from 'KENWOOD' community


### Interactive Plot

<vegachart schema-url="{{ site.baseurl }}/assets/json/final_interactive_plot.json" style="width: 100%"></vegachart>

Click on the bar to see changes the distribuion of trip duration from August to December

How to use the dashboard:
Above is an interactive dashboard which shows the distribution of electric bike (EV) rides in Chicago area. Left side is a map of Chicago metropolitan area with circles of different colors, density and size. The bike vendors in our dataset are represented by blue, orange and green colors and the size corresponds to duration of trip.

Map - To view corresponding scatter and bar plots for a vendor, user needs to click on a circle from the map. For instance, clicking on a blue circle will only show plots for 'bird' vendor on all 3 visualizations. To reset the dashboard, the user can click anywhere on the map. Hovering over a dot will display the trip duration and name of the community where the ride was ended.

Bar plot - A user can also click on the horizontal bar plot to view corresponding drop locations on map and start time of each ride.

Scatter plot - This is static plot which shows the trip duration of EV rides from August 2020 to December 2020 with trip duration on y-axis. The plot changes as per selection from either the map or the bar plot. Points close to x-axis mean that shorter trip duration and viz. For instance, selecting bird vendor from bar plot show that more trip were taken from August - September but for short durations. The trips were very less in December.



### Search The Data & Methods

Below are links to the dataset (left button) and the analysis code (right button):

<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/lseemann/Chicago_ZIP_Codes/master/chicago_zips_topojson.json'" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/YashWasnik7/final_project_data_viz/blob/main/singh_vishnupriya_wasnik_yash_final_project_2.ipynb" text="The Analysis" %}
</div>


Link - https://urbanmatter.com/electric-or-auto-discover-chicagos-best-commuter-ebike-ride/#:~:text=Benefit%20of%20commuting%20with%20Electric,town%20without%20a%20sweat%20easily.