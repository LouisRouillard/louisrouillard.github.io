---
title: "PAVI: Plate-Amortized Variational Inference"
collection: publications
permalink: /publication/PAVI-preprint
excerpt: 'Through an original combination of amortization and stochastic training, we scale inference to very large problems.'
date: 2023-04-18
venue: 'Preprint - TMLR'
paperurl: https://openreview.net/forum?id=vlY9GDCCA6
citation: '
@article{
    anonymous2023pavi,
    title={{PAVI}: Plate-Amortized Variational Inference},
    author={Anonymous},
    journal={Submitted to Transactions on Machine Learning Research},
    year={2023},
    url={https://openreview.net/forum?id=vlY9GDCCA6},
    note={Under review}
}'
---
Given observed data and a probabilistic generative model, Bayesian inference searches for the distribution of the model's parameters that could have yielded the data. Inference is challenging for large population studies where millions of measurements are performed over a cohort of hundreds of subjects, resulting in a massive parameter space. This large cardinality renders off-the-shelf Variational Inference (VI) computationally impractical.

In this work, we design structured VI families that efficiently tackle large population studies. Our main idea is to share the parameterization and learning across the different i.i.d. variables in a generative model -symbolized by the model's *plates*. We name this concept *plate amortization*. Contrary to off-the-shelf stochastic VI --which slows down inference-- plate amortization results in orders of magnitude faster to train variational distributions. Applied to large-scale hierarchical problems, PAVI yields expressive, parsimoniously parameterized VI with an affordable training time --effectively unlocking inference in those regimes.

We illustrate the practical utility of PAVI through a challenging Neuroimaging example featuring 400 million latent parameters, demonstrating a significant step towards scalable and expressive Variational Inference.

<img src="/images/download_logo.png" alt="download_logo" width="30"/> [Download paper here](/files/PAVI_preprint.pdf)

Recommended citation:
```
@article{
    anonymous2023pavi,
    title={{PAVI}: Plate-Amortized Variational Inference},
    author={Anonymous},
    journal={Submitted to Transactions on Machine Learning Research},
    year={2023},
    url={https://openreview.net/forum?id=vlY9GDCCA6},
    note={Under review}
}
```