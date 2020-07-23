---
title: Advanced Analyses of Tree Physiological Time Series in R and PhytoSim

authors: [cpappas, rpeters, "Roman Zweifel", "Kathy Steppe", ahurley]

summary: "Introducing (R) software for processing high-frequency dendrometer and sapflow data."

all_day: true
date: "2020-08-03T08:00:00Z"
date_end: "2020-08-06T23:59:00Z"

event: ESA 105th Annual Meeting 
event_url: https://www.esa.org/saltlake/
location: Virtual Meeting
featured: false

image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/Sg9j3QqOpTo)'
  focal_point: Right

links:
- icon: search
  icon_pack: fas
  name: View Materials
  url: /docs-workshops/esa-workshop2020
- icon: file-alt
  icon_pack: fas
  name: See Files
  url: https://github.com/deep-org/workshop_data/tree/master/esa-workshop2020

math: true
publishDate: "2020-07-01T00:00:00Z"
tags:
- R
- DEEP
url_code: ""
url_pdf: ""
url_video: ""

# {{% alert note %}}
# Contact authors for more details and pre-requisites for attending this course.
# {{% /alert %}}


---


Increasing availability of tree physiological time series on tree growth and water use provide unique opportunities for exploring tree and forest function, health, and resilience to ongoing environmental changes.\ However, processing such time series data is challenging, due to data quantity and quality, varying time steps, labour-intensive data cleaning, and assumptions for converting raw measurements to physiologically meaningful quantities. 
To resolve such issues, software tools are continuously being developed, facilitating data pre- and post-processing in a fast, efficient and reproducible way.

Within this workshop we provide participants hands-on training on novel software tools: R packages to process dendrometer and sap flow data, and PhytoSim models to integrate data and unravel underlying mechanisms.
Dendrometer functionalities include the option to align measurements to regular time intervals, remove outliers and correct for data-jumps.
Additionally, parameters such as yearly growth or maximum daily shrinkage are provided.
For sap flow data processing, we present functionalities for importing and homogenising raw measurements, conducting various data-processing approaches, calculating sap flux density and crown conductance, and their uncertainties.
For the dendrometer-sap flow combination, we focus on turgor-driven growth and hydraulics.

Guided by example datasets, this interactive workshop presents a benchmark for dendrometer and sap flow data processing methods and facilitates greater potential for improving comparability between datasets.
Participants should bring their own laptops with pre-installed copy of [R](http://r-project.org) and [RStudio](http://rstudio.com) and/or [PhytoSim](http://phyto-it.com). 
Data files and codes for this workshop will be made publicly available, so participants and those unable to attend will have access to these resources.


___


## Organizer

- Richard L. Peters (Ghent University)

## Co-organizers
 
- Christoforos Pappas (Universit? de Montr?al)
- Roman Zweifel (Swiss Federal Institute for Forest, Snow and Landscape Research WSL)
- Kathy Steppe (Ghent University)
- Alexander Hurley (GFZ)
