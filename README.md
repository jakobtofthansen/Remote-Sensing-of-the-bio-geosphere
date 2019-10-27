# Methodological comparison of SENTINEL-2 & PROBA-V

In the communities of Remote Sensing, and Geographical Information Systems, the available software is abundant. 
When doing remote sensing analysis, the ’Terrset - geospatial monitoring and modeling software’ has previously used. 
At the same time, a rapid expansion of data accessibility and suppliers has set new standard for pre-processed data and synthesized products. 
Just as the data and suppliers has diversified, the satellites has become specialized and easier to access by the public. 
The LANDSAT data received through generations, must have natural successors to properly utilize the full potential of timeseries analyzes. 
Meaning satellites have been launched with the a main goal; continuity of data. 

This paper examines the difference of measurement for two different satellites and sensors for the same study area and timeframe. 
The PROBA-V, launched in May 2013 as a successor to the SPOT Vegetation missions, is a satellite from the European Space Agency which provides global coverage on a 2-5 day basis. The Sentinel-2, launched in June 2015
by the same space agency, consists of two sun-synchronous satellites (A & B) spaced 180◦ apart. These two Sentinel-2 satellites provide global coverage on a 5 day basis at the equator with a spatial resolution 10 times to the PROBA-V.
Manually calculated NDVI measurements will be examined from both satellites for all of Denmark for a total of 975
days. 

One of the principles of this paper to explore the possibilities of these new opportunities, both for the benefit of personal current and future research. 
The general impression, using python as a tool for remote sensing, is that the data processing and preparation took more time, but when finished it could quickly be scaled up temporally and spatially.
The main advantages of performing and analyzing satellite data through python and Google Earth Engine, has been the reliability, stability and most importantly the quality of the analysis being reproducible.

## Study area
The study area for this project is the whole of Denmark, without the island of Bornholm. A central coordinate is chosen in the town of Odder, with a 200 km radius around it; all landmass inside this radius is subject to the analysis; this includes
the southern part of Skane, Sweden as well. The central coordinate is at ¨ [10.151320,55.981851]; shown on figure 1. 
The study uses date from 01-03-2017 through to 01-11-2019, this is due to limitations on the availability of atmospherically corrected Sentinel-2 data.

### IMAGE HERE 

## Results

The NDVI has been calculated for both satellites described in Section 2.2, spanning an area of Denmark excluding Bornholm. 
The observed values and trends are presented in figure below.

### IMAGE HERE

The figure above shows a clear seasonality in higher NDVI numbers in the summer months of both years, for both satellites.
Furthermore the Figure shows the difference in spike variety between the PROBA-V and Sentinel-2 satellites; the PROBAV measures higher NDVI numbers more often. Looking at figure 8, the plotted trendlines for both satellites are shown.
These are calculated using the moving average function with a 90 day frequency. The relative difference between the two is not large; they both display approximately the same fluctuations, with some inconsistencies. Generally PROBA-V
measures higher NDVI numbers throughout the time series, with a smoother trend and a seasonality that follows common sense. 
Meaning the winter months have lower NDVI levels compared to spring and summer months. 
This logic is abandoned when examining the trendline of the Sentinel-2 data; around October 2017 - January 2018 a large spike in
the NDVI values appear, which almost reaches the NDVI values of the following summers. 
According to the Sentinel-2 observations the greenness of the winter is equal to early-late summer. 
Continuing past 2017 the spring of 2018 includes NDVI trend values of around 0.0; suggesting the entire study area was covered by either clouds or overflown with water.
This drop occurs once more around winter-spring of 2019, this time without completely bottoming out at 0.0. 
The inconsistencies of the Sentinel-2 data is likely connected to larger percentage cloud cover.

### IMAGE HERE

Looking at the evolution of NDVI values on a two year period, for both PROBA-V and Sentinel-2, a seasonality pattern emerges with high NDVI during summer periods and lower during winter periods, except the winter of 2017/18.

