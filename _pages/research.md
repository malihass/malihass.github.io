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
3. M. Hassanaly, B. Perry, M. E. Mueller, S. Yellapantula, "Uniform-in-Phase-Space Data Selection with Iterative Normalizing Flows", **Data-Centric Engineering**, 2023. [\[PDF\]](https://arxiv.org/pdf/2112.15446), [\[Code\]](https://github.com/NREL/Phase-space-sampling)
4. A. Rybchuk, M. Hassanaly, N. Hamilton, P. Doubrawa, M. J. Fulton, L. A. Martinez-Tossas, "Ensemble flow reconstruction in the atmospheric boundary layer from spatially limited measurements through latent diffusion models", **Physics of Fluids**, 2023. [\[PDF\]](https://pubs.aip.org/aip/pof/article/35/12/126604/2928913/Ensemble-flow-reconstruction-in-the-atmospheric), [\[Code\]](https://github.com/rybchuk/latent-diffusion-3d-atmospheric-boundary-layer)
5. A. Rybchuk, L. A Martínez-Tossas, N. Hamilton, P. Doubrawa, G. Vijayakumar, M. Hassanaly, M. B. Kuhn and D. S. Zalkind, "A baseline for ensemble-based, time-resolved inflow reconstruction for a single turbine using large-eddy simulations and latent diffusion models", **Wake Conference**, 2023. [\[PDF\]](https://iopscience.iop.org/article/10.1088/1742-6596/2505/1/012018/pdf)
6. H.-W. Pang, M. Hassanaly, B. Perry, M. Day, W. H. Green, "Iterative Workflow for Quantification and Minimization of Reduced Chemistry-Induced Uncertainties in Reacting Flow Simulation", **WIPP 39th International Symposium on Combustion**, 2022. [\[Poster\]](https://www.nrel.gov/docs/fy22osti/83520.pdf)
7. S. Barwey, M. Hassanaly, V. Raman, A. Steinberg, "Using Machine Learning to Construct Velocity Fields from OH-PLIF Images", in **Combustion Science and Technology**, 2019. [\[PDF\]](https://arxiv.org/pdf/1909.13669.pdf)

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
Reacting flows modeling is a challenging computational problem that require efficiently modeling microscopic scale phenomena that influence macroscopic scales, without resolving the entire range of scales. I work on population-balance equations for modeling of soot particles. Additionally, reacting flows require resolving stiff systems of ODE that can accurately model complex chemistry. However, chemical composition usually spans a reduced part of composition space. It is therefore possible to represent the chemistry on low-dimensional manifold that can represent the dynamics of the chemistry at a reduced computational cost. I help develop this approach for modeling turbulent ignition of jet fuels. Alternatively, surrogate reduced chemistry models can be developed to replace detailed chemisty approaches. I develop such a strategy for surface chemistry models in deposition reactors. 

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
6. N. Wimer, L. Esclapez, N. Brunhart-Lupo, M. Henry de Frahan, M. Rahimi, M. Hassanaly, J. Rood, S. Yellapantula, H. Sitaraman, B. Perry, M. Martin, O. Doronina, S. Appukuttan, M. Rieth, M. Day, "Visualizations of a methane/diesel RCCI engine using PeleC and PeleLMeX" in **75th Annual Meeting of the APS Division of Fluid Dynamics**, 2022. [\[Gallery of Fluid Motion Video\]](https://gfm.aps.org/meetings/dfd-2022/63236765199e4c2c0873f9f6) 🏆 **Milton Van Dyke Award** [\[PDF\]](https://journals.aps.org/prfluids/pdf/10.1103/PhysRevFluids.8.110511)

## *Numerical solver*
No matter how accurate are physics models, they intimately interact with numerical solvers which can introduce larger errors than the physics-modeling approach. For instance, numerical discretization may introduce dissipation that outweighs the effect of turbulence models. I have developed a solver that minimize the amount of numerical dissipation of variable density low-Mach solvers in OpenFoam. 

<p align="center">
<img src="/images/dissipation.png" width="375" height="125"/> 
</p>

In turn, numerical solvers also depend on the computing architecture on which they are deployed. With the rise of GPU/CPU computing architectures, writing efficient code requires appropriate memory management. I have developed an approach where numerical chemistry Jacobian can be symbolically encoded, allowing to control the common subexpressions precomputations. A tradeoff between memory and computational intensity can be done that way. The approach has been deployed on Exascale machines.

### Related work
1. M. Hassanaly, H. Koo, C. F. Lietz, S. T. Chong, V. Raman, "A minimally-dissipative low-Mach number solver for complex reacting flows in OpenFOAM" in **Computer and Fluids**, 2018. [\[PDF\]](https://arxiv.org/pdf/1705.04777.pdf)
2. M. Hassanaly, N. T. Wimer, A. Felden, L. Esclapez, J. Ream, M. T. Henry de Frahan, J. Rood, M. Day, "Symbolic construction of the chemical Jacobian of quasi-steady state (QSS) chemistries for Exascale computing platforms" in **Combustion and Flame**, 2024. [\[PDF\]](https://arxiv.org/abs/2405.05974), [\[Code\]](https://github.com/AMReX-Combustion/PelePhysics)
3. C. J. Balos, Marc Day, L. Esclapez, A. M. Felden, D. J. Gardner, M. Hassanaly, D. R. Reynolds, J. Rood, J. M. Sexton, N. T. Wimer, C. S. Woodward, "SUNDIALS Time Integrators for Exascale Applications with Many Independent ODE Systems" in **International Journal of High Performance Computing Applications**, 2024. [\[PDF\]](https://arxiv.org/pdf/2405.01713)

<a id="uq"></a>
<h2>Uncertainty quantification (UQ)</h2>

## *Bayesian inference*
Inverse Bayesian parametric inference can allow objective system identification given a limited dataset. In the context of Li-ion battery degradation, data availability is usually sparse, and the degradation may occur through different parameter sets. Inverse parametric inference can help identify the degradation mode or decide that more data is needed. However, the cost of parametric inference may be prohibitive when complex forward physics models are used. I develop surrogate approaches based on physics-informed neural networks to replace expensive Li-ion battery models.
<p align="center">
<img src="/images/pinn-battery.jpg" width="750" height="250"/>
</p>

### Related work:
1. M. Hassanaly, P. J. Weddle, R. N. King, S. De, A. Doostan, C. R. Randall, E. J. Dufek, A. M. Colclasure, K. Smith, "PINN surrogate of Li-ion battery models for parameter inference. Part I: Implementation and multi-fidelity hierarchies for the single-particle model", in **Journal of Energy Storage**, 2024. [\[PDF\]](https://arxiv.org/pdf/2312.17329.pdf) [\[Code\]](https://github.com/NREL/PINNSTRIPES)
2. M. Hassanaly, P. J. Weddle, R. N. King, S. De, A. Doostan, C. R. Randall, E. J. Dufek, A. M. Colclasure, K. Smith, "PINN surrogate of Li-ion battery models for parameter inference. Part II: Regularization and application of the pseudo-2D model", in **Journal of Energy Storage**, 2024. [\[PDF\]](https://arxiv.org/pdf/2312.17336.pdf) [\[Code\]](https://github.com/NREL/PINNSTRIPES)
3. M. Hassanaly, J. M. Parra-Alvarez, M. J. Rahimi, H. Sitaraman, "Bayesian calibration of bubble size dynamics applied to CO2 gas fermenters" in **Chemical Engineering Research and Design**, 2025. [\[PDF\]](https://arxiv.org/pdf/2404.19636), [\[Code\]](https://github.com/NREL/BioReactorDesign)

 
## *Rare event probability estimation*
Efficiently estimating rare event probability requires artificially increasing the number of rare events observed. I develop methods for encouraging the occurrence of rare events in physics simulations.
<p align="center">
<img src="/images/gams.png" width="750" height="250"/>
</p>

### Related work:
1. M. Hassanaly, V. Raman, "A self-similarity principle for the computation of rare event probability" in **Journal of Physics A: Mathematical and Theoretical**, 2019. [\[PDF\]](https://arxiv.org/pdf/1911.01222.pdf)
2. M. Hassanaly, A. Glaws, R. N. King, "GANISP: a GAN-assisted Importance SPlitting Probability Estimator" in **AAAI-ADAM**, 2022. [\[PDF\]](https://arxiv.org/pdf/2112.15444.pdf), [\[Code\]](https://github.com/NREL/GANISP)


## *Uncertainty propagation*
Propagate uncertainty through physics-based models with a computationally efficient approach. Here the focus is on propagating the uncertainty of ML closure models through high-fidelity simulations with a sample-efficient approach.

### Related work:
1. G. Pash, M. Hassanaly, S. Yellapantula, "A Priori Uncertainty Quantification of Reacting Turbulence Closure Models using Bayesian Neural Networks" in **Engineering Applications of Artificial Intelligence**, 2024. [\[PDF\]](https://arxiv.org/pdf/2402.18729), [\[Code\]](https://github.com/NREL/MLUQ-PROP)
2. G. Pash, M. Hassanaly, S. Yellapantula, "Equipping Neural Network Surrogates with Uncertainty for Propagation in Physical Systems" in **SIAM UQ**, 2024. [\[PDF\]](https://www.nrel.gov/docs/fy24osti/89061.pdf), [\[Code\]](https://github.com/NREL/MLUQ-PROP)

<a id="adv"></a>
<h2>Adversarial robustness</h2>
I develop reinforcement learning (RL) methods that play the role of malicious agents that fool defense algorithms to induce catastrophic outcomes. These RL agents can then inform further improvement of defense algorithms by continuously improving the defense. Effectively, the defense must adapt to evolving tasks which poses the question of catastrophic forgetting. I develop these methods in the context of cyber-security of the power grid, and I hope to deploy them on other applications in the future.

<p align="center">
<img src="/images/adv.png" width="750" height="250"/>
</p>

### Related work:
1. R. Prasad, M. Hassanaly, X. Zhang, A. Sahu, "Discovery of false data injection schemes on frequency controllers with reinforcement learning" in **IEEE Power & Energy Society General Meeting (PESGM)**, 2024.  [\[PDF\]](https://arxiv.org/pdf/2408.16958)
2. P. Aslami, K. Chen, T. M. Hansen, M. Hassanaly, "Continual Adversarial Reinforcement Learning (CARL) of False Data Injection detection: forgetting and explainability" **IEEE PowerTech**, 2025. [\[PDF\]](https://arxiv.org/pdf/2411.10367)
3. K. Chen, T. Nguyen, M. Hassanaly, "Adversarial Multi-Agent Reinforcement Learning for Proactive False Data Injection Detection" **Under Review**, 2025. [\[PDF\]](https://arxiv.org/pdf/2411.12130)
4. A. Sahu, T. Nguyen, K. Chen, X. Zhang, M. Hassanaly, "Detection of False Data Injection Attacks (FDIA) on Power Dynamical Systems With a State Prediction Method" **IEEE Access**, 2024. [\[PDF\]](https://arxiv.org/pdf/2409.04609) 
5. N. Do, T. Nguyen, M. Hassanaly, R. Alharbi, J. T. Seo, M. T. Thai, "Swift Hydra: Self-Reinforcing Generative Framework for Anomaly Detection with Multiple Mamba Models" **ICLR**, 2025. [\[PDF\]](https://arxiv.org/pdf/2503.06413?)

