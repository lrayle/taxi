
# A latent Dirichlet allocation (LDA) model for taxi trips

## Question: How do the New York City and San Francisco taxi markets differ? 

## Motivation
In 2014, I wanted to know how Uber was expanding the market for on-demand mobility. I suspected that in cities like New York the traditional taxi ecosystem was already well developed, so Uber not be a huge change. But cities like San Francisco have sparser taxi service, so Uber may be more market-expanding. 

This project provides a baseline by identifying differences in the taxi market in SF and NYC. In order to do that, I used timestamped GPS data on taxi pickup and dropoffs to classify different types of trips in each city. 

## The Model

LDA is an unsupervised learning model that originally developed to classify text documents into topics, as described by Blei et al. (2003). The central idea is that each document in a given collection contains a mixture of latent topics, and these underlying topics give rise to a predictable vocabulary. Thus the pattern of word frequency in the document collection can be used to infer the topics it contains.

In this application I used LDA to classify trips based on their spatial and temporal attributes.

## The Data
This analysis uses timestamped taxi GPS records provided by the SFMTA and the NY Taxi and Limousine Commission. 

The San Francisco dataset consists of complete trip records (more than 700,000 total) from one of the city’s larger taxi companies for October 2012 and mid-July through October 2013. The New York dataset includes all trips in the city. I chose to use only October 2013, which totals more than 15 million trips. Of these I randomly sampled 10%. 

The data cover the metropolitan area of each city. 
The data are from 2012 and 2013, a time when Uber was only beginning to impact the taxi market.

## Results
The results suggest New Yorkers tend to use taxis in a broader range of cases, especially for commuting, whereas taxi usage in San Francisco is more specialized, with a greater focus on late night and airport trips. This demonstrates a way to infer taxi trip purposes from GPS data alone, without need for surveys or reliance on potentially biased data sources.


## Project Status
This was a project prepared for Alexey Pozdnoukhov's Scalable Spatial Analytics course (CE263) at UC Berkeley in 2014. See 'LDA_writeup.pdf' for details. 

The jupyter notebooks contain the code I used for data preparation, model building, and some visualization. 
The code is untested and not very clean. In the future I may find time make it more reproducible. 
