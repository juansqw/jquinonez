---
title: "Inflation density forecast in the Dominican Republic"
author: "Juan Quinonez"
date: '2022-08-08'
output: html_document
bibliography: "bibliografia.bib"
slug: []
categories:
  - R
tags: []
excerpt: In recent years, the literature is pointing out that not only inflation trajectory is important, but also the uncertainty that surrounds inflation projections.
---

Ever since countries have adopted the Inflation Targeting Scheme for monetary policy, inflation and inflation forecast has played a central role for central banks. In recent years, the literature is pointing out that not only inflation trajectory is important, but also the uncertainty that surrounds inflation projections.

Hall and Mitchell (2007) and other authors (Rossi (2014)) propose the use of **fancharts** to show the central path of forecast, but also the uncertainty of these projections (on shaded areas).

![Fanchart example. Taken from Quinonez and Ramirez (2020)](fanchart.png)

In [this document](https://cdn.bancentral.gov.do/documents/trabajos-de-investigacion/documents/coleccion_ensayos_vol_xiv_no2.pdf?v=1655153256246), my dear friend Nerys and I use a normal density function, with asymmetry and changing variance in time to obtain the density of the inflation forecast and the uncertainty related to the historic forecast error on different horizons.

## Bibliography

<div id="refs" class="references csl-bib-body hanging-indent">

<div id="ref-HALL20071" class="csl-entry">

Hall, Stephen G., and James Mitchell. 2007. “Combining Density Forecasts.” *International Journal of Forecasting* 23 (1): 1–13. https://doi.org/<https://doi.org/10.1016/j.ijforecast.2006.08.001>.

</div>

<div id="ref-QuiRa2020" class="csl-entry">

Quinonez, Juan, and Nerys Ramirez. 2020. “Inflation Density Forecast in the Dominican Republic.” *Oeconomia* 14 (2): 20–30. <https://cdn.bancentral.gov.do/documents/trabajos-de-investigacion/documents/coleccion_ensayos_vol_xiv_no2.pdf?v=1655153256246>.

</div>

<div id="ref-Rossi_densityforecasts" class="csl-entry">

Rossi, Barbara. 2014. “Density Forecasts in Economics, Forecasting and Policymaking.”

</div>

</div>
