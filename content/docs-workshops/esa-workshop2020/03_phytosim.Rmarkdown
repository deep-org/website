---
author: [Kathy Steppe]
draft: false
date: 2020-07-21T20:00:00
categories: ["R", "workshop"]
tags: ["process-based model", "physiology"]
linktitle: PhytoSim Workflow
menu:
    esa-workshop:
      weight: 30
title: Analysis Workflow
type: docs
toc: true
---


## 1. Background

State-of-the-art mechanistic models can simulate intra-daily stem growth (of both xylem and phloem) and internal stem hydraulics with an (sub-)hourly resolution by combining dendrometer and sapflow measurements. 
`PhytoSim` was designed to apply such models, consisting of a set of dynamic algebraic and/or first order  (ordinary) differential equations - it is a dynamic *Plant Modelling and Simulation* software.

`PhytoSim` can be downloaded [here](https://www.phyto-it.com/).

Main features of the software are:

- Compilation free modelling,
- Model editor with syntax highlighting, real-time model analysis and unit checking,
- Supports dynamic models with algebraic and/or differential equations,
- Built-in plant model library (including simulation examples for all models),
- Unit support throughout the entire modelling/simulation process,
- Dynamic model simulation,
- Automatic (moving window) model calibration,
- Uncertainty analysis,
- Sensitivity (local and global) and identifiability analysis.


## 2. Mechanistic modelling of tree hydraulics and turgor-driven growth 

### `STACI` model 

The model is driven by the sap flow to the crown, *F(crown)*.
The stem of diameter *D* is modelled by two coaxial cylinders (xylem and stem storage compartment, respectively) separated by a membrane.
The radial flow rate into and out of the stem storage compartment is represented by *f(stem)*.
This radial water flow (bold arrow) establishes the direct link between the sub-model for calculating dynamic water transport and the sub-model for predicting stem diameter variations.
Depending on the value of the pressure potential in the stem storage compartment, the stem diameter variation resulting from turgor-driven growth is included. 

> A tutorial on the application of the STACI model can be downloaded [here](https://github.com/deep-org/workshop_data/raw/master/esa-workshop2020/PhytoSim/ESA2020_PhytoSim.zip).


![](/docs-workshops/esa-workshop2020/03_phytosim_files/staci.png)

**Figure:** *The scheme and mathematical equations of STACI. See References for sources.*

## 3. Beyond the simulations

Dendrometer-sap flow combinations can be successfully used in monitoring networks, such as [TreeWatch.net](https://treewatch.net), which is a tree water and carbon monitoring network to assess instant tree hydraulic functioning and stem growth via measurements and mechanistic modelling. 

This can be used to demonstrate the sensitivity of trees to changing weather conditions, such as drought, heat waves, or heavy rain showers. 

## 4. References

- Steppe K, Pauw DJW De, Lemeur R. (2008) A step towards new irrigation scheduling strategies using plant-based measurements and mathematical modelling. Irrigation Science 26: 505-517.
- Steppe K, Lemeur R, Vanrolleghem A. (2005) A mathematical model linking tree sap flow dynamics to dialy stem diameter fluctuation and radial stem growth. Tree Physiology 26: 257-273.
- Steppe K, Sterck F, Deslauriers A. (2015) Diel growth dynamics in tree stems: Linking anatomy and ecophysiology. Trends in Plant Science 20: 335-343.
- Steppe K, von der Crone JS, De Pauw DJW. (2016) TreeWatch.net: A Water and Carbon Monitoring and Modeling Network to Assess Instant Tree Hydraulics and Carbon Status. Frontiers in Plant Science 7: 1-8.



