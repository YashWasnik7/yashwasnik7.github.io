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


## Chicago Map

<vegachart schema-url="{{ site.baseurl }}/assets/json/chicago_map.json" style="width: 100%"></vegachart>

## Bar plot of time duration for bike vendors

<vegachart schema-url="{{ site.baseurl }}/assets/json/bar_plot.json" style="width: 100%"></vegachart>

# Interactive Plot

<vegachart schema-url="{{ site.baseurl }}/assets/json/final_interactive_plot.json" style="width: 100%"></vegachart>

Bar chart of Mean Maximum Total Floors by County.

## Search The Data & Methods

Below is where we can put some links to both the data and the analysis code as buttons:

<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/lseemann/Chicago_ZIP_Codes/master/chicago_zips_topojson.json'" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/YashWasnik7/final_project_data_viz/blob/main/singh_vishnupriya_wasnik_yash_final_project_2.ipynb" text="The Analysis" %}
</div>

