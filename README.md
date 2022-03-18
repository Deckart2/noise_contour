# Midway and O'Hare Noise Contour

## Overview

This repo captures the work I conducted as a Cook County Assessor's Office (CCAO) data intern in the Winter of 2022 to build a surface to reflect noise values surrounding O'Hare and Midway airports. The work can be seen in the CCAO [gitlab repository](https://gitlab.com/ccao-data-science---modeling). However, the exact location of the work will move, so I am putting my code here as a stable location to show it.

## Repo Contents

`input` is a folder containing datasets used to process the data. Some of them were pulled from CCAO's AWS S3 buckets where they store data in the cloud. 

`output/kriging_demo` shows pdfs of kriging surfaces created.

`airport_sound_report.Rmd` is a R Markdown file used to create a report summarizing this work. That report can also be found in the repo or via [this link](https://github.com/Deckart2/noise_contour/blob/main/airport_sound_report.pdf). 

`create_midway_sound.R` is a short script that creates dataframe for noise monitoring stations surrounding Midway airport. 

`ohare_sound.Rmd` is the heart of this repo. It contains code to clean and compile the airport sound monitoring location dataset, preliminary data visualization, code to build and evaluate model surfaces, code to create more fine-grained model surfaces, and finally code to write those surfaces. 
