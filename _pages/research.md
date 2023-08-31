---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
redirect_from:
  - /thesis
---

I develop Machine Learning methods to tackle large-scale open Neuroscience problems probabilistically.

## Methodology: Plate-Amortized Variational Inference (PAVI)

PAVI is a method to perform [inference](https://en.wikipedia.org/wiki/Bayesian_inference) in large-scale problems. Experimenters frequently hypothesize [generative models](https://en.wikipedia.org/wiki/Bayesian_network) to **explain some observed data**. The goal is to recover the latent *parameters* that could have yielded the observed *data* through the explanatory model. This is called **inference**. Because there may be some noise in the system or the generative process is random, the parameters often cannot be inferred unequivocally. The experimenter thus wishes to recover a probabilistic **distribution** of the parameters. What is the probability that each set of parameters generated the observed data through the model? To give a concrete Neuroscience example: given some MRI imaging of a patient's brain, how can we guess the size of the neurons in a given part of the brain?

One way to tackle inference is through optimization. We can define parametric distributions and fit those to the unknown distribution of parameters that could explain the observed data. Those methods are coined **Variational Inference (VI)**. VI is an attractive way to tackle inference because it is based on optimization, so it can leverage recent advances in the **Machine Learning** community. Nevertheless, VI can struggle when tackling substantial problems. Neuroscience typically features such large scales. For instance, a single brain can feature millions of voxels (volumetric pixels). The goal of PAVI is thus to **scale VI to very large problems, featuring hundreds of millions of inferred parameters**.

PAVI **shares the learning across repeated structures in the problem** to scale up inference. As an illustration, having inferred the size of the neurons in a given part of the brain, PAVI does not try to solve similar problems from scratch but does so similarly. In this case: inferring the size of the neurons in different brain parts. Because it shares learning, PAVI can perform inference up to a **thousand times faster than off-the-shelf methods**. This reduces the training time from weeks to hours and unlocks inference in large-scale regimes. The following sections describe ongoing Neuroscience projects that exploit PAVI.

Check out <img src="/images/download_logo.png" alt="download_logo" width="30"/> [the PAVI preprint](/files/PAVI_preprint.pdf) for more information

## Application: full cortex probabilistic parcellation for a cohort of 1,000 subjects

A parcellation clusters brain regions into different **connectivity networks**: fingerprints describing co-activation with the rest of the brain, as measured using functional Magnetic Resonance Imaging (fMRI). The core idea is that brain regions that co-activate work together towards a given brain function: vision, limb control, etc... A parcellation thus amounts to a functional **cartography of the brain**.

However, the brains of two different subjects can differ a lot from one another. Furthermore, the information we have to infer the function of a given brain location for a given subject is scarce. Hence, representing the cartographies of different subjects as only probabilistically known is helpful. See below the result for two subjects amongst a population of a thousand. Using PAVI, we shared the learning across brain regions and subjects and got those maps under **5 hours of computation time** for a parameter space of 400 million! The maps represent as colors the different networks in the brain and the primarily associated function. When the coloring softens, we cannot associate the corresponding region unequivocally with a network:

<img src="/images/Fullcortex.png" alt="fullcortex_parcellation" width="500"/> 
