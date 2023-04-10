---
name: Vega Lite Example Project
tools: [Python, HTML, vega-lite]
image: assets/pngs/download.png
description: This is a "showcase" project that uses vega-lite for interactive viz!
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Plot 1



<vegachart schema-url="{{ site.baseurl }}/assets/json/altair_buildings_chart.json" style="width: 100%"></vegachart>

Line graph showing the distribution of Mean Square Footage by Year and City.

# Plot 2

<vegachart schema-url="{{ site.baseurl }}/assets/json/altair_max_total_floors.json" style="width: 100%"></vegachart>

Bar chart of Mean Maximum Total Floors by County.

## Search The Data & Methods

Below is where we can put some links to both the data and the analysis code as buttons:

<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_bcubcg_fall2022/main/data/building_inventory.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/YashWasnik7/assignment10/blob/main/singh-vishnupriya-wasnik-yash-assignment10.ipynb" text="The Analysis" %}
</div>

