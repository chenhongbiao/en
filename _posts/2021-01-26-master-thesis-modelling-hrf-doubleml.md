---
layout: post 
title: Master thesis - Towards a robust estimation of interactions between signals in fMRI-LFP experiments
tags: [Academic]
matheq: no
comments: yes
toc: yes
share: yes
recentvisitors: yes
---

- Author: Hongbiao Chen
- First supervisor: Dr. Michel Besserve
- Second supervisor: Prof. Dr. Nikos Logothetis
- Date: January 26, 2021
- Place: Neural Information Processing, Graduate Training Center for Neuroscience, University of Tübingen

### Abstract

#### (1) Introduce topics, keywords, and what we know
Multimodal measurement in neuroscience has become a mainstream experiment setting since it can investigate a neural system in different spatiotemporal scales to reveal the data generation mechanism across levels. 
For example, the simultaneous acquisition of functional magnetic resonance imaging (fMRI) and electrophysiology (Ephy) enables us to study the causal link - Hemodynamic Response Function (HRF), from the Ephy Local Field Potential (LFP) signal to the fMRI blood oxygenation level dependent (BOLD) signal.

#### (2) Introduce the question and what we don't know
However, the measured signal in the local system is not only contaminated by exogenous independent noise sources, but also influenced by the local module interaction and the global environment state due to the nested structure of neural systems.
In the case of concurrent fMRI-Ephy recording, the raw Ephy data is not only mixed with the fMRI gradient interference, but also contains the interaction effect of local frequency bands and the modulation effect of the global brain state.
It's still challenging to separate noise components for the high quality denoised Ephy data and to estimate the local HRF without bias, which results from the high-dimensional confounders inlcuding other local frequency bands and the global fMRI BOLD signal.

#### (3) provide major methods and results 
Following the lab rotation work, we develop an ensemble method to remove fMRI gradient artifacts, which also integrates a new metric to evaluate the denoised signal performance qualitatively and quantitively. 
The denoised method consists of multiple decomposition algorithms, including Principal Component Analysis (PCA), Independent Component Analysis (ICA) and Non-negative Matrix Factorization (NMF), and the evaluation metric is based on the coherence between recovered spike trains and the LFP during the detected ripple events.
While the comparative study shows that the optimized setting in the denoised pipeline are dependent on*** data itself characteristics, we provide empirical initializations and automatic parameter selection for the general purpose. 

Afterwards, we build a realistic model of multimodal signals to estimate the local HRF in a nonparametric way, by applying Double Machine Learning (DML) which combines standard causal inference and advanced machine learning (ML) techniques.
The DML estimator is theoretical unbiased for estimating the interested treatment effect (TE) from one local LFP band to the local BOLD signal, i.e., the low-dimensional parameters in the local HRF, by removing all nuisance effects of confounders.
In this thesis, we assume a linear time-invariant (LTI) system between the neural activity and the BOLD response, and implement the multi-treatment DML via EconML toolbox, where the local HRF is approximated by the LTI system's impulse response function.

#### (4) final conclusions and how can we get closer
Our experimental results demonstrate that the ensemble denoised approach can significantly reduce various noise effects to obtain high-quality Ephy signals with increased Signal-to-Noise Ratio (SNR) of ripple events, compared to a standard averaged artifact subtraction (AAS) method.
On the simulated and real dataset, we show that the DML method is always a fair choice compared to the naive method for the local HRF estimation, though it's more computational expensive and the performance improvement is actually determined by the underlying model relationships.
Given the complexity and nonlinearity of neural systems, we still recommend the DML method to estimate causal parameters and draw statistical inference about the local HRF, especially when multimodal signals of potential confounders are available.

### Summary 

#### (1) Ephy Denoising
In summary, we investigated an ensemble denosing toolkit for the elimination of various noise effects on the Ephy signal during Ephy-fMRI experiment, which is mainly corrupted by the gradient interference noise of the fMRI imaging. We show the detailed denoising workflow in two representative sessions K13m17 and E10bv1, and demonstrate that for clean dataset, (AAS plus) PCA and ICA are generally adequate and for datasets contaminated with large or complex noise structures, NMF would be a better choice. We also suggest some principles of how to inspect and evaluate the denoised signal quality, from the time plots, spectral plots to the spike-LFP coherence of ripple events in the hippocampus.

#### (2) HRF Estimation
Overall, we build a LTI model with confounders for the causal HRF estimation by using the naive and DML method. DML is able to correct the regularization bias entailed by the ML prediction of high-dimensional confounders. Thus, the DML method is suitable to estimate site-specific HRF, i.e., the treatment effects from the one local frequency band to the local BOLD signal. The simulation results show the effects of multi-treatments with multi-confounders, data normalization, model selection, and parameter tuning. The experimental results show that in the dataset E10aw1, the gamma and ripple bands are the primary treatments and the global fMRI signal is the most effective confounders, compared to the other local frequency bands. Together, it demonstrates that the DML method is a worthy choice to estimate the HRF compared to the naive regression method, especially when there are lots of potential confounders with the nonlinear relationship.

### Presentation

[Hong's master thesis](/media/resources/hongbiao-master-thesis-modelling-hrf-doubleml.pdf)

### Acknowledgments

I would like to express my thanks to Dr. Michel Besserve. When I first met him in the signal processing lecture, I was impressed by his organized slide and passionate teaching. After the lab visit, I admire him for his marvellous work, which is extensive in the interdisciplinary area among neuroscience, causal analysis and machine learning. I’m really excited to work with him to explore the advanced topics and techniques, including how sleep rhythms affect memory consolidation, how to denoise fMRI interference by nonnegative matrix factorization, and how to estimate the causal interactions by double machine learning. He guides me the research direction by his intelligent mind regularly but also gives me flexibility to consider my interests. I always enjoy the conversation with him, when he points out the key question in the office or discusses the new ideas in the Skype. I learn a lot from him during the time of essay rotation, lab rotation and master thesis, and I’m keen to be a creative and productive researcher in the future.

At the same time, I’m grateful that I have some great colleagues and friends. Kaidi Shao is the one who introduces me the lab work and enriches my life, including delicious food and gossiping. She helps me go through the paper work and shares her valuable experience, like how to handle the PC with a hidden helpful man - Joachim Werner. Shervin Safavi influences me by his professional style, generously providing constructive advice and actively sharing academic news about paper, talk and conference. I will remember all the time with their support and company.

![Michel group](/media/pictures/2020-Skype-Michel-group.jpg)
2020 Michel Group Skype