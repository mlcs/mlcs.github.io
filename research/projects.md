---
layout: page
title:
subtitle:
use-site-title: false
---
![MLCS-Logo](/img/mlcs_logo_small.png){: .center-block :}

***

We currently have two doctoral projects and a third one that will start
in Fall of 2021. Additionally, we have a couple of undergrad projects
and a third one set to start in spring. Below we provide brief summaries
of these projects going on the group.

[Doctoral Projects](#doctoral-projects)  
[Masters projects](#masters-projects)  
[Bachelors projects](#bachelors-projects)  

***

## Doctoral projects

### Predicting Sea Surface Temperature Patterns in the Pacific Ocean
#### [Jakob Schlör](https://machineclimate.de/people/schloer/)

The most dominant mode of oceanic climate variability on an interdecadel
scale is the El Niño Southern Oscillation (ENSO). ENSO events are
characterized by the anomalous sea surface temperatures (SSTs) in the
equatorial Pacific. Large anomalies in this region are known to have
high impact on global climate, as for instance, intense rainfall over
Peru and droughts and wildfires in Northern Australia during the ENSO
warm phase, known as El Niño. Although ENSO is an important climate
phenomena, its cause and variability is not yet fully understood, which
makes it hard for climate models to capture and predict its occurrence.
In this project, we aim to forecast the equatorial SST anomaly patterns
in the Pacific based on a data driven approach used together with
probabilistic generative models (PGMs). PGMs allow us to make spatial
and temporal predictions with uncertainties as well as reveal insights
into underlying drivers of the modeled phenomenon. Our final goal is to
be able to provide local SST forecasts from a global perspective.

![SSTA-2016](/img/ssta_elnino_2016.png){: style="float: right"}


### Analyzing the Monsoon Dynamics by Complex Networks
#### [Felix Strnad](https://machineclimate.de/people/strnad/)

Analyzing rainfall events reveals areas on every continent that reveal
similar behaviour: Heavy rainfalls during metereological summer and
drier conditions during metereological winter. These areas are labelled
as monsoon systems. In the last years, the phenomena has emerged as the concept of the Global Monsoon (GM), a global-scale solstitial mode that drives the annual variation of
tropical and subtropical precipitation. However, its underlying
dynamical behavior and interconnections to other global scale weather
systems is so far not fully understood.  We want to investigate the
dynamics of the GM via methods from complex network analysis and
Bayesian Inference. By better understanding the common/different
variabilities in monsoon dynamics we hope to provide reliable estimates
of the consequences of global climate change to the monsoon system. 
Complex Climate Networks of extreme rainfall events can tell us a lot about synchronization of rainfall events over long-range spatial  distances. We use it to better understand the physical mechanisms behind these long-range spatial teleconnections.

![GM-def](/img/climate_network_links.png){: .center-block :}


### Seasonal weather forecasts using deep learning
#### [Jannik Thümmel](https://machineclimate.de/people/thuemmel/)

Atmospheric processes are highly non-linear and chaotic rendering long-term
forecasts of their dynamics impossible. However, there exist recurring
patterns in the climate system that lead to predictable tendencies in weather.
These patterns are termed teleconnections for their effects on distant regions
of the planet. Well-known examples include the El-Nino-Southern-Oscillation,
the Northern-Atlantic-Oscillation and the Madden-Julian-Oscillation, which
occur on annual (ENSO), seasonal (NAO) and sub-seasonal (MJO) temporal scales.
Teleconnections are known to be a significant driver of weather patterns and
could be exploited to generate predictions of weather trends far beyond the
forecast horizon of atmospheric models. Machine Learning is ideally suited to
identify subtle patterns in complex data and exploit these patterns to
generate predictions. Therefore the aim of our project is to develop machine
learning systems that are able to identify teleconnection patterns from data
and generate skillful predictions at time scales that are difficult to model
with numerical methods. We are looking to design neural network architectures
that incorporate physical knowledge as inductive biases and that are capable
of modeling the effects of teleconnections across large spatial and temporal
scales.


### Pitfalls and possible improvements in climate networok construction
#### [Moritz Haas](https://machineclimate.de/people/haas/)

![Network-Measures](/img/mh_project_figure.jpg){: .center-block :}

Empirical distributions of node-wise network characteristics using Pearson
correlation (common for climate networks) for data generated from a Matern
isotropic Gaussian random field. Dotted lines denote the ground truth
distributions. In the regime of scarce data (in time), the empirical networks
have systematically distorted characteristics compared to the ground truth,
where the shortest links are formed.

## Masters Projects

### Explainable community structure in climate networks
#### [Merle Kammer](https://machineclimate.de/people/kammer/)

Climate networks have helped to uncover complex structures in climatic
observables.  For instance, climate networks were used to reduce rainfall data
to relevant patterns that can be linked to geophysical processes. However, the
identification of regions that show similar behavior with respect to the
timing and spatial distribution of extreme rainfall events (EREs) remains
challenging. We want to apply a recently developed algorithmic framework based
on tangles to discover community structures in the spatial distribution of
EREs. Tangles enables us to create a hierarchical tree representation of
communities including the likelihood that spatial locations belong to a
community. Each tree layer can be associated to a closed question, thus making
the division of different communities transparent.  Applied to global
precipitation data, we hope that tangles is a promising tool to quantify
community structures and to reveal underlying geophysical processes leading to
these structures.

![Hard-Clustering](/img/mk_project_figure.jpg){: .center-block :}


### Parameter inference and uncertainty quantification for an intermediate complexity climate model
#### [Benedict Roeder](https://machineclimate.de/people/roeder/) (Master's Thesis)

Well-adapted parameters in climate models are essential to make accurate
predictions for future projections.  In climate science, the record of precise
and comprehensive observational data is rather short and parameters of climate
models are often hand-tuned or learned from artificially generated data.  Due
to limited and noisy data, one wants to use Bayesian models to have access to
uncertainties of the inferred parameters.  Most popular algorithms for
learning parameters from observational data like the Kalman inversion approach
only provide point estimates of parameters.  In this work, we compare two
Bayesian parameter inference approaches applied to the intermediate complexity
model for the El Niño-Southern Oscillation by Zebiak & Cane.  i) The
"Calibrate, Emulate, Sample" (CES) approach, an extension of the ensemble
Kalman inversion which allows posterior inference by emulating the model via
Gaussian Processes and thereby enables efficient sampling.  ii) The
simulation-based inference (SBI) approach where the approximate posterior
distribution is learned from simulated model data and observational data using
neural networks.  We evaluate the performance of both approaches by comparing
their run times and the number of required model evaluations, assess the
scalability with respect to the number of inference parameters, and examine
their posterior distributions.

![ENSO-Model](/img/roeder_project_figure.jpg){: .center-block :}


### Spatiotemporal patterns of European heatwaves and their influence on vegetation
#### [Julia Hellmig](https://machineclimate.de/people/hellmig/)

Heatwaves are extreme events that have the potential to cause deaths,
agricultural loss and damage ecosystems. With anthropogenic climate change,
heatwaves have been shown to occur more often already and are suspected to
become even more frequent in the future. Especially Europe is a heatwave
epicenter, with mega-heatwaves in 2003, 2010 and 2018 just to name a few.
This project aims to analyze spatio-temporal patterns of European heatwaves
with the graphs framework Deep Graphs. We try to cluster Euopean heatwaves
spatially and temporally, in order to find distinct heatwave families. We
suggest that heatwaves within one family might be caused by the same
atmospheric regime. In the long run this approach could be a first step to
better predict heatwave in the future.  A second part of the project analyzes
the influence of heatwave families and individual heatwaves on vegetation. We
expect to see differences in the influence of extreme heat on vegetation at
different locations in Europe.

![Scandi-Heatwave](/img/jh_project_figure.jpg){: .center-block :}


### Spatiotemporal analysis of extreme rainfall clusters over North Indian Ocean
#### [Ranganatha B R](https://machineclimate.de/people/ranganatha/)

The project aims at studying tropical cyclones and their tracks using
precipitation data. The statistical analysis of the storm tracks
constructed using Deepgraphs allows us to differentiate between different
physical phenomena which are different over land and ocean. Further, the
tracks exhibit a pattern that can be studied using Machine Learning which
can help us be well prepared for future heavy precipitation events like
tropical cyclones and depressions. Since Long Short Term Memory (LSTM) is a
special kind of Recurrent Neural Network that can learn sequence data much
more efficiently than other deep learning methods, we use them to predict
future track. We use different models with varying inputs to efficiently
predict the storm track. Successful training of these models validates the
existence of a storm track pattern in the North Indian Ocean along with the
proof of the concept that tropical cyclones can be studied under the banner
of extreme precipitation.

![Storm-Tracks](/img/rbr_project_figure.jpg){: .center-block :}



## Bachelors Projects

### Machine Learning Methods to Model Monthly Precipitation over Southern Europe Using Climate Indices

#### [Davide Lussu](https://machineclimate.de/people/lussu) (Bachelor's Thesis)

The Mediterranean region is one of the regions most strongly affected by
climate change. A decline in precipitation is observed in the region with
consequences for agriculture and water resources.  Various atmospheric modes
such as the North Atlantic Oscillation impact the precipitation in this
region. Indices measuring the pressure difference between two locations to
describe these oscillating modes can be correlated to the precipitation.  This
project explores different statistical machine learning methods to describe
precipitation based on the Oscillation Indices. Regression is performed on
timeseries of all indices to model precipitation provided by the ERA5 monthly
precipitation dataset spanning over the past 40 years. The methods used are
basic Linear Regression, a Random Forest Regressor and an Artificial Neural
Network (ANN) which are fitted to the time series on each location on the map.
Also a further ANN approach is tested that uses all time series with added
coordinates as an input for training

![DL-Project](/img/dl_project_figure.png){: .center-block :}

### Impact of strong El Niño events on river discharge in South America 
#### [Markus Deppner](https://machineclimate.de/people/deppner/) (Bachelor's Thesis)

The El Niño Southern Oscillation (ENSO) is one of the most influential
climate patterns in terms of climate variability around the globe and
yet all its impacts are not fully understood. This project investigates
the magnitude of El Niño (EN)  events on river discharge in South
America as EN-related floods can cause ecological, economical and
social problems in many regions around the continent. By applying
machine learning techniques on the “Global Streamflow Indices and
Metadata archive” (GSIM) we plan to extend the amount of in situ
stations for a 40 year timespan by almost three-fold. The idea is to
infer  missing streamflow data by using the temporal correlations of
stations with missing values to others with data. This approach provides
a possible solution for the problems of scattered data and in situ
stations temporarily fading in and out, which makes large-scale
hydrological research challenging.

![DISCH-SA](/img/discharge_stations_southamerica.png){: .center-block :}
