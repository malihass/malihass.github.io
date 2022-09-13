---
layout: archive
permalink: /Research/
title: "Research"
author_profile: true
comments: false
redirect_from: 
  - "/Research"
  - "/research"
  - "/Research.html"
  - "/research.html"
---
{% include base_path %}


<a id="sciml"></a>
<h2>Scientific Machine Learning (SciML)</h2>

## *Generative models*

Generative models can be useful for manipulating high-dimensional probability density functions which are often critical for closure modeling, state estimation or data curation. I develop methods for generative adversarial networks (GANs) for uncertainty-aware state estimation of atmospheric flows.

<p align="center">
<img src="/images/demoDiverseSR.gif" width="375" height="125"/>
<img src="/images/cgan-wtlk.png" width="375" height="125"/>
</p>

Since samples generated with GANs are typically of high quality, they can be amenable to forward simulations that can assist uncertainty quantification tasks that use ensembles of forward simulations (typical in atmospheric modeling). When estimating rare-event probability, the sampling strategy can be critical and can benefit from a well-informed generative procedure.

<p align="center">
<img src="/images/ganisp.png" width="750" height="250"/>
</p>

Internally, some generative models directly learn the PDF that is being manipulated. Crucially, they work well in high dimensions. The PDF estimate can be used for various scientific tasks. For instance, I use them to curate datasets and transform inhomogeneously distributed data into a uniform-in-phase-space dataset.

<p align="center">
<img src="/images/uips.png" width="750" height="250"/>
</p>

