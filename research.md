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

### Electrical Stimulation of the Retina
In collaboration with EJ Chichilnisky lab at Stanford, I have extensively researched computational aspects to the problem of large-scale neural stimulation [2,3]. The BRAIN initiative report stated this is a major area where developments are needed, since this capability can be critical for establishing functional relationships among neurons, and because it opens a concrete possibility for manipulating the activity of neural circuits, providing a technological substrate for new therapies. I worked in the specific context of simultaneous stimulation and recording of Retinal Ganglion Cells (RGC). There, pervasiveness of stimulation artifacts hampers our ability to make sense of data: as a result of electrical stimuli, recordings in multi-electrode arrays become heavily corrupted, and painstaking manual curation by a highly skilled experimentalist is required to infer neural responses. I invented a method that enables such automatic analysis. This method is based on the modeling of recorded signals as the sum of an artifact and neural spikes, and the use of a structured gaussian process to model an infer the artifact component, while simultaneously estimating spikes by template matching. The resulting algorithm greatly enhances the data analysis pipeline, as now it is possible to analyze in hours volumes of data that would otherwise take months. Currently we are applying this method to a large-scale study of how neurons respond to different types of large-scale stimulation, and at different locations. Also, for the development of a high-resolution neural prosthesis to treat loss of sight due to retinal degeneration. There, one needs to determine in real-time the optimal stimuli that will generate a perception, which requires knowing whether electrical stimulus elicits activation in different neuron, a capability granted by our algorithm. Currently, we are exploring elementary closed-loop protocols to show this highly-non trivial interaction is feasible. In summary, the technique I developed enabled data analysis at a much larger spatio-temporal scale than previously possible, opening the doors for probing new scientific questions and conceiving more sophisticated neuro-stimulation protocols and devices.

### Hierarchical bayesian modeling of C.elegans. 
The nematode (worm) C. elegans is a unique model organism for neuroscientists as its connectome, or neural wiring diagram, is highly stereotypical across specimens, and some prior knowledge of its structure has been known for decades. Therefore, in principle one could combine information from many individuals to accurately infer complex models of neural dynamics, and better understand how activity in the network of 302 neurons relates to behavior and processing of external information. This problem can be cast as a hierarchical bayesian model, where MCMC is the gold-standard inference method. However, in practice, to combine information from many worms one needs to “canonicalize” the recorded time series, by matching them to a reference worm. To do this, one requires to resolve the identity of each recorded calcium trace, which in practice necessitates laborious human analysis. We created a method that aims to automatize this analysis, by integrating the matching inference problem in the hierarchical bayesian setup, through the addition of a variable that represents this matching. We appealed to variational inference (VI), as MCMC-based approaches are slowed-down by the additional matching inference. However, applying VI is non-trivial, as permutations are discrete objects, precluding the immediate use of stochastic gradient descent, the standard optimization substrate for VI. To alleviate this problem, we developed two different relaxations that replace discrete permutations by continuous approximations, and showed we outperform a MCMC sampler [4]. These relaxations are based some rounding and stick-breaking constructions. Altogether, these new methods have the potential to greatly improve data-analysis capabilities in the Bayesian hierarchical modeling of C.elegans in real experiments, they automatizes a canonicalization procedure that otherwise would  be extremely painstaking for a human [5].

### Gumbel-Sinkhorn networks for learning permutations
This work focuses on more fundamental aspects related to inference of permutations, and applications to deep learning. Specifically, we conceive approximate inference of permutations and matchings based on the perturb-and-MAP framework, plus the approximation of a matching operator by the so-called Sinkhorn operator,  i.e., the successive row and column-wise normalization of a matrix. By appealing to a popular entropy-regularization technique, we showed that the Sinkhorn operator approximates a matching in the very same way as the softmax approximates the choice of a category. With this observation we conceived a novel architecture for an artificial neural network that learns permutations; a Gumbel-Sinkhorn network [6]. Our results provide new principled methods for representing permutations in stochastic computation graphs, a question that otherwise would be treated heuristically in the Deep Learning community. Also, it establishes interesting connection with the theory of optimal transportation [7].

### References

[1] Mena, G. & Paninski, L. (2014) On Quadrature Methods for Refractory Point Process Likelihoods.
Neural Computation, Vol. 26, No. 12, 2790-2797.
<br>
[2] Mena, G., Grosberg, L., Hottowy, P., Litke, A., Cunningham, J., Chichilnisky E.J. & Paninski,
L. (2017) Electrical Stimulus Artifact Cancellation and Neural Spike Detection on Large Multi-
Electrode Arrays. In press, PLOS Computational Biology 13: e1005842.
<br>
[3] Mena, G., Grosberg, L. , Kellison-Linn, F. , Chichilnisky E.J. & Paninski, L. (2015) Large-scale
Multi-Electrode Array Spike Sorting Algorithm Introducing Concurrent Recording and Stimulation.
NIPS Workshop on Statistical Methods for Understanding Neural Systems.
<br>
[4]  Linderman, S.* , Mena, G.* , Cooper, H., Paninski, L., Cunningham, J. (2018) Reparameterizing the Birkhoff Polytope for Variational Permutation Inference. AISTATS. arXiv:1710.09508
<br>
[5]  Mena, G.*, Linderman*, S., Belanger, D., Snoek, J., Paninski, L., Cunningham, J. (2017) Toward Bayesian permutation inference for identifying neurons in C. elegans. NIPS Workshop on Worm’s Neural
Information Processing.
<br>
[6]  Mena, G., Belanger, D., Linderman, S., Snoek, J. (2018). Learning Latent Permutations with Gumbel-
Sinkhorn Networks. Under review (ICLR 2018). OpenReview
<br>
[7]  Mena, G., Belanger, D., Muñoz, G., Snoek, J. (2017) Sinkhorn Networks: Using Optimal Transport Techniques to Learn Permutations. NIPS Workshop in Optimal Transport & Machine Learning.


