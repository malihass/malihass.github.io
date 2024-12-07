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

## Phase-space-sampling [![UIPS-CI](https://github.com/NREL/Phase-space-sampling/actions/workflows/ci.yml/badge.svg)](https://github.com/NREL/Phase-space-sampling/actions/workflows/ci.yml) [![UIPS-pypi](https://badge.fury.io/py/uips.svg)](https://badge.fury.io/py/uips) 


[Code](https://github.com/NREL/Phase-space-sampling)
[Paper](https://www.cambridge.org/core/journals/data-centric-engineering/article/uniforminphasespace-data-selection-with-iterative-normalizing-flows/E6212E3FCB5A7EE7B1399BA49667B84C)
[Pypi](https://pypi.org/project/uips/)

Reduce a large dataset by strategically downselecting datapoints. The downselection preferentially keeps data points that have low probability and discards data points that are observed with high probability. The code can accommodate high-dimensions (we have tried up to 89 dimensions) and high number of data points (we have tried up to 100 millions). An MPI-parallel strategy is used to speed up the downselection. The probability estimation is done with a normalizing flow which can be trained with GPU to further accelerate training.

Using an iterative PDF estimation, the training cost does not increase with the number of datapoints, thereby allows reducing very large dataset at a reduced cost. 

Starting from a large dataset non-uniformly sampled such as the left picture below. The probability density function of the dataset is estimated (picture below on the right).
<p float="left">
  <img src="https://raw.githubusercontent.com/NREL/Phase-space-sampling/main/documentation/readmeImages/fulldataset.png" width="350"/>
  <img src="https://raw.githubusercontent.com/NREL/Phase-space-sampling/main/documentation/readmeImages/probabilityMap.png" width="350"/>
</p>

Uniform-in-phase-space datasets can be generated using the probability map using an arbitrary number of downselected points. The pictures below show a reduced dataset with 1,000 and 10,000 datapoints.
<p float="left">
  <img src="https://raw.githubusercontent.com/NREL/Phase-space-sampling/main/documentation/readmeImages/103_uips.png" width="350"/> 
  <img src="https://raw.githubusercontent.com/NREL/Phase-space-sampling/main/documentation/readmeImages/104_uips.png" width="350"/>
</p>



# <ins>Bi</ins>o <ins>R</ins>eactor <ins>D</ins>esign (BiRD) [![bird-CI](https://github.com/NREL/BioReactorDesign/actions/workflows/ci.yml/badge.svg)](https://github.com/NREL/BioReactorDesign/actions/workflows/ci.yml) [![bird-pyversion](https://img.shields.io/pypi/pyversions/NREL-bird.svg)](https://pypi.org/project/NREL-bird/)  [![bird-pypi](https://badge.fury.io/py/nrel-bird.svg)](https://badge.fury.io/py/nrel-bird)


[Code](https://github.com/NREL/BioReactorDesign)
[Pypi](https://pypi.org/project/nrel-bird/)

Generates clean meshes of block-cylindrical geometries. The code generates `blockMeshDict` which can be used to generate structured meshes with OpenFOAM. The interface to generate the `blockMeshDict` is designed to easily vary the geometry being meshed, thereby enabling geometry optimization tasks. A schematic of the block cylindrical architecture described by `.json` files in the repo is show below (left). The corresponding mesh generated is shown on the right.
<p float="left">
  <img src="https://raw.githubusercontent.com/NREL/BioReactorDesign/main/assets/schematic.png" width="350"/>
  <img src="https://raw.githubusercontent.com/NREL/BioReactorDesign/main/assets/3dsparger.png" width="200"/>
</p>

 
Another interface is provides to generate STL files which may be used to generate boundary conditions in OpenFOAM. An example of such STL is shown below.
<p float="left">
  <img src="https://raw.githubusercontent.com/NREL/BioReactorDesign/main/assets/simpleOutput.png" width="350"/> 
</p>



This code was primarily designed to optimize the design of spargers in bubble column reactors. However we can use it for any block cylindrical geometries which come up a lot more often than I initially thought!

## Sup3r [![Pytests](https://github.com/NREL/sup3r/workflows/Pytests/badge.svg)](https://github.com/NREL/sup3r/actions/workflows/pull_request_tests.yml)  [![Lint Code Base](https://github.com/NREL/sup3r/actions/workflows/linter.yml/badge.svg)](https://github.com/NREL/sup3r/actions/workflows/linter.yml)  ![](https://codecov.io/gh/nrel/sup3r/branch/main/graph/badge.svg)

[Code](https://github.com/NREL/sup3r)

Super-resolution of global atmospheric models with Generative Adversarial Networks (GAN). The super-resolution may be spatial, temporal or both. The code is designed to handle very large datasets and large models. An interface to estimate the uncertainty during the super-resolution process is also provided.


## Diversity Super Res 

[Code](https://github.com/NREL/diversity_SR)
[Paper](https://arxiv.org/abs/2111.05962)

Diverse super-resolution of atmospheric data using a GAN (Generative Adversarial Neural Net). The diversity of the data generated is evaluated by computing a priori the conditional mean $$\mathbb{E}(HR \| LR)$$ and the diagonal of the conditional variance $$\mathbb{E}(HR^2 \| LR)$$. Examples of the a priori estimated moments are shown below.

<p align="center">
<img src="/files/images/aprioriMoments.png" width="600"/>
</p>


During training, minibatches of atmospheric data are generated to evaluate empirically the moments aforementioned for the generated samples. The a priori and empirical moments are compared through a Frechet Distance loss which penalizes the generator. The advantage of this method is that the distribution of the generated samples can be quantitatively compared to the ideal distribution.  
Below is a demonstration of the data that can be generated. On the left a low-resolution wind data input is shown, on the right the true high-resolution data is show. In the middle, many possible super-resolved wind contour that map back to the same low-resolution input are shown.


<p align="center">
<img src="https://raw.githubusercontent.com/NREL/diversity_SR/master/diversity_SR/Demo/DEMO.gif" width="562" height="187"/>
</p>


## GANISP (<ins>GAN</ins>-assited <ins>I</ins>mportance <ins>SP</ins>litting)

[Code](https://github.com/NREL/GANISP)
[Paper](https://openreview.net/pdf?id=e6k_JgCT1P)
[Reviews](https://openreview.net/forum?id=e6k_JgCT1P)

Regularize genealogical adaptive multilevel splitting methods by using a Generative adversarial network (GAN) for the realization cloning. The GAN is regularized to encourage diverse generation of samples. Example of generated clones using the GAN vs a random cloning method are shown below in the case of Kuramoto-Sivashinsky equation.

<p align="center">
<img src="/files/images/cloning.png" width="550"/>
</p>



## PINNSTRIPES (<ins>P</ins>hysics-<ins>I</ins>nformed <ins>N</ins>eural <ins>N</ins>etwork <ins>S</ins>urroga<ins>T</ins>e for <ins>R</ins>apidly <ins>I</ins>dentifying <ins>P</ins>arameters in <ins>E</ins>nergy <ins>S</ins>ystems) [![PINNSTRIPES-CI](https://github.com/NREL/PINNSTRIPES/actions/workflows/ci.yml/badge.svg)](https://github.com/NREL/PINNSTRIPES/actions/workflows/ci.yml) 

[Code](https://github.com/NREL/PINNSTRIPES)
[Paper 1](https://arxiv.org/pdf/2312.17329.pdf)
[Paper 2](https://arxiv.org/pdf/2312.17336.pdf)

Bayesian inference of Li-ion battery models parameters made data-efficient thanks to Physics-informed neural networks. The code contains a demonstration of the implementation for single particle model, and provides an interface for using the surrogate within a Bayesian inference worflow.

As example the training results using *no data* is shown for the single particle model (SPM) of an NMC Li-ion battery.

<p float="left">
  <img src="https://raw.githubusercontent.com/NREL/PINNSTRIPES/main/assets/corr_0.5_1.gif" width="175"/>
  <img src="https://raw.githubusercontent.com/NREL/PINNSTRIPES/main/assets/cs2D_0.5_1.gif" width="265"/>
  <img src="https://raw.githubusercontent.com/NREL/PINNSTRIPES/main/assets/phi_0.5_1.gif" width="240"/>
</p>




## prettyPlot [![prettyPlot-CI](https://github.com/malihass/prettyPlot/actions/workflows/ci.yml/badge.svg)](https://github.com/malihass/prettyPlot/actions/workflows/ci.yml) [![prettyPlot-CI](https://badge.fury.io/py/prettyPlot.svg)](https://badge.fury.io/py/prettyPlot) 

[Code](https://github.com/malihass/prettyPlot)
[Pypi](https://pypi.org/project/prettyPlot/)

A suite of tools to
1. Standardize research plots in python
2. Parse input files
3. Display a progress bar for iterative processes

