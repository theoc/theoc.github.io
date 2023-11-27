---
title:  "Earth System Modelling benefitting from Cluster-Booster division"
date:   2016-11-14T13:08:28
cover:
  image: "/img/banners/deep-bench.jpg" 
  caption: "Trace of multi-process computation and communication"
  alt: "Trace of multi-process computation and communication"
  hidden: false
---

Understanding the evolution and changes of global climate is of utmost importance in the 21st century. The complexity of simulating the climate is reflected in the structure of the scientific codes in this research field. Scientists from The Cyprus Institute examined an alternative approach to heterogeneous computing in the many-core era for such Earth system models by porting the [EMAC](http://www.messy-interface.org/) Earth System Model application to the [DEEP platform](http://www.deep-er.eu/). 

## The challenge
EMAC is composed of two extremely different code parts. It couples a global circulation model (ECHAM) with local physical (MESSy) and chemical (MECCA) models to study climate change and air quality scenarios. Whereas the first one has high communication demands, the latter ones have high computational demands. For running the code on traditional homogenous parallel supercomputers this heterogeneity of the code poses a major challenge as it results in significant load imbalance which again hinders the scalability of the application.

## The solution
To alleviate this code imbalance and improve scalability, the DEEP Cluster-Booster approach offers a suitable solution: The computationally demanding code parts of the MESSy and MECCA models are offloaded to the Booster, while the communication demanding ECHAM model stays on the Cluster. In order to make the code division work, the [OmpSs](https://pm.bsc.es/ompss) programming model was used for:
 
* **Intranode taskification** The chemistry mechanism of the code (MECCA) was taskified using OmpSs directives. OmpSs allows the user to specify inputs and outputs for blocks of code or functions, giving enough information to the Nanos++ run-time which enables it to detect which  tasks  are  ready  to  be executed  concurrently,  and  therefore  the  programmer  does not have to explicitly manage the parallelization.
This helps to massively parallelize the chemistry calculations. Plus, the load imbalance is automatically alleviated by dynamic load balancing via OmpSs.
* **Internode taskification** OmpSs provides 2 important features: it allows offloading to remote  nodes – not  just locally  available  coprocessors/accelerators – which  is  a  key functionality to effectively use the Booster. Plus, it allows the use of the Booster as a pool of coprocessors, so tasks can be offloaded to any Booster node with enough free cores. The latter enables one to eliminate the load imbalance caused by sunlight gradients in MECCA. The second source of imbalance by heterogeneous reactions is also automatically alleviated by the dynamical load balance using the massive parallelization in the Booster.

## Outcome
The new version of EMAC, running ECHAM with MPI processes and MECCA with shared memory OmpSs tasks, outperforms the old EMAC using pure MPI, and continues to scale beyond the region where the original implementation scaling performance plateaus. It is important to note, that the use of the OmpSs API largely frees the programmer from implementing the offloading logic. Since EMAC is developed and used in a large community working on all aspects of the model, this can facilitate adoption of the concept in the MESSy community.  

We expect that the changes we propose with this work will contribute to the eventual adoption of Cluster-Booster division and Many Integrated Core (MIC) accelerated architectures in presently available implementations of Earth system models. This way, we believe, the codes of the scientific community will be able to exploit the potential of fully Exascale-capable platforms.

The relevant paper is available in [Geoscientific Model Development](http://www.geosci-model-dev.net/9/3483/2016/).

**Citation:** Christou, M., Christoudias, T., Morillo, J., Alvarez, D., and Merx, H.: Earth system modelling on system-level heterogeneous architectures: EMAC (version 2.42) on the Dynamical Exascale Entry Platform (DEEP), Geosci. Model Dev., 9, 3483-3491, doi:10.5194/gmd-9-3483-2016, 2016.
