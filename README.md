# gee_floodmap
__Introduction__

This is a flood mapping project using Google Earth Engine.

Google Earth Engine has datasets of satellite images (https://developers.google.com/earth-engine/datasets/), in this flood mapping project, images from Sentinel-1 and Sentinel-2 were used (https://developers.google.com/earth-engine/datasets/catalog/sentinel) for analyzing the flooding extent of a severe rainstorm event.

Codes are in https://code.earthengine.google.com/3ab3edfee326d3509a9333b5b554b30f?accept_repo=users%2Fujavalgandhi%2FEnd-to-End-Projects

__Event of study__

In mid-Nov 2021, atmospheric river brought heavy rainfall to southern BC, Canada.
In Hope, British Columbia, 277.5 millimetres (10.93 in) of rain fell from November 14 to 15, 2021; nearing the two-day record of 303.6 millimetres (11.95 in) set from November 9 to 10 1990.
This caused servere flooding in many parts of BC, including Abbotsford and metro Vancouver. 
This is a preliminary study of flood map near Abbortsford during the storm.

__Methodolody__

The Sentinel-1 mission provides data from a dual-polarization C-band Synthetic Aperture Radar (SAR) instrument. SAR instruments are capable of acquiring meaningful data in all weather conditions (even clouds) during daytime and nighttime, which is particular useful for analyzing flooding events. We will gather satellite image before and after the flood, and make comparison. Since open water is characterized by low backscatter due to specular reflection, we can measure the difference between pre and post rainfall event, to see if certain area have been flooded. 

On the other hand, Sentinel-2 could provide a clear rgb satellite image, to facilitate the study of original landuse.

__The process__

The process is relatively simple in this preliminary study:
1. Define the boundary of study
2. Define the date of study (before the flood event and after the flood event, for satellite image comparison)
3. Collect relevant images from Sentinel datasets:
  a. Sentinel-1 covers Metro Vancouver with "IW mode" and "VV", "VV-VH" polirisation (https://sentinels.copernicus.eu/documents/247904/4748961/Sentinel-1-Mode-Polarisation-Observation-Geometry-2021.png) Gather images of early Nov 2021 (Pre-rainstorm) and 16-20 Nov (Post-rainstorm)
  b. Sentinel-2 RGB satellite image, in early July 2021 with limited clouds
5. Apply speckle filter on collected Sentinel-1 datasets 
6. Compare pre and post-event images, by calculating the difference in backscatter. Two methods were used for comparison, subtraction and division, and subtration with thresold of 3 demonstrated better mapping of flooded area in area of study.
7. Mask out areas with:
  a. Permanent water
  b. Slope of 1:25 (4%) or above
8. Add layer of flooded area 
