---
layout: page
permalink: /research/
title: Past and current research
tags: [code]
modified: 12-29-2017
comments: false
---
<br>
During my PhD I’ve focused in the field of Neural Data Science, aiming to develop methods for handling massive stream of data routinely collected with modern neuro-technologies. I’ve covered from the quite fundamental aspects of ML, to the applied problem of the end-to-end development of algorithms to be used in future neural prosthesis to treat neuro-degenerative retinal disease. 
<br>
One of the major challenges in systems neuroscience resides in the difficulty to fully apprehend the structure in massive neural data; it is therefore urgently needed to envision methods that facilitates the processing and understanding of these datasets. This provides a fertile ground for the creation of new techniques, and ML highlights as a suited methodological framework: both the problem of finding sparse neural signals from recordings, and of finding structure in the resulting high-dimensional neural time series, can be cast as statistical inference problems, and advanced ML methodology is required to come up with models and algorithms to efficiently address these problems. In the following I  describe the four main projects I worked on.

### Neural Coding
The neural coding problem corresponds to determining which features of the world neurons respond to (encode). The standard data-driven approach consist on inferring a model that expresses the distribution of neural responses given stimuli time-series. These responses are represented as spike trains, and can be thought as the emissions of a point process. Therefore, efficient methods for inference in point processes are required. My contribution in this area [1] was the discovery of a simplifying Gaussian Quadrature approximation for the calculation of the mean firing rate  that greatly facilitate its inference: this provided a substantial improvements over existing methods. This result permitted to fit neural encoding models much faster, without sacrificing accuracy.
