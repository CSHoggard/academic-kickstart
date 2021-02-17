---
title: William Morris palettes for the R Environment (morris)
subtitle: 🎨 Six new colour schemes for the tidyverse 🎨

# Summary for listings and search engines
summary: Welcome 👋 We know that first impressions are important, so we've populated your new site with some initial content to help you get familiar with everything in no time.

# Link this post with a project
projects: []

# Date published
date: "2020-12-13T00:00:00Z"

# Date updated
lastmod: "2020-12-13T00:00:00Z"

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Image credit: [V&A Museum](https://collections.vam.ac.uk/item/O78889/strawberry-thief-furnishing-fabric-morris-william/)'
  focal_point: ""
  placement: 1
  preview_only: false

authors:
- admin

tags:
- morris
- rstats

categories:
- morris
- rstats
---

# The morris package

The package provides a number of palettes for ggplot2 inspired by the British textile designer, poet, novelist and activist [William Morris](https://en.wikipedia.org/wiki/William_Morris). William Morris (1834-1896) was a major contributor to the revival of traditional British textile arts and is best associated with the [British Arts and Crafts movement](https://en.wikipedia.org/wiki/Arts_and_Crafts_movement). Rooted in the [Modern Style (British Art Nouveau)](https://en.wikipedia.org/wiki/Modern_Style_(British_Art_Nouveau_style)), the Arts and Crafts movement was known for traditional craftsmanship, often using medieval, romantic and folk styles of decoration. Known for its advocation of economic and social reform, the movement was strongly anti-industrial, and prior to the 1930s had a strong influence on the arts in Europe. 

{{< figure src="https://raw.githubusercontent.com/CSHoggard/morris/main/readme_files/comparison.png" title="Left: Acanthus (1875). V&A Museum no. E.496-1919 [V&A Museum](https://collections.vam.ac.uk/item/O78222/acanthus-wallpaper-morris-william/). Right: Colour breakdown tables (extracted using functions in the `magick` and `imager` packages)" >}}


# Installation  

Please use the `devtools` package in order to install `morris`.

``` r
devtools::install_github("cshoggard/morris")
```

A further five of William Morris' most famous works are included:  

**Strawberry Thief** (1883). V&A Museum no. T.586-1919.  

<img src="https://raw.githubusercontent.com/CSHoggard/morris/main/readme_files/st.jpg" width="400" />  

``` r
scales::show_col(morris:::strawberry_palette)
```

<img src="https://raw.githubusercontent.com/CSHoggard/morris/main/readme_files/strawberry_chart.jpeg" width="700" />  

**Trellis** (1864). V&A Museum no. E.452-1919.  

<img src="https://raw.githubusercontent.com/CSHoggard/morris/main/readme_files/t.jpg" width="400" /> 

``` r
scales::show_col(morris:::trellis_palette)
```  

<img src="https://raw.githubusercontent.com/CSHoggard/morris/main/readme_files/trellis_chart.jpeg" width="700" /> 

**Holland Park** (1883). Met Museum no. 27.139.3.  

<img src="https://raw.githubusercontent.com/CSHoggard/morris/main/readme_files/hp.jpg" width="400" /> 

``` r
scales::show_col(morris:::holland_palette)
```

<img src="https://raw.githubusercontent.com/CSHoggard/morris/main/readme_files/holland_chart.jpeg" width="700" />  

**Peacock and Dragons** (1878). WMG no. F26e.  

<img src="https://raw.githubusercontent.com/CSHoggard/morris/main/readme_files/pd.jpg" width="400" />  

``` r
scales::show_col(morris:::peacock_palette)
```

<img src="https://raw.githubusercontent.com/CSHoggard/morris/main/readme_files/peacock_chart.jpeg" width="700" />  

**Embroidery with Flowers and Leaves (Leek Embroidery Society)** (1885-1895). Rijksmuseum no. BK-1994-28.  

<img src="https://raw.githubusercontent.com/CSHoggard/morris/main/readme_files/fl.jpg" width="400" />  

``` r
scales::show_col(morris:::flowers_palette)
```

<img src="https://raw.githubusercontent.com/CSHoggard/morris/main/readme_files/flowers_chart.jpeg" width="700" /> 

  
## An example:

``` r
library(tidyverse)
#> -- Attaching packages ------------------------------------------------ tidyverse 1.2.1 --
#> v ggplot2 3.1.0       v purrr   0.3.0  
#> v tibble  2.0.1       v dplyr   0.8.0.1
#> v tidyr   0.8.2       v stringr 1.4.0  
#> v readr   1.3.1       v forcats 0.4.0
#> -- Conflicts --------------------------------------------------- tidyverse_conflicts() --
#> x dplyr::filter() masks stats::filter()
#> x dplyr::lag()    masks stats::lag()
library(morris)
library(palmerpenguins)
library(extrafont)
#> Registering fonts with R
```  

``` plot
loadfonts(device = "win")

theme_set(theme_minimal(base_size = 12, base_family = "Lato"))

penguins %>%
  ggplot(aes(flipper_length_mm, body_mass_g, shape = species, colour = species)) +
           geom_point(size = 3) +
  scale_colour_flowers() +
  labs(title = "Penguin Mass vs. Flipper Length",
       x = "Flipper Length (mm)", 
       y = "Body Mass (g)",
       shape = "Species",
       colour = "Species") +
  theme(plot.title = element_text(size = 18, hjust = 0.5, margin = margin(0,0,20,0)),
        legend.position = "bottom")
```

<img src="https://raw.githubusercontent.com/CSHoggard/morris/main/readme_files/Example.png" width="1200" />  



