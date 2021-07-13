---
title: A Comprehensive Toolbox for Tree Physiological Data Processing in R
date: "2021-02-09T00:00:00Z"
draft: false
linktitle: ESA2021 Tree Physiological Toolbox
menu:
    esa2021-workshop:
      name: Introduction
      weight: 1
summary: Introduction to methods for processing time series in ecological research.
type: docs
weight: 1
---



The increasing availability of tree physiological data provides unique opportunities for exploring tree and forest function, health, and resilience to ongoing environmental changes. However, processing such data sets is challenging, due to data quantity and quality, labor-intensive data cleaning, user-specific assumptions, and methodological uncertainties.
Within this workshop we aim at addressing some of these issues though a toolbox of novel `R` packages geared towards comprehensive tree physiological data processing.
We provide participants hands-on training on free software tools and their synergies for tree physiological data processing, spanning from interactive visual inspection and cleaning of raw data to advanced data analyses and uncertainty quantification. 
Three main topics are covered:  
1. Interactive data cleaning with [`datacleanr`](https://the-hull.github.io/datacleanr/), an R package designed to ensure best data-handling practices of spatio-temporal tree ecophysiological data.  
2. Sap flow data processing with the [`TREX`](https://the-hull.github.io/TREX/),including gap-filling thermal dissipation data, converting heat metrics to sap flow,and estimating data-processing uncertainties.  
3. Dendrometer data processing with [`treenetproc`](https://github.com/treenet/treenetproc/), an `R` package with advanced functionalities on partitioning stem growth and hydraulic signals from dendrometer data and on detecting growing season dynamics.

Here we present step by step examples on how to process data of time series collected at the Hyytiälä Forestry Field Station, a flux tower site in Finland. 
At this site three mature trees (two Pinus sylvestris and one Betula spp.) were equipped with linear variable differential transformator (LVDT) dendrometers and thermal dissipation probes (TDP).
These sensors were used to monitor stem radial dynamics (in µm) and sap flux density (in cm3 cm-2 h-1) from 2015 until 2018. 

The presentation for the course can be found [here](https://raw.githubusercontent.com/deep-org/workshop_data/master/esa-workshop2021/ESA2021.pdf),
and along with example data sets [here](https://github.com/deep-org/workshop_data/tree/master/esa-workshop2021).


Participants should bring their own laptops with pre-installed [`R`](https://r-project.org)/[`RStudio`](https://rstudio.com/).

![Screenshot of ESA 2021 workshop presentation](/docs-workshops/esa-workshop2021/_index_files/deepesa.png)

