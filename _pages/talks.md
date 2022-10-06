---
layout: archive
permalink: /Talks/
title: "Talks"
author_profile: true
comments: false
redirect_from: 
  - "/Talks"
  - "/talks"
  - "/talks.html"
  - "/talks.html"
---
{% include base_path %}


<h2>Generative models and scientific sampling</h2>

## *NCSU applied mathematics seminar*

Realistic image generation has benefited from recent groundbreaking advances in the ML community. At the core of generative models lies the capability to sample high-dimensional distributions with relatively small support and a priori unknown shape. In many scientific applications, this capability is a limiting factor that has led to modeling choices that circumvent the sampling problem. In this talk, I will demonstrate how generative models can tackle outstanding scientific challenges by leveraging their ability to sample high-dimensional distributions, or directly estimate them. While generative models are typically understood as data augmentation tools, their ability to handle high-dimensional distributions makes them also suited for data reduction. The sampling capabilities of generative models are illustrated for two scientific problems: atmospheric state inference, and turbulent combustion closure modeling.


<iframe width="560" height="315" src="https://www.youtube.com/embed/7rD8qj1M2c0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Related work:
1. M. Hassanaly, A. Glaws, K. Stengel, R. N. King, "Adversarial sampling of unknown and high-dimensional conditional distributions" in **Journal of Computational Physics**, 2022. [\[PDF\]](https://arxiv.org/pdf/2111.05962.pdf), [\[Code\]](https://github.com/NREL/diversity_SR)
2. M. Hassanaly, B. Perry, M. E. Mueller, S. Yellapantula, "Uniform-in-Phase-Space Data Selection with Iterative Normalizing Flows", **Under Review**, 2022. [\[PDF\]](https://arxiv.org/pdf/2112.15446), [\[Code\]](https://github.com/NREL/Phase-space-sampling)
3. H.-W. Pang, M. Hassanaly, B. Perry, M. Day, W. H. Green, "Iterative Workflow for Quantification and Minimization of Reduced Chemistry-Induced Uncertainties in Reacting Flow Simulation", **WIPP 39th International Symposium on Combustion**, 2022. [\[Poster\]](https://www.nrel.gov/docs/fy22osti/83520.pdf)

<h2>GAN-assisted importance splitting estimator</h2>

## *AAAI-ADAM Workshop, 2022*

Designing manufacturing processes with high yield and strong reliability relies on effective methods for rare event estimation. Genealogical importance splitting reduces the variance of rare event probability estimators by iteratively selecting and replicating realizations that are headed towards a rare event. The replication step is difficult when applied to deterministic systems where the initial conditions of the offspring realizations need to be modified. Typically, a random perturbation is applied to the offspring to differentiate their trajectory from the parent realization. However, this random perturbation strategy may be effective for some systems while failing for others, preventing variance reduction in the probability estimate. This work seeks to address this limitation using a generative model such as a Generative Adversarial Network (GAN) to generate perturbations that are consistent with the attractor of the dynamical system. The proposed GAN-assisted Importance SPlitting method (GANISP) improves the variance reduction for the system targeted.

<iframe src="https://nrel-my.sharepoint.com/personal/mhassana_nrel_gov/_layouts/15/embed.aspx?UniqueId=5fa322a5-2c51-4cdc-8a16-51dd40807483&nav=%7B%22playbackOptions%22%3A%7B%22startTimeInSeconds%22%3A6%7D%7D&embed=%7B%22ust%22%3Atrue%2C%22hv%22%3A%22CopyEmbedCode%22%7D&referrer=StreamWebApp&referrerScenario=EmbedDialog.Create" width="640" height="360" frameborder="0" scrolling="no" allowfullscreen title="Meeting with Hassanaly, Malik-20220224_143815-Meeting Recording.mp4"></iframe>

### Related work
1. M. Hassanaly, A. Glaws, R. N. King, "GANISP: a GAN-assisted Importance SPlitting Probability Estimator" in **AAAI-ADAM**, 2022. [\[PDF\]](https://arxiv.org/pdf/2112.15444.pdf), [\[Code\]](https://github.com/NREL/GANISP)
