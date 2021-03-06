
# A latent Dirichlet allocation (LDA) model for taxi trips

## Question
**_How do the New York City and San Francisco taxi markets differ?_**

## Motivation
In 2014, I wanted to know how Uber was expanding the market for on-demand mobility. I suspected that in cities like New York the traditional taxi ecosystem was already well developed, so Uber not be a huge change. But cities like San Francisco have sparser taxi service, so Uber may be more market-expanding. 

This project provides a baseline by identifying differences in the taxi market in SF and NYC. In order to do that, I used timestamped GPS data on taxi pickup and dropoffs to classify different types of trips in each city. 

## The Model

LDA is an unsupervised learning model that originally developed to classify text documents into topics, as described by [Blei et al. (2003)](http://www.jmlr.org/papers/v3/blei03a.html "Blei et al. (2003)"). The central idea is that each document in a given collection contains a mixture of latent topics, and these underlying topics give rise to a predictable vocabulary. Thus the pattern of word frequency in the document collection can be used to infer the topics it contains.

In this application I used LDA to classify trips based on their spatial and temporal attributes. (Other examples [here](https://hal.archives-ouvertes.fr/hal-01052951/ "Come et al.") and [here](http://dl.acm.org/citation.cfm?id=2424395 "Kling").)

## The Data
This analysis uses timestamped taxi GPS records from the SFMTA and the NY Taxi and Limousine Commission. 

- San Francisco: complete trip records from one of the city’s larger taxi companies
  - October 2012 and mid-July through October 2013 (>700,000 trips).
- New York: all trips in the city
  - I chose to use only October 2013, more than 15 million trips. Of these I randomly sampled 10%.
  - available [here](http://chriswhong.com/open-data/foil_nyc_taxi/ "taxi data"). 

## Results
**_The results suggest New Yorkers tend to use taxis in a broader range of cases, especially for commuting. Taxi usage in San Francisco is more specialized, with a greater focus on late night and airport trips._** 

NYC has more distinct trip types than does SF. E.g., it has two distinct types for morning and evening commute.

<img src="images/facet-plots-both.png?raw=true" alt="facet-plot" width="624" height="553">

All the trip types together. Note the spikes in SF on Friday and Saturday nights. 

<img src="images/nyc-colors-700x350.png?raw=true" alt="facet-plot">
<img src="images/sf-colors-700x350.png?raw=true" alt="facet-plot">


This demonstrates a way to infer taxi trip purposes from GPS data alone, without need for surveys or reliance on potentially biased data sources.

## Project Status
The jupyter notebooks contain the code I used for data preparation, model building, and some visualization - including an implementation of the [Gensim LDA model](https://radimrehurek.com/gensim/models/ldamodel.html). 
The code was written with Python2. It is untested and not very clean. In the future I may find time make it more reproducible. 

See the [project write-up](LDA_writeup.pdf) for methodological details. 

