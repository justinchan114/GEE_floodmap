# gee_floodmap
Introduction

This is a flood mapping project with the aid of Google Earth Engine.
Google Earth Engine has datasets with satellitte images (https://developers.google.com/earth-engine/datasets/), in this flood mapping project, images from Sentinel-1 and Sentinel-2 were used (https://developers.google.com/earth-engine/datasets/catalog/sentinel).

The Sentinel-1 mission provides data from a dual-polarization C-band Synthetic Aperture Radar (SAR) instrument. SAR instruments are capable of acquiring meaningful data in all weather conditions (even clouds) during daytime and nighttime. Hence this is particular useful for flooding events, since clouds are often presence.

The process:
1. Define the boundary of study
2. Define the date of study (before the flood event and after the flood event, for satellite image comparison)
2. Collect relevant images from Sentinel dataset, Sentinel-1 covers Metro Vancouver with "IW mode" and "VV", "VV-VH" polirisation (https://sentinels.copernicus.eu/documents/247904/4748961/Sentinel-1-Mode-Polarisation-Observation-Geometry-2021.png) 
3. Apply speckle filter and compare between pre and post-event images
4. Mask out areas with:
  a. Permanent water
  b. Slope of 1:25 (4%) or above

https://code.earthengine.google.com/3ab3edfee326d3509a9333b5b554b30f?accept_repo=users%2Fujavalgandhi%2FEnd-to-End-Projects
