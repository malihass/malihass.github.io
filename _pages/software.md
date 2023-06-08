---
layout: archive
title: "Software"
permalink: /software/
author_profile: true
redirect_from:
  - "/Software"
  - "/software"
  - "/software.html"
  - "/Software.html"
---

{% include base_path %}

## Phase-space-sampling [![UIPS-CI](https://github.com/NREL/Phase-space-sampling/actions/workflows/ci.yml/badge.svg)](https://github.com/NREL/Phase-space-sampling/actions/workflows/ci.yml)

[Code](https://github.com/NREL/Phase-space-sampling)
[Paper](https://www.cambridge.org/core/journals/data-centric-engineering/article/uniforminphasespace-data-selection-with-iterative-normalizing-flows/E6212E3FCB5A7EE7B1399BA49667B84C)

Reduce a large dataset by strategically downselecting datapoints. The downselection preferentially keeps data points that have low probability and discards data points that are observed with high probability. The code can accomodate high-dimensions (we have tried up to 89 dimensions) and high number of data points (we have tried up to 100 millions). An MPI-parallel strategy is used to speed up the downselection. The probability estimation is done with a normalizing flow which can be trained with GPU to further accelerate training.

Using an iterative PDF estimation, the training cost does not increase with the number of datapoints, thereby allows reducing very large dataset at a reduced cost. 

Starting from a large dataset non-uniformly sampled such as the left picture below. The probability density function of the dataset is estimated (picture below on the right).
<p float="left">
  <img src="/files/images/fulldataset.png" width="350"/>
  <img src="/files/images/probabilityMap.png" width="350"/>
</p>

Uniform-in-phase-space datasets can be generated using the probability map using an arbitrary number of downselected points. The pictures below show a reduced dataset with 1,000 and 10,000 datapoints.
<p float="left">
  <img src="/files/images/103_phaseSpaceSampling.png" width="350"/> 
  <img src="/files/images/104_phaseSpaceSampling.png" width="350"/>
</p>



## Sparger Design [![SpargerDesign-CI](https://github.com/NREL/spargerDesign/actions/workflows/ci.yml/badge.svg)](https://github.com/NREL/spargerDesign/actions/workflows/ci.yml)

[Code](https://github.com/NREL/spargerDesign)

Generates clean meshes of block-cylindrical geometries. The code generates `blockMeshDict` which can be used to generate structured meshes with OpenFOAM. The interface to generate the `blockMeshDict` is designed to easily vary the geometry being meshed, thereby enabling geometry optimization tasks.

 
Another interface is provides to generate STL files which may be used to generate boundary conditions in OpenFOAM.


This code was primarily designed to optimize the design of spargers in bubble column reactors. However we can use it for any block cylindrical geometries which come up a lot more often than I initially thought!



## Sup3r ![](https://codecov.io/gh/nrel/sup3r/branch/main/graph/badge.svg) ![](https://github.com/NREL/sup3r/workflows/Pytests/badge.svg) ![](https://github.com/NREL/sup3r/workflows/Lint%20Code%20Base/badge.svg)

[Code](https://github.com/NREL/sup3r)

Super-resolution of global atmospheric models with Generative Adversarial Networks (GAN). The super-resolution may be spatial, temporal or both. The code is designed to handle very large datasets and large models. An interface to estimate the uncertainty during the super-resolution process is also provided.


## Diversity Super Res 

[Code](https://github.com/NREL/diversity_SR)
[Paper](https://arxiv.org/abs/2111.05962)

Diverse super-resolution of atmospheric data using a GAN (Generative Adversarial Neural Net). The diversity of the data generated is evaluated by computing a priori the conditional mean $$\mathbb{E}(HR|LR)$$ and the diagonal of the conditional variance $$\mathbb{E}(HR^2|LR)$$. During training, minibatches of atmospheric data are generated to evaluate empirically the moments aforementioned for the generated samples. The a priori and empirical moments are compared through a Frechet Distance loss which penalizes the generator. The advantage of this method is that the distribution of the generated samples can be quantitatively compared to the ideal distribution.  

## GANISP

[Code](https://github.com/NREL/GANISP)
[Paper](https://openreview.net/pdf?id=e6k_JgCT1P)
[Reviews](https://openreview.net/forum?id=e6k_JgCT1P)

Regularize genealogical adaptive multilevel splitting methods by using a Generative adversarial network (GAN) for the realization cloning. The GAN is regularized to encourage diverse generation of samples.




