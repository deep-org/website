---
title: A Comprehensive Toolbox for Tree Physiological Data Processing in R
date: "2021-02-09T00:00:00Z"
draft: false
linktitle: Tree Physiological Toolbox
menu:
    esa2021-workshop:
      name: Introduction
      weight: 1
summary: Introduction to methods for processing time series in ecological research.
type: docs
weight: 1
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


The presentation for the course can be found [here](https://raw.githubusercontent.com/deep-org/workshop_data/master/esa-workshop2021/ESA2021.pdf),
and along with example data sets [here](https://github.com/deep-org/workshop_data/tree/master/esa-workshop2021).


![Screenshot of ESA 2021 workshop presentation](/docs-workshops/esa-workshop2021/_index_files/deepesa.png)

