---
title: "Climate-Atmospheric Chemical Kinetics on GPU Accelerators"
date:   "2017-07-14T13:08:28"
cover:
  image: "img/banners/GPU.jpg"
  caption: "GPU calculated surface-layer atmospheric radical concentration"
  alt: "GPU calculated surface-layer atmospheric radical concentration"
  hidden: false
---

One of today’s great scientific challenges is to predict how climate will change locally as gas concentrations change over time. The study of chemistry-climate interactions represents an important and, at the same time, difficult task of global Earth system research. 

The global climate model EMAC is a modular model that simulates climate change and air quality scenarios. EMAC uses a general-purpose chemical kinetic module to calculate the concentrations and the interactions of chemical species in the atmosphere. Solving atmospheric chemical kinetics is one of the most computationally intensive tasks in atmospheric chemical transport simulations. 

To address the computational challenge, a project was initiated under Vi-SEEM to accelerate the performance of the chemical kinetics calculations on modern high-performance supercomputers using Graphics Processing Units (GPU). 

The Vi-SEEM project provided an opportunity to develop and test the software using the Cy-TERA Supercomputer System in Cyprus. Cy-TERA provides computational resources for researchers in the wider South East Europe and Eastern Mediterranean Region with the installation of a hybrid cluster machine of peak performance 30 Teraflops. 

The outcome of the study was the development a publicly released source code that automatically ports the kinetics calculations on GPU architectures. Each GPU thread calculates the chemical concentrations of an individual atmospheric grid box, massively parallelising theworkload. The achieved performance showed up to 22.4× improvement of the kernel execution time over the old implementation.

The Vi-SEEM project provided the necessary e-Infrastructure resources, training and support to develop the building blocks for a new generation of advanced and well-evaluated high-resolution global climate models, capable of simulating and predicting regional climate with unprecedented fidelity. 

Vastly improved spatial and temporal simulation accuracy will allow assessment of the impacts of climate change on the environment, human health, agriculture and energy sectors for the years to come and will enable informed policy planning for adaptation and mitigation.

## Links

* [Open Research Software Journal](https://openresearchsoftware.metajnl.com/articles/10.5334/jors.158/)
* [Vi-SEEM code repository](https://code.vi-seem.eu/malvanos/medina)
* [Github repository](https://github.com/CyIClimate/medina)