### Related work:
1. M. Hassanaly, A. Glaws, K. Stengel, R. N. King, "Adversarial sampling of unknown and high-dimensional conditional distributions" in **Journal of Computational Physics**, 2022. [\[PDF\]](https://arxiv.org/pdf/2111.05962.pdf), [\[Code\]](https://github.com/NREL/diversity_SR)
2. M. Hassanaly, A. Glaws, R. N. King, "GANISP: a GAN-assisted Importance SPlitting Probability Estimator" in **AAAI-ADAM**, 2022. [\[PDF\]](https://arxiv.org/pdf/2112.15444.pdf), [\[Code\]](https://github.com/NREL/GANISP)
3. M. Hassanaly, B. Perry, M. E. Mueller, S. Yellapantula, "Uniform-in-Phase-Space Data Selection with Iterative Normalizing Flows", **Under Review**, 2022. [\[PDF\]](https://arxiv.org/pdf/2112.15446), [\[Code\]](https://github.com/NREL/Phase-space-sampling)
4. H.-W. Pang, M. Hassanaly, B. Perry, M. Day, W. H. Green, "Iterative Workflow for Quantification and Minimization of Reduced Chemistry-Induced Uncertainties in Reacting Flow Simulation", **WIPP 39th International Symposium on Combustion**, 2022. [\[Poster\]](https://www.nrel.gov/docs/fy22osti/83520.pdf)
5. S. Barwey, M. Hassanaly, V. Raman, A. Steinberg, "Using Machine Learning to Construct Velocity Fields from OH-PLIF Images", in **Combustion Science and Technology**, 2019. [\[PDF\]](https://arxiv.org/pdf/1909.13669.pdf)

## *Information extraction*

Despite large numerical and experimental available datasets it is not always straightforward to extract useful information for design purpose. I have found that reducing datasets either via sparse-sensing or data clustering can be a valuable tool. Sparse sensing can allow to pinpoint the cause of a variability in observations. Practically, we have used it to understand the cause being ignition kernels that catch fire or that that blow-out in aircraft engines.

<p align="center">
<img src="/images/failure-modified.gif" width="375" height="125"/> 
<img src="/images/success-modified.gif" width="375" height="125"/> 
<img src="/images/ign-sensors.png" width="375" height="125"/> 
</p>

Clustering can be useful to extract an interpretable and statistically significant sequence of states that explain a given phenomenon. I have used clustering to identify ignition mode and blow-out modes for ignition kernels that interact with different fuels. I used it to understand why a flame may attack or detach from a nozzle in a swirl combustor.

<p align="center">
<img src="/images/ign-modes.png" width="375" height="125"/> <img src="/images/crom-swirl.png" width="375" height="125"/>

</p>

### Related work
1. M. Hassanaly, Y. Tang, S. Barwey, V. Raman, "Data-driven analysis of relight variability of jet fuels induced by turbulence" in **Combustion and Flame**, 2021. [\[PDF\]](https://arxiv.org/pdf/2011.06696.pdf)
2. S. Barwey, M. Hassanaly, Q. An, V. Raman, A. Steinberg, "Experimental data-based reduced-order model for analysis and prediction of flame transition in gas turbine combustors" in **Combustion Theory and Modelling**, 2019. [\[PDF\]](https://arxiv.org/pdf/1904.00546.pdf)
3. S. Barwey, H. Ganesh, M. Hassanaly, V. Raman, S. Ceccio, "Data-based analysis of multimodal partial cavity shedding dynamics" in **Experiments in Fluids**, 2020. [\[PDF\]](https://drive.google.com/file/d/1cHa3zFwG378uNvRHxUjHwr9xSjccY8QP/view)


<a id="cfm"></a>
<h2>Complex fluid flows and High-Performance Computing (HPC)</h2>

## *Reacting flows*
Reacting flows modeling is a challenging computational problem that require efficiently modeling microscopic scale phenomena that influence macroscopic scales, without resolving the entire range of scales. I work on population-balance equations for modeling of soot particles. Additionally, reacting flows require resolving stiff systems of ODE that can accurately model complex chemistry. However, chemiscal composition usually spans a reduced part of composition space. It is therefore possible to represent the chemistry on low-dimensional manifold that can represent the dynamics of the chemistry at a reduced computational cost. I help develop this approach for modeling turbulent ignition of jet fuels. Alternatively, surrogate reduced chemistry models can be developed to replace detailed chemisty approaches. I develop such a strategy for surface chemistry models in deposition reactors. 

<p align="center">
<img src="/images/soot.png" width="375" height="125"/> 
<img src="/images/cvd.png" width="250" height="83.3"/> 
</p>

### Related work:
1. M. Hassanaly, H. Sitaraman, K. L. Schulte, A. J. Ptak, J. Simon, K. Udwary, J. H. Leach, H. Splawn, "Surface chemistry models for GaAs epitaxial growth and hydride cracking using reacting flow simulations" in **Journal of Applied Physics**, 2021. [\[PDF\]](https://arxiv.org/pdf/2109.11540)
2. M. Hassanaly, H. Sitaraman, K. Udwary, K. L. Schulte, H. Splawn, A. Ptak, J. Simon, "Optimization of Hydride Vapor Phase Epitaxy (HVPE) Deposition Reactor Manufacturing III-V Materials Using Multiple Large-Eddy Simulations (LES)" in **AIChE Annual Meeting**, 2020. [\[Abstract\]](/files/pdf/dhvpe_aiche.pdf)
3. Y. Tang, M. Hassanaly, V. Raman, B. Sforzo, J. Seitzman, "A comprehensive modeling procedure for estimating statistical properties of forced ignition" in **Combustion and Flame**, 2019. [\[PDF\]](https://www.osti.gov/servlets/purl/1570445)
4. H. Koo, M. Hassanaly, V. Raman, M. E. Mueller, K.-P. Geigle, "Large-eddy simulation of soot formation in a model gas turbine combustor" in **Journal of Engineering for Gas Turbines and Power**, 2017. [\[PDF\]](https://elib.dlr.de/107073/1/2016_koo_geigle_GTP_author_final.pdf)
5. S. T. Chong, M. Hassanaly, H. Koo, M. E. Mueller, V. Raman, K.-P. Geigle, "Large eddy simulation of pressure and dilution-jet effects on soot formation in a model aircraft swirl combustor" in **Combustion and Flame**, 2018. [\[PDF\]](https://elib.dlr.de/119917/1/2018_chong_geigle_cf_author_final.pdf)

## *Numerical solver*
No matter how accurate are physics models, they intimately interact with numerical solvers which can introduce larger errors than the physics-modeling approach. For instance, numerical discretization may introduce dissipation that outweighs the effect of turbulence models. I have developed a solver that minimize the amount of numerical dissipation of variable density low-Mach solvers in OpenFoam. 

<p align="center">
<img src="/images/dissipation.png" width="375" height="125"/> 
</p>

In turn, numerical solvers also depend on the computing architecture on which they are deployed. With the rise of GPU/CPU computing architectures, writing efficient code requires appropriate memory management. I have developed an approach where numerical chemistry Jacobian can be symbolically encoded, allowing to control the common subexpressions precomputations. A tradeoff between memory and computational intensity can be done that way. The approach has been deployed on Exascale machines.

### Related work
1. M. Hassanaly, H. Koo, C. F. Lietz, S. T. Chong, V. Raman, "A minimally-dissipative low-Mach number solver for complex reacting flows in OpenFOAM" in **Computer and Fluids**, 2018. [\[PDF\]](https://arxiv.org/pdf/1705.04777.pdf)
2. [\[Documentation\]](https://amrex-combustion.github.io/PelePhysics/QSS.html) on common-subexpression precomputations, and symbolic chemical Jacobian.


<a id="uq"></a>
<h2>Uncertainty quantification (UQ)</h2>

## *Bayesian inference*
Inverse Bayesian parametric inference can allow objective system identification given a limited dataset. In the context of Li-ion battery degradation, data availability is usually sparse, and the degradation may occur through different parameter sets. Inverse parametric inference can help identify the degradation mode or decide that more data is needed. However, the cost of parametric inference may be prohibitive when complex forward physics models are used. I develop surrogate approaches based on physics-informed neural networks to replace expensive Li-ion battery models.
<p align="center">
<img src="/images/pinn-battery.jpg" width="750" height="250"/>
</p>
 
## *Rare event probability estimation*
Efficiently estimating rare event probability requires artificially increasing the number of rare events observed. I develop methods for encouraging the occurrence of rare events in physics simulations.
<p align="center">
<img src="/images/gams.png" width="750" height="250"/>
</p>


## *Uncertainty propagation*

Coming Soon!

### Related work:
1. M. Hassanaly, P. J. Weddle, K. Smith, S. De, A. Doostan, R. N. King, "Physics-Informed Neural Network Modeling of Li-Ion Batteries", in **242nd ECS Meeting**, 2022. [\[Abstract\]](https://www.nrel.gov/docs/fy22osti/82015.pdf)
2. M. Hassanaly, V. Raman, "A self-similarity principle for the computation of rare event probability" in **Journal of Physics A: Mathematical and Theoretical**, 2019. [\[PDF\]](https://arxiv.org/pdf/1911.01222.pdf)
3. M. Hassanaly, A. Glaws, R. N. King, "GANISP: a GAN-assisted Importance SPlitting Probability Estimator" in **AAAI-ADAM**, 2022. [\[PDF\]](https://arxiv.org/pdf/2112.15444.pdf), [\[Code\]](https://github.com/NREL/GANISP)