There is a slight deviation in the red band wavelength between the two satellites 610−690 nm for the PROBA-V, and
650−680 nm for the Sentinel-2 satellites. This is due to the Sentinel-2 missions having greater focus on the chlorophyll
contents of the vegetation, which is reflected in the higher values of the red bandwidth. This means that the values observed
here from the PROBA-V satellite is recorded in a broader bandwidth than the Sentinel-2, and thereby potentially has a
different value measured. As seen in Figure 8, the sentinel mission had a remarkably lower NDVI score compared to the
PROBA-V, only few times were the modeled trendline NDVI-score from PROBA-V lower than the Sentinel-2 counterpart.

Another difference is the amount of information processed. The Sentinel-2 has a temporal scale of about five days.
The PROBA-V satellite has a daily synthesis, both are susceptible to clouds, but the PROBA-V has a higher temporal
resolution than that of the sentinel-2. This impacts the analysis somewhat, but as the scale and range of the analysis is on
a national and annual scale, the impact on the smoothed trendline is regarded as minor.

A main speculation point for the difference in trendlines between the Sentinel-2 and PROBA-V is the fact that there is a
difference in the spectral resolution for both the red and NIR bands, and the large spatial resolution difference.
The bandwidth of the red band of the PROBA-V satellite is twice as large, 82 vs. 39, as the Sentinel-2, while the NIR
band is narrower, 121 vs. 133/147. As mentioned previously the Sentinel-2 was developed for the detection of Chlorophyll in plants, which is why the difference in bandwidth exists. The larger bandwidth of the PROBA-V could contribute
to the slightly increased NDVI values compared to Sentinel-2.

The spatial resolution of the PROBA-V, created from nadir observations, is 100m while Sentinel-2 is 10m in the VNIR
bands. This resolution difference could be a contributor to the more detailed observations from the Sentinel-2, in regards
to figure 7, which does not include the large spike fluctuations. A more detailed and larger dataset like the Sentinel-2
compared to the PROBA-V is more likely to include a lot of noise, when summed up to a larger extend, like the study area
of this paper. The study area consists of an area 400km x 400km, including bodies of water around the landmass. The
more stable and smooth trendline of the PROBA-V satellite is less likely to be influenced by noise, and therefore maybe
a more precise measurement in this regard. The temporal and radiometric scale of both satellites is more or less the same
without much impact on this study.

Using GEE a massive amount of data is made available to use without much hassle. This project has only taken the
information measured by the red and NIR bands from the two different sensors into consideration, while a huge number
of metadata is also available to increase the understanding of the data. This paper has not taken anything other than the
calculated NDVI values into account for the methodology, which has created gaps in our results in regards to the analysis
of these. The lack of understanding the real reason behind the difference in the two time series values could have been
patched by including information about the cloud cover percentage, land percentage, missing data percentage ect. for
each data point. These three, and many more, pieces of information could potentially help create a understanding of the
difference; and remove some of the speculation

## Conclusion
The two different satellites and sensors produced two different NDVI measurement plots for the same study area and time
frame. The raw observed data from the PROBA-V satellite showed more short variation and spikes but was generally
more stable in the long term trends. The Sentinel-2 data showed less variation in the short term observations, while more
unstable and noise polluted on a long term basis. The Sentinel-2 with the narrower bandwidth on the red band and superior
spatial resolution picked up on to much detail, which showed a less cohesive result in the end.

The comparison between the two satellites and sensors fell short due to the exclusion of explanatory metadata around
the satellite images. Without including information about cloud cover percentage, land mass percentage and missing data
percentage, in the analysis; it is all speculatory guesswork in regards to understanding the differences in the data.

The only fair conclusion to this methodological comparison between the two satellites is that without the proper
understanding and examination of the tools and data beforehand, a useful and repeatable result can not be produced. The
use of Google Earth Engine, though very powerful and futuristic, needs to be calibrated and used correctly.
