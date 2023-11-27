---
title:  "Dark Sky Visualisation"
date:   "2015-09-02T15:42:28"
categories: ["visualization"]
cover:
  image: "img/banners/HALO.jpg"
  alt: "2015 IEEE Scientific Visualisation Contest"
  hidden: false
---


Cosmological simulations are a cornerstone of our understanding of the Universe during its 13.7 billion year progression from small fluctuations that we see in the cosmic microwave background to today, where we are surrounded by galaxies and clusters of galaxies interconnected by a vast cosmic web.

Simulations of the formation of structure in the Universe typically simulate dark matter, a collisionless fluid, as a discretized set of particles that interact only gravitationally. Ensuring adequate mass resolution within a simulation requires a large number of particles — typically on the scale of 10243, 20483, or even 102403 particles in the largest simulations. Developing visualisations for these particles, and perhaps more challengingly for the structures that they form through gravitational interaction and collapse, requires first identifying the structures, developing spatial or informatics representations of the components or the structures themselves, and then correlating these visualizations across time steps.

{{< youtube QlA5WX1UneU >}}

_CaSToRC CoS516 Course Final Project: "High Performance Visualisation for Large-Scale Scientific Data Analytics" submitted to the [IEEE SciVis Contest 2015](http://darksky.slac.stanford.edu/scivis2015/)._

Typically, structures are identified through a semi-local process known as halo finding, wherein dark matter halos are identified either via local particle density estimation or through simple linking-length mechanisms. Within these halos, which may represent galaxies or clusters of galaxies, substructures are identified – within a galaxy cluster, smaller halos may be identified which correspond to the location of galaxies. As these structures and substructures interact, merge, separate and grow, the structure of the Universe grows and changes with it. Visualizing the transitions that simulated halos undergo during the lifetime of the Universe can provide necessary inputs to understanding observations from next generation telescopes.

Datasets derived from the [Dark Sky Simulations](http://darksky.slac.stanford.edu/scivis2015/data.html).

