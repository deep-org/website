---
title: Reproducible and interactive processing with datacleanr
authors:
  - ahurley
date: '2020-11-23'
slug: datacleanr-intro
categories:
  - Data Handling
tags:
  - Tutorial
subtitle: 'something'
summary: 'something more'
lastmod: '2020-11-23T15:04:33+01:00'
featured: no
image:
  caption: 'Image credit: **A. Hurley**'
  focal_point: ""
  placement: 1
  preview_only: false
projects: []
---






# Background






<!-- [![](https://cranlogs.r-pkg.org/badges/datacleanr)](https://cran.r-project.org/package=datacleanr) -->


# About `datacleanr`

Here we introduce `datacleanr`, a recently developed app.
Itis a flexible and efficient tool for **interactive** data cleaning, and is inherently interoperable, as it seamlessly integrates into **reproducible** data analyses pipelines in `R`.
It can deal with nested **tabular**, as well as **spatial** and **time series** data.
We present how to use the app and show two use-cases - one for processing **wood anatomical data** and one for environmental data (soil respiration - `\(CO_2\)` flux).
Detailed documentation and examples can be found [here](https://the-hull.github.io/datacleanr) on the app's website.

# Installation 

The latest release on CRAN can be installed using:


```r
# also installing dplyr for later use
packages <- (c("datacleanr", "dplyr", "RAPTOR"))
install.packages(setdiff(packages, 
                         rownames(installed.packages())))

library(datacleanr)
library(dplyr)

```


You can install the development version of `datacleanr`  with:


```r
packages <- (c("remotes"))
install.packages(setdiff(packages, 
                         rownames(installed.packages())))

remotes::install_github("the-hull/datacleanr")
```

# Design and features

`datacleanr` is developed using the [shiny](https://shiny.rstudio.com/) package, and relies on informative summaries, visual cues and interactive data selection and annotation.
All data-altering operations are documented, and converted to valid `R` code (**reproducible recipe**), that can be copied, sent to an active `RStudio` script, or saved to disk.

The documentation for the app (`?dcr_app()`) explains the basic use and all features.
Throughout the app, there are conveniently-placed help links that provide details on features.


There are **four tabs** in the app for these tasks:

- **Set-up & Overview**: define nesting structure based on (multiple) groups.
- **Filtering**: use `R` expression to filter/subset data.
- **Visual Cleaning and Annotating**: generate bivarirate (time series) plots and maps, as well as highlight and annotate individual observations. Cycle through nested groups to expedite exploration and cleaning. Histograms of original vs. 'cleaned' data can be generated.
- **Extract**: generate reproducible recipe and define outputs. **`dcr_app` also returns all intermediate and final outputs invisibly to the active `R` session for later use (e.g. when batch processing)**

Note, maps require columns `lon` and `lat` (X and Y) in decimal degrees in the data set to render.

## Additional features

- **Grouping**: the grouping defined in the "Set-up and Overview" tab is carried forward through the app. These groups can be used to cycle through nested/granular data, and considerably speed up exploration and cleaning. These groups are also available for filtering (Filtering tab), where filter expressions can be scoped to group level (i.e. no groups, individual, all groups).
- **Interoperability**: 
  when a logical (`TRUE`\\`FALSE`) column named `.dcrflag` is present, corresponding observations are rendered with different symbols in plots and maps. Use this feature to validate or cross-check external quality control or outlier flagging methods.
- **Batching**:
  If data sets are too large, or too deeply nested (e.g. individual, plot, site, region, etc.), we recommend a split-combine approach to expedite the processing. 
  

```r
iris_split <- split(iris, iris$Species) 

output <- lapply(iris_split, 
       dcr_app)

```
  


# Using `datacleanr` with Wood Anatomical Measurements

`RAPTOR` is a powerful tool to assimilate and generate cell-level measurements of coniferous, woody plants. 
It will serve as the basis to generate a dataset, which we will subsequently clean. 
More details on `RAPTOR` can be found in [Peters *et al.* (2018)](https://doi.org/10.1016/j.dendro.2017.10.003) and in the dedicated DEEP tutorial [here](/2020/11/23/raptor-intro/).

First, we 


```r

library(RAPTOR)

# grab example data
input <- is.raptor(example.data(species = "MOUNT_PINUS"),
                   str = FALSE)
# rotate annual rings where necessary
# so that detection algorithms can operate seamlessly
aligned <- align(input, 
                 list = c("h", "h", "h", 0.03),
                 make.plot = FALSE)

# identify first cell in every annual ring
first <- first.cell(aligned,
                    frac.small = 0.2,
                    yrs = FALSE, 
                    make.plot = FALSE)

# identify all cells along radial files,
# starting from first cells
output <- pos.det(first,
  swe = 0.7, sle = 3, ec = 1.75, swl = 0.5, sll = 5, lc = 10,
  prof.co = 1.7, max.cells = 0.7, yrs = FALSE, aligning = FALSE, make.plot = TRUE
)

```

The `output` can be used directly in `datacleanr`, but a few additional steps make the subsequent processing considerably more efficient.
Through `RAPTOR`'s alignment process, all rings are assumed to originate on a planar coordinate system at `(0,0)`,
causing overlap during plotting.
We will add space out the individual rings, and add factors for grouping, which will be used to visualize years and rows individually.


```r

# grab maximum YCAL location and add a buffer for convenience
# this is used to space out rings below
buffer <- 100
max_ring_size <- output %>% 
  group_by(YEAR) %>% 
  summarize(max_length = max(YCAL, na.rm = TRUE) + buffer) %>% 
  mutate(cumulative_year_length = cumsum(max_length))

output_dcr <- output %>% 
  left_join(max_ring_size) %>% 
  mutate(YEAR_dcr = as.factor(YEAR),
         # leverage RAPTOR's row identification
         ROW_dcr = as.factor(ifelse(is.na(ROW), "00",ROW )),
         # space out overlapping rings
         YCAL_dcr =  YCAL + cumulative_year_length)

datacleanr::dcr_app(output_dcr)

```



# Using `datacleanr` with Environmental Data: Soil Respiration



**COSORE** is a community-driven soil respiration database, recently introduced with a manuscript published [here]( https://doi.org/10.1111/gcb.15353) by Bond-Lamberty *et al.*.
The database provides soil respiration flux estimates, as well as meta data across multiple data sets. 
Let's explore!



```r


remotes::install_github("bpbond/cosore")
library(dplyr)

# check data base info
db_info <- cosore::csr_database()
tibble::glimpse(db_info)

# grab one data set and explore in detail
dset <- "d20190409_ANJILELI"
anjilleli <- cosore::csr_dataset(dset)
tibble::glimpse(anjilleli$description)


datacleanr::dcr_app(anjilleli$data)
```
<img src="https://raw.githubusercontent.com/the-Hull/datacleanr/master/man/figures/readme_cosore_single.gif" width = "1000" align = "center"/>



**Explore nested data sets**:


```r
# grab all data from ZHANG
zhang <- cosore::csr_table("data", c("d20190424_ZHANG_maple",
                                        "d20190424_ZHANG_oak")) %>%
  # adjust for grouping
  mutate(CSR_PORT = as.factor(CSR_PORT))

# group by CSR_DATASET and CSR_PORT
datacleanr::dcr_app(zhang)

```

<img src="https://raw.githubusercontent.com/the-Hull/datacleanr/master/man/figures/readme_cosore.gif" width = "1000" align = "center"/>


