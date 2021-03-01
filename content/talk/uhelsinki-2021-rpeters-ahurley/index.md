---
title: Time series data processing course

authors: [rpeters, ahurley]

summary: "Introduction to methods for processing time series in ecological research"

all_day: false
date: "2021-02-09T08:00:00Z"
date_end: "2021-02-09T12:00:00Z"

event: Time Series Course
location: Virtual Meeting - University of Helsinki
featured: false

image:
  caption: 'Image credit: **R. Peters**'
  focal_point: Right

links:
- icon: search
  icon_pack: fas
  name: View Materials
  url: /docs-workshops/uhelsinki-workshop2021
- icon: file-alt
  icon_pack: fas
  name: View Files
  url: https://github.com/deep-org/workshop_data/tree/master/UH

math: true
publishDate: "2020-07-01T00:00:00Z"
tags:
- R
- DEEP
url_code: ""
url_pdf: "https://raw.githubusercontent.com/deep-org/workshop_data/master/UH/Course%20-%20Time%20series%20data%20processing.pdf"
url_video: ""

# {{% alert note %}}
# Contact authors for more details and pre-requisites for attending this course.
# {{% /alert %}}


---

Ecological research is becoming increasingly data-rich, with automated sensors providing highly relevant time-series data on both the health status of our forests and the environment to which it is exposed.
However, the properties of time-series data, including its large quantity of data, sometimes irregular collection intervals, and need for temporal data aggregation, makes working with such data difficult.
Issue are often encountered in relation to adjusting the data format, making sense of the timestamp utilized during the data collection, and removing outliers. 
Yet, users of time-series data often apply their own methods for processing and cleaning their time series, allowing for little communication on the encountered issues, nor providing transparency and reproducibility of data processing practises. 
Our goal should thus be to make methods for data processing in ecological research more accessible, save time and standardize workflows.

Here we present step by step examples on how to process data of time series collected at the Hyytiälä Forestry Field Station, a flux tower site in Finland. 
At this site three mature trees (two Pinus sylvestris and one Betula spp.) were equipped with linear variable differential transformator (LVDT) dendrometers and thermal dissipation probes (TDP).
These sensors were used to monitor stem radial dynamics (in µm) and sap flux density (in cm3 cm-2 h-1) from 2015 until 2018. 
Yet, multiple data-processing steps have to be taken to obtain usable measurement for data analyses. 
Within this course (original given at the University of Helsinki) we present the basis of time series data processing, common issues and R packages (including datacleanr, treenetproc and TREX) capable of supporting fast and reproducible data processing. 


The presentation for the course can be found [here](https://raw.githubusercontent.com/deep-org/workshop_data/master/UH/Course%20-%20Time%20series%20data%20processing.pdf),
and along with example data sets [here](https://github.com/deep-org/workshop_data/tree/master/UH).


![Presentation screenshot](/talk/uhelsinki-2021-rpeters-ahurley/index_files/deep.png)