---
title: "ADAVI: Automatic Dual Amortized Variational Inference Applied To Pyramidal Bayesian Models"
collection: publications
permalink: /publication/ADAVI-ICLR-2022
excerpt: 'We automatically derive a variational family dual to a plate-enriched Hierarchical Bayesian Network and perform amortized inference.'
date: 2022-04-25
venue: 'ICLR 2022'
paperurl: 'https://openreview.net/forum?id=CgIEctmcXx1'
citation: '
@inproceedings{
    rouillard2022adavi,
    title={{ADAVI}: Automatic Dual Amortized Variational Inference Applied To Pyramidal Bayesian Models},
    author={Louis Rouillard and Demian Wassermann},
    booktitle={International Conference on Learning Representations},
    year={2022},
    url={https://openreview.net/forum?id=CgIEctmcXx1}
}'
---
Frequently, population studies feature pyramidally-organized data represented using Hierarchical Bayesian Models (HBM) enriched with plates. These models can become prohibitively large in settings such as neuroimaging, where a sample is composed of a functional MRI signal measured on 300 brain locations, across 4 measurement sessions, and 30 subjects, resulting in around 1 million latent parameters.

Such high dimensionality hampers the usage of modern, expressive flow-based techniques.

To infer parameter posterior distributions in this challenging class of problems, we designed a novel methodology that automatically produces a variational family dual to a target HBM. This variational family, represented as a neural network, consists in the combination of an attention-based hierarchical encoder feeding summary statistics to a set of normalizing flows. Our automatically-derived neural network exploits exchangeability in the plate-enriched HBM and factorizes its parameter space. The resulting architecture reduces by orders of magnitude its parameterization with respect to that of a typical flow-based representation, while maintaining expressivity.

Our method performs inference on the specified HBM in an amortized setup: once trained, it can readily be applied to a new data sample to compute the parameters' full posterior.

We demonstrate the capability and scalability of our method on simulated data, as well as a challenging high-dimensional brain parcellation experiment. We also open up several questions that lie at the intersection between normalizing flows, SBI, structured Variational Inference, and inference amortization.

<img src="/images/download_logo.png" alt="download_logo" width="30"/> [Download paper here](/files/ADAVI_ICLR2022.pdf)

Recommended citation:
```
@inproceedings{
    rouillard2022adavi,
    title={{ADAVI}: Automatic Dual Amortized Variational Inference Applied To Pyramidal Bayesian Models},
    author={Louis Rouillard and Demian Wassermann},
    booktitle={International Conference on Learning Representations},
    year={2022},
    url={https://openreview.net/forum?id=CgIEctmcXx1}
}
```