# Midway and O'Hare Noise Contour

## Overview

This repo captures the work I conducted as a Cook County Assessor's Office (CCAO) data intern in the Winter of 2022 to build a surface to reflect noise values surrounding O'Hare and Midway airports. The work can be seen in the CCAO [gitlab repository](https://gitlab.com/ccao-data-science---modeling). However, the exact location of the work will move, so I am putting my code here as a stable location to show it. I summarize the overall goal of the project and the results as well as describe repo contents below. 

## Report Abstract

**Problem** The CCAO previously used a polygon surrounding O'Hare airport to demarcate properties that had high sound exposure. They used a binary variable to capture airport sound. This is unsatisfactory because it does not take into account sound from Midway airport at all or the continuous nature of sound surrounding O'Hare. 

**Data** We collected data from noise monitoring stations surrounding O'Hare and Midway which is publicly available from the Chicago Department of Aviation's website. The completed dataframe had columns representing year, location of noise monitor, and a measure of sound level for that given location and year (in DNL). 

**Analysis** We interpolated these points to continuous surfaces reflecting noise surrounding both Chicago airports using two methods: inverse distance weighting and ordinary kriging. To test the best parameters associated with both models, we performed Leave One Out Cross-Validaton. 

**Conclusion** Our best performing surface was an odinary kriging surface and had an RMSE of about 3.83 DNL. To contextualize, a quiet urban setting could have DNL of around 55 while standing approximately 3 feet from a honking car could have DNL of about 110 (see [here](https://www.faa.gov/regulations_policies/policy_guidance/noise/basics/) for a great graphic from the FAA). 



## Repo Contents

`input` is a folder containing datasets used to process the data. Some of them were pulled from CCAO's AWS S3 buckets where they store data in the cloud. 

`output/kriging_demo` shows pdfs of kriging surfaces created.

`airport_sound_report.Rmd` is a R Markdown file used to create a report summarizing this work. That report can also be found in the repo or via [this link](https://github.com/Deckart2/noise_contour/blob/main/airport_sound_report.pdf). 

`create_midway_sound.R` is a short script that creates dataframe for noise monitoring stations surrounding Midway airport. 

`ohare_sound.Rmd` is the heart of this repo. It contains code to clean and compile the airport sound monitoring location dataset, preliminary data visualization, code to build and evaluate model surfaces, code to create more fine-grained model surfaces, and finally code to write those surfaces. 
