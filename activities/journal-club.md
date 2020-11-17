---
layout: page
title:
subtitle:
use-site-title: false
---
![MLCS-Logo](/img/mlcs_logo_small.png){: .center-block :}

# Journal Club

This is a summary of the [Machine Learning for Climate
Science](https://mlcs.github.io) group journal club. It is mainly
intended for internal use but can also be seen as our paper review.
Currently our Journal Club takes place every Tuesday at 1 pm CEST. Since
beginnning of November, it is done entirely online on Zoom:

**Topic:** MLCS Journal Club  
**Time:** Tuesdays, 1 pm CEST  
**Join Zoom Meeting:** https://zoom.us/j/93600491273  
**Meeting ID:** 936 0049 1273  

***

## Upcoming
+ **17 November 2020**  
[Wang, Chen, Liu, Sci Adv,
2019](https://dx.doi.org/10.1126/sciadv.aax0220) to be presented by
Felix S.  
+ **24 November 2020**  
[Pante, Knippertz, Nature Comms,
2020](https://doi.org/10.1038/s41467-019-11081-4) to be presented by Lea
E.  
+ **1 December 2020**  
[Yang et al., Environ Res Lett,
2019](https://doi.org/10.1088/1748-9326/ab5c6f) to be presented by
Markus D.  
+ **8 December 2020**  
[Hegerl et al., Environ Res Lett,
2019](https://doi.org/10.1088/1748-9326/ab4557) to be presented by
Bedartha G.  

***

## Past meetings

[01.09.20 - Petersik et al. (2020) Probabilistic ENSO Forecasting](#01092020)\
[02.09.20 - Renard et al. (2019) Hidden Climate Indices for Floodings](#02092020)\
[03.09.20 - Rasp et al. (2018) NN for learning subgrid proecesses](#03092020)\
[04.09.20 - Rasp et al. (2020) Data-driven medium range weather forecasting](#04092020)\
[09.09.20 - Datasets, benchmarks and scores](#09092020)\
[15.09.20 - Houze et al. (2015) TRMM dataset summary](#15092020)\
[22.09.20 - Presentation of research ideas](#22092020)\
[28.09.20 - Talk: Climate Change are we up for the Challenge](#28092020)\
[05.10.20 - Deser et al. (2017) ENSO variability](#05102020)\
[13.10.20 - Schneider et al. (2014) Migrations and dynamics of ITCZ](#13102020)\
[27.10.20 - Papagiannopoulou (2018) Hydro-climatic biomes via multitask learning](#27102020)\
[28.10.20 - Ding (2005) Circumglobal Teleconnection in the NH Summer](#28102020)\
[03.11.20 - Hoskins (2020) The detailed dynamics of the June–August Hadley Cell](#03112020)
[10.11.20 - DiNezio (2020) Emergence of an equatorial mode in the Indian Ocean](#10112020)


***


### 01.09.2020

**Petersik 2020: Probabilistic forecasting of El Nino using NN Models**

ENSO forecasting using Gaussian density neural networks (GDNN) and
Quantile Regression Neural Networks (QRNN).
-   GDNNs outperform QRNN because prior assumptions on distribution
    compensate for small dataset
-   high prediction skill by using few variables (ONI, WWV, DMI, zonal
    wind stress anomaly, metric of ECNS)

Model:
-   GDNN: ensemble of multilayer perceptrons with mean and variance
    output nodes
-   QRNN: predicts the location of a quantile
-   Regularization by dropout and early stopping
-   output of the models are the ONI for lead time

Predictor Variables:
-   Oceanic Nino Index (ONI): 3 month running average of SST anomaly in
    NINO 3.4 region
-   WWV: volume of water at 20\(^\circ\)C isotherm
-   Dipole Mode Indes (DMI): difference between the monthly
    area-averaged SSTA of the western and southeastern equatorial Indian
    Ocean
-   zonal wind stress anomaly in the western Pacific
-   ECN

Results:
-   Anomaly correlation coefficient (ACC): Pearson correlation between
    predicted mean and observed ONI
-   Quantile skill score (QSS): positive QSS indicates that the model is
    better than the reference
-   For El Nino time periods ACC have weak seasonal variation in
    contrast to La Nina
-   GDNN outperforms QRNN in ACC and QSS

Questions and Critics:
-   importance of parameters for the prediction (heat map)
-   evaluation of input variables, e.g. start with 20 adhoc predictors
    and reduce them by tracking prediction quality
-   weak discussion of uncertainties
-   correlation ACC do not predict absolute values of ONI
-   humming distance: normalized missing links in network
-   La nina is usually better predicted than El nino, which is in
    contrast to Fig. 2

[Back to top](#journal-club)


### 02.09.2020

**Renard 2019: Hidden Climate Indices from Occurances of Hydrologic Extremes**

Develop a probabilistic model with a set of latent variables which is
used to describe temporal and spatial extreme precipitation. The learned
latent variables are called hidden climate indices (HCIs) which show
correlation to climate variables in some cases.
-   avoid relying on standard climate indices, which might be poor
    predictors
-   showing method on synthetic case, Australian coast line (ENSO
    dependent) and floods in France

Method:
-   Occurrences of event are described by Bernoulli distribution
-   spatial parameters are multivariate Gaussian distributions
-   conditional independence between parameters in space and time
-   stepwise Bayesian inference using adaptive MCMC
-   similar method that probabilistic PCA

Case studies and results:

-   Synthetic data are well described by model even with missing data,
    standard effect of hidden variables show significance
-   Eastern Australian spring floods are described by K=3 HCIs, where
    the first HCI correlates with the NINO4 index
-   Autumn floods in France are also well described by the model with
    K=6 HCIs. The HCIs do not correlated to standard climate indices.
    The first index slightly correlates with large convection in the
    north of France and strong winds in the south of France.

Improvements:
-   include interactions between parameters of HCIs
-   go beyond linear time or space behaviour

Discussion:
-   comparison to correlation network for teleconnections
-   how many parameters to choose
-   PDO and NAO are indices which result of PCA
-   ONI is a three month average of Nino3.4, adapted ONI with thirty
    year average of temperature
-   main message: creating time series from discrete occurance extreme
    events
-   extreme value distributions: maximum of each block in a time series
    (used in hydrology for the worst floods)

[Back to top](#journal-club)


### 03.09.2020

**Rasp 2018: Deep learning to represent subgrid processes in climate models**

[https://www.pnas.org/content/115/39/9684](https://www.pnas.org/content/115/39/9684)

The computational expensive cloud resolving model, SPCAM, is surrogated
by training a deep neural network (NNCAM).
-   Once trained, the NNCAM runs 20 times faster
-   The NNCAM captures the mean climate well
-   NNCAM learned to conserve energy
-   The network is able to interpolate between different temperature
    scenarios but fails on extrapolation
-   NNCAM outperforms a parametrized surrogate model, CTRLCAM

[[images/Rasp2019.JPG]]

**Method:**
-   NN with 9 layers and 256 nodes per layer
-   dimension of data point: x=94, y=65 with 140 mio training points

**Question and Discussion:**
-   CTR is the control/base line model
-   pressure is exponential height
-   related field: using NN for downscaling, i.e. form course to fine scale
-   related work: intra day extreme precipitation [Mishra
    2018](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2018GL078689)

[Back to top](#journal-club)

### 04.09.2020

**Rasp, Thuerey 2020: Purely data-driven medium-range weather
forecasting achieves comparable skill to physical models at similar
resolution**

[https://arxiv.org/pdf/2008.08626.pdf](https://arxiv.org/pdf/2008.08626.pdf)

**Discussion:**
- input data 240 000 values at each time point (maybe three time steps) 
- course grid of appox. 360km
- ERA5 has a resolution of 0.25 degree (you can download even finer grid
  from ERA, probably interpolated)
- running average over the year and plot variance 
- seasonality may also play a role (same apply for long range phenomena,
  e.g. ENSO, where other periodic phenomena play a role)
- gradients are in respect to time (i.e. sample direction)
- median would be more expressive to capture extreme events

**Idea which came up:**

Course grain the input at the lat/lon nodes by a correlation matrix to
create an adjacency matrix. This would reduce dimension to relevant
correlations to before feeding into an ML algorithm for e.g. ENSO
prediction.  This would reduce the input to relevant patterns that any
ML approach must anyway recognize.

Ideas how to proceed are:

- set a value threshold in adjacency matrix to reduce input data for
  each lead-time
- do this for a set of input variables (SST, precipitation, windspeed at
  different pressure levels...) 
- combines climate networks with learning algorithms
- Compare to NN which gets not processed input data. NN might learn the
  same thing. Either way would be interesting. 
- [Rheinwalt2015](https://www.researchgate.net/profile/Aljoscha_Rheinwalt/publication/300285664_Teleconnections_in_Climate_Networks_A_Network-of-Networks_Approach_to_Investigate_the_Influence_of_Sea_Surface_Temperature_Variability_on_Monsoon_Systems/links/59772b83a6fdcc8348b175cd/Teleconnections-in-Climate-Networks-A-Network-of-Networks-Approach-to-Investigate-the-Influence-of-Sea-Surface-Temperature-Variability-on-Monsoon-Systems.pdf)

[Back to top](#journal-club)

### 09.09.2020

**Datasets, Benchmarks, Scores and Metrics**

**Benchmarks:** <https://www.overleaf.com/8663366341vrwmtgrqrxks>
1. benchmark for algorithms
> - algorithm should not over or under fit 
> - key question (of a scientific domain) with respect to a particular algorithm

2. benchmark for datasets/problem
> - Properties: domain specific problem, not easily solvable, naive solution is not satisfying, baseline or ground truth
> - key question of a scientific domain which is closely related to a specific dataset
> - [Uphoff2020] website to store benchmark climate datasets


- Problems/Tasks are benchmarks which are either related to datasets or
  algorithms
- Api/features of the benchmark task should be formulated from the
  domain scientists (quantitative quantifiers should be left open)
- In climate science: tasks are usually with respect to dataset where
  the new approach/model should be better than existing methods
- Dimensions of quantifiers: computational speed and memory, accuracy,
  scale ability

**Scores**: [Prediction scores and metrics](scores_metrics)
- idea to sort metrics or errors by their property, i.e. Markov property
  for time-series
- significance tests are only used by statisticians (literature from
  Alvarez)
- ACC: <img
  src="https://render.githubusercontent.com/render/math?math=\large
  \bar{c}_i"> could be inferred from the data by using a bayesian
  structural model
- idea to use relational-databases to sort tasks, datasets, papers and
  scores (notion.so, airtable)

**Research Ideas**:
- Formulate: research question, dataset and method
- think about possible results (hypothesis)
- make a timeline/plan including bottlenecks

[Back to top](#journal-club)


### 15.09.2020

**Houze 2015: The variable nature of convection in the tropics and
subtropics A legacy of 16 years of the Tropical Rainfall Measuring
Mission satellite**

[https://agupubs.onlinelibrary.wiley.com/doi/abs/10.1002/2015RG000488](https://agupubs.onlinelibrary.wiley.com/doi/abs/10.1002/2015RG000488)

Summary of precipitation and convection patterns over the globe which
are obtained by precipitation radar of the Tropical Rainfall Measuring
Mission (TRMM). Convection systems have different types which cannot be
viewed as a single kind of entity.  

Discussion:
- GPM dataset is an extension of the TRMM dataset which reaches further
  to the poles
- TRMM dataset on precipitation is thus preprocessed
- Stratiform and convective clouds are different in their vertical
  latent heat profile, shallow and tall, respectively
- Convection systems and thus extreme rain might have different physical
  origin (DCC or WCC)
- [Traxl2016](https://aip.scitation.org/doi/10.1063/1.4952963) network
  in space time grouping extreme events
- Are extreme rainfall teleconnections different for these convection
  classes?
- Idea: Which features in terms of precipitation (e.g. extreme rainfall)
  corresponds to DCC and WCCs
- Idea: Scatter plot of p(DCC) and p(WCC) to see cluster and project
  them to real space instead of comparing maps


[Back to top](#journal-club)


### 22.09.2020

**Presenting Research Ideas**

Felix and Jakob where presenting a set of possible research ideas.

+ Felix's idea was related to the global monsoon
+ Jakob's idea was related to ENSO complexity prediction.


[Back to top](#journal-club)


### 28.09.2020

**Talk: Climate Change are we up for the Challenge**

Youtube lecture [Brian Hoskins - Climate Change are we up for the
Challenge](https://www.youtube.com/watch?v=fit76ptQBsg)

Notes:
- the earth without an atmosphere has temperature of -18 
- with greenhouse gases its 15 degree. The greenhouse gases are water
  vapour, carbon dioxide, methane
- Carbon dioxide measurements:
	> - 100t of CO_2 emitted now (2016)
	> - in 1000 years without any more emission 15 - 40 t will remain
- Global warming is not equally distributed, Northern hemishpere is
  stronger affected
- sea level change due to ice melting and water expansion
- no sea ice in summer in the mid century
- warmer atmosphere can hold more water thus, the number of extreme rain
  events increase (Clausius–Clapeyron relation)
- cyclones become stronger because warmer oceans give more energy to the
  winds
- Projections to the future 2081 - 2100 by 4 degree rise of GST (IPCC 2013)
	> - 11 degrees warmer over the landmass in the Northern Hemisphere 
	> - land ocean contrast would yield to new weather
	> - 1 m rise of water level
	> - Oceans change pH value
- Compensating Methods:
	> - Getting CO2 out of atmosphere
	> - Geoengineering
- Mitigation
	> - area under the curve as budget\\
- Challenge to society and politics
	> - Can we look beyond our own group
	> - CAn we look beyond the short term 
- Number/Measure for communication, number of aircondition, max
  temperatures
	

[Back to top](#journal-club)


### 05.10.2020 

**Deser et al. 2017**

[https://doi.org/10.1175/JCLI-D-16-0844.1](https://doi.org/10.1175/JCLI-D-16-0844.1)

Jakob S. presented the paper [Presentation Deser (2017)](/files/deser_2017.pdf)

Discussion:
- averaging already the DJF months loses a lot of information about the
  variability
- the assumption of interchangable ENSOs is not necessarily true and
  should be tested
- constructing all possible pairs of El Ninos and La Ninas and sample
  from them would possibly give a larger uncertainty (this would go
  beyond the interchangable ENSO) 


[Back to top](#journal-club)


### 13.10.2020 

**Schneider (2014) Migrations and dynamics of the intertropical
convergence zone**

[Schneider 2014](http://www.nature.com/doifinder/10.1038/nature13636)

Presentation by Lea:
- Give a definition of ITCZ 
- analysis of ITCZ migrates to warmer hemisphere
- energy flux are weak near the ITCZ
- definition of ITCZ by divergence of moist energy flux
- annual changes of ITCZ in the Indian Ocean is much stronger than in
  the Pacific and Antlantic which can't be explained by the energy flux
- ITCZ is found where the energy flux changes sign  
- moist static energy: the heat released by a air parcel when moved from
  some height to the upper atmosphere, i.e. the heat released when water
  vapour condensates (indicator of water vapour in an air parcel)
- model of div F = S - F - O 
> - O, F, S are measured 
- this allows to obtain the energy flux equator = ITCZ 
- northern shifted ITCZ over Pacific and Atlantic is due to the AMOC
- in the Indian Ocean the monsoon is likely to have an impact on ITCZ
  position
- From La Nina to El Nino the ITCZ moves southwards which is counter
  intuitive
> - explanation from ocean uptake which significantly decreases
- greenhouse warming in the Northern Hemisphere is stronger than in the
  Southern Hemisphere which leads to a movement of ITCZ to the NH

Discussion:
- moist static energy heat flux is obtained by an weighted integral of
  the wind fields over the pressure (weighted by the value of moist
  energy values) 
- the ITCZ influences the monsoon, its likely not the other way around
- the second maxima of precipitation south of the Equator in the Indian
  Ocean in JJA might be interesting to observe (Fig. 2 b)


[Back to top](#journal-club)


### 27.10.2020 

**Papagiannopoulou (2018) Global hydro-climatic biomes identified via
multitask learning**

[Papagiannopoulou 2018](https://doi.org/10.5194/gmd-11-4139-2018)

Markus D. presented the paper
[Presentation](/files/papagiannopolou_2018.pdf):


Aim: develope data driven approach to quantify the response of
vegetation to local climate variables

Discussion:
- comparing Granger causalities (like in Fig. 3) should be done using
  some statistical test
- including climate features in the multi task learning  model increases
  prediction stronger than in the single task learning model
- log scale for precipitation in the scatter plot would be better
- this method is well suited for high dimensional input clustering where
  standard methods, e.g. k-means, etc. are weak


[Back to top](#journal-club)


### 28.10.2020 

**Ding (2005) Circumglobal Teleconnection in the Northern Hemisphere
Summer**

[Ding 2005](https://doi.org/10.1175/JCLI3473.1)

Felix S. presented the paper [presentation](/files/ding_2005.pdf):

Ding and Wang show evidence that teleconnections in the Northern
Hemisphere are linked with each other during boreal summer and on
interannual variability. They term this connection as circumglobal
teleconnection (CGT) pattern.
- geopotential height: the height of one particular pressure, this is an
  intuitive variable for atmospheric flow 
- teleconnections their definition: relationship in the low-frequency
  variability by studying EOFs and look at their spatial regions
- circumglobal teleconnection is defined by positive correlation of
  maximum standard deviation of geopotential height, the maximum over
  India is used as an index CGTI
- the second EOF of geopotential height shows hight correlation to the
  CGT
- CGTI is correlaed to Indian Summer Monsoon but not to ENSO, the
  correlation between CGTI and ENSO is via ISM 
- two scenarios qualitatively explain the CGT:
> 1. anomaly height due to monsoon is transported by rossby waves
> 2. anomalous height above europe which is transported by rossby wave which gives a height above india


Discussion:
- connection between teleconnections defined as low-frequency
  variability of EOFs and climate network teleconnections is not fully
  clear [paper by Donges]
>- fuzzy network teleconnections may be similar to EOF teleconnections
>- both definitions are based on the correlation matrix
- CGT definition has got rising attention in 2020

[Back to top](#journal-club)


### 03.11.2020 

**Hoskins (2020) The detailed dynamics of the June–August Hadley Cell**

The paper [Hoskins 2020](DOI: 10.1002/qj.3702) was presented by Bedartha G.

Summary: \
Hoskins et al. examine the Hadley cell in JJA by observing the angular
momentum and vorticity. They show,that that tropical convections and
meridional circulations drive the Hadley Cell movement. Thus, the main
contribution to the summer (JJA) Hadley cell is from the Indian Ocean
and the west Pacific. Equatorial air movement from southern to northern
Hemisphere occurs in filaments in the upper troposphere. 


Observation variables:
- angular momentum
- absolute vorticity: vorticity with added earths rotation
- potential vorticity: vorticity on an isotropic surface


Take home message:
- Hadley cell in summer is really only one
- Hadley cell is not at all even around the globe (longitudes)
- vorticity is strongly related to convection


[Back to top](#journal-club)


### 10.11.2020 

**DiNezio (2020) Emergence of an equatorial mode in the Indian Ocean**

[DiNezio et al., Sci Adv, 2020](https://dx.doi.org/10.1126/sciadv.aay7684) to be presented by Jakob S.  
 
The presentation can be found [here](/files/DiNezio_2020.pdf).

**Summary:**

> Methods:
> 
> - Numerical simulations of past and future climate changes
> - Coupled Model Intercomparison Project 5 (CMIP5) run under "buisness as usual" high emission scenario
> > Only some models get the SST gradient changes in the IO correct
> - Analyze simulations of the Last Glacial Maximum (LGM) around 21000 years ago (CESM1)
> 
> 
> Results:
> 
> - IO normal conditions become more similar to the Pacific and Atlantic with westerly winds and shallower thermocline in the eastern IO
> - CMIP5 models predict increasing westerly winds with GHG
> - Under greenhouse warming and LGM the SST variability increases in the eastern equatorial IO (EEIO) 
> - This could lead to EEIO mode like in Atlantic and Pacific
> - Causation of the EEIO mode:
> > 1. Equatorial winds become more easterly
> > 2. Increased upwelling and eastward shoaling thermocline in JAS
> > 3. Self enhancing effect known as Bjerknes atmospheric-oceanic feedback
> > -> Development of SSTAs in EEIO in Aug-Sep-Oct months
> - EEIO SST variablity is destingued from IOD, which is shown by disabled ENSO and IOD mode in LGM sim.
> > (disable ENSO and IOD means setting Nino3.4 and IOD index to climatology)
> - EEIO mode also shows the negative/cold phase 
> 
> 
> Impacts for the second half of the century:
> 
> - equatorial mode would drive rainfall variability with stronger amplitude
> - rainfall deficits (droughts) over the Horn of Africa as well as Southern India
> - increased rainfall over Indonesia and Northern Australia
> - so far IOD had not as strong impacts because of its strength
> - CMIP5 predict 2-4 equatorial IO modes per decade

**Discussion:**
- Why do only some CMIP5 models show this equatorial mode emergence?
- Is there some reason for this deviation?
- Given the CMIP5 models how likely would such an equatorial mode
  emerge? What are the uncertainties?


[Back to top](#journal-club)


### 17.11.2020 

**Wang et al. (2019) Diversity of the Madden-Julian Oscillation**

[Wang et al., Sci Adv, 2019](https://advances.sciencemag.org/content/5/7/eaax0220) presented by Felix S.  
 
The presentation can be found [here](files/ "Presentation Wang (2019)").

Discussion:
- MJO is the strongest intraseasonal variability
- How can we conclude the effect of Kelvin waves from wind vector fields?
 

[Back to top](#journal-club)

