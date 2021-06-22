---
layout: post 
title: Lab rotation report - Denoise fMRI gradient interference on electrophysiological signals
tags: [Academic]
matheq: no
comments: yes
toc: yes
share: yes
recentvisitors: yes
---

- Author: Hongbiao Chen
- Supervisor: Dr. Michel Besserve
- Date: January 31, 2020
- Place: Neural Information Processing, Graduate Training Center for Neuroscience, University of Tübingen

### Abstract

The simultaneous acquisition of functional magnetic resonance imaging (fMRI) and electrophysiology (Ephy) data is a promising experiment technique in neuroscience because it allows us to study the same neural system from two different levels concurrently. However, recording fMRI-Ephy together induces fMRI gradient interference on Ephy data and denoising Ephy signals is still challenging. Here we review methods of reducing gradient artifacts, including hardware-based and software-based, and present a new denoising method, Non-negative Matrix Factorization with Itakura-Saito divergence (IS-NMF). Our results demonstrate that IS-NMF approach can effectively remove residual artifacts to obtain high quality Ephy data after applying hardware compensation and standard averaged artifact subtraction (AAS).

### Summary 

In summary, when we record fMRI and Ephy signals together, the Ephy data contains not only the original neural electrical signals but also fMRI-induced gradient artifacts and residual noise. After using hardware circuits to compensate the fMRI interference, the rest of noise can be eliminated by performing IS-NMF in addition to AAS method to get the denoised Ephy data.

### Presentation

[Hong's lab rotation report](/media/resources/hongbiao-lab-rotation-is-nmf-denoise-fmri-lfp.pdf)