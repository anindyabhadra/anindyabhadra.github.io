---
layout: page
permalink: /research/
title: research
description: Selected ongoing and past projects.
nav: true
nav_order: 2
_styles: >
  @media (min-width: 577px) { .research-fig.wide { width: auto; display: table; } .research-fig.wide img { height: 190px; width: auto; } .research-fig.wide figcaption { display: table-caption; caption-side: bottom; } }
---

## Selected ongoing projects

### Generative modeling of SPD-valued data and applications in neuroimaging
{: .accent}

<figure class="research-fig wide">
  <img src="/assets/img/research/wishart_20_mix_panel_histograms.png" alt="Schematic: Generative modeling of mixture Wishart data." loading="lazy">
  <figcaption><strong>Generative modeling of mixture Wishart data using a <a href="https://arxiv.org/abs/2606.15442">volume-normalized shape flow</a> (left two panels) and competing methods (right two panels). Holdout data from the target in gray.</strong></figcaption>
</figure>

Building on the telescoping decomposition of symmetric positive definite (SPD) matrices introduced by [Bhadra et al. (2024, JMLR)](https://www.jmlr.org/papers/v25/23-0254.html), my recent work involves principled approaches for generative modeling of such data, that commonly arise in neuroimaging. The key ideas are developed in [Bhadra (2026, arXiv)](https://arxiv.org/abs/2606.15442), who explores a _reversal_ of this decomposition to design a new unconstrained SPD coordinate chart that isolates the Jacobian into a single coordinate encoding the log determinant.  Consequently, Bhadra (2026) demonstrates it is (somewhat counterintuitively) _easier_ to design a volume-normalized shape flow for SPD for generative modeling compared to unconstrained Euclidean data with no intrinsic notion of volume. 


### Inference in highly multivariate Gaussian process models for environmental applications
{: .accent}

<figure class="research-fig wide">
  <img src="/assets/img/research/oxy.png" alt="Oxygen prediction residuals in the Southern Ocean conditional of temperature and salinity using Argo data." loading="lazy">
  <figcaption><strong><a href="https://doi.org/10.1007/s11004-025-10185-6">Oxygen prediction residuals</a> in the Southern Ocean conditional of temperature and salinity using Argo data.</strong></figcaption>
</figure>

Modern oceanographic data sets such as [Argo](https://argo.ucsd.edu/) collect tens of variables in hundreds or thousands of spatial locations. Principled modeling of such data calls for construction of highly multivariate cross-covariances, and efficient computational methodology. My recent work involves variational Bayes and random Fourier features-based methods to address this.


### Computationally efficient inference and uncertainty quantification in probabilistic graphical models
{: .accent}

<figure class="research-fig">
  <img src="/assets/img/research/movies.png" alt="Movie ratings network." loading="lazy">
  <figcaption><strong>A Markov random field model of movie preferences for males and females based on the MovieLens 1M ratings data.</strong></figcaption>
</figure>

Probabilistic graphical models are a longstanding interest of mine, and I have several ongoing projects in this area. [Sagar et al. (2024, EJS)](https://doi.org/10.1214/23-EJS2196) establish posterior concentration results under global-local shrinkage priors on precision matrices, including the graphical horseshoe. [Bhadra et al. (2024, JMLR)](https://www.jmlr.org/papers/v25/23-0254.html) provide a resolution to the problem of computing evidence, or marginal likelihood, in Gaussian graphical models (GGMs), for a class of priors considerably broader than what was previously feasible. [Sagar et al. (2024, Stat)](https://doi.org/10.1002/sta4.682) develop a fast MAP estimation procedure using a novel local linear approximation scheme for GGMs. Likelihood-based inference in probabilistic graphical models with intractable likelihood, including partially observed cases such as the Boltzmann machines, is developed by [Chen et al. (2026, JMLR)](https://arxiv.org/abs/2404.17763). A useful follow-up is by [Chen et al. (2026, AISTATS)](https://openreview.net/forum?id=lDnMftmNhP) who give both exact and approximate MCMC algorithms for these models while avoiding a computationally expensive and sequential *inner loop* Markov chain. See also other related papers on my webpage.

## Selected past projects

### Beyond Matérn: the Confluent Hypergeometric covariance function for Gaussian process models
{: .accent}

<figure class="research-fig">
  <img src="/assets/img/research/ch_covariance.png" alt="Correlation vs. distance: The CH class keeps Matérn-type smoothness control but has polynomial, not exponential, tails." loading="lazy">
  <figcaption><strong>The <a href="https://doi.org/10.1080/01621459.2022.2027775">CH covariance class</a> keeps Matérn-type smoothness control but has polynomial, not exponential, tails. It can model both short and long range dependence.</strong> </figcaption>
</figure>

I have worked in the recent past (and continue to work on) Gaussian process (GP) models, which appear in at least three distinct areas of great contemporary interest: as models for spatial and spatiotemporal processes, as surrogate models for computer experiments, and as limits of deep neural networks. My first work in this area concerns the design of a covariance function. The Matérn covariance function remains very popular in spatial statistics in part because of the control it affords the user on the mean squared differentiability of the GP realizations. However, the Matérn covariance possesses an exponentially decaying tail, which may not be the best choice for modeling in situations where distant observations can display high correlations. This problem can be remedied of course by using Cauchy or rational quadratic covariances, but this comes at a great cost: the control over smoothness is completely lost! [Ma and Bhadra (2023, JASA)](https://doi.org/10.1080/01621459.2022.2027775) design a new covariance class called the *Confluent Hypergeometric (CH)* class as a mixture of the Matérn class that allows simultaneous flexibility on smoothness and polynomial tail decay via two distinct parameters. A key observation is made on the connection between Matérn and the normalizing constant of the generalized inverse Gaussian distribution of Barndorff-Nielsen. [Yarger and Bhadra (2025, Math. Geosc.)](https://doi.org/10.1007/s11004-025-10185-6) provide valid multivariate generalizations of the CH covariance function. [Fang and Bhadra (2025, EJS)](https://doi.org/10.1214/25-EJS2417) demonstrate Gaussian process priors with rescaled Matérn and CH covariance functions achieve the nonparametric minimax rate in estimation, even when the smoothness of the true function and that of the covariance function does not match. All of the above papers consider geospatial applications.

### Non-Gaussian infinite-width limits of Bayesian neural networks
{: .accent}

<figure class="research-fig">
  <img src="/assets/img/research/KP.png" alt="With α-stable weights, prior draws are dominated by a few large jumps." loading="lazy">
  <figcaption><strong>With <a href="https://openreview.net/forum?id=usFdPd4Ghs">deep α-kernel processes</a>, priors can take large jumps, Gaussian process draws change less abruptly.</strong></figcaption>
</figure>

From the early works of Neal (1996), the infinite width Gaussian scaling limit of a Bayesian neural network with one hidden layer is a well known result, *provided the network weights have bounded prior variance*. The tractable properties of Gaussian processes then allow straightforward posterior uncertainty quantification. Neural network weights with unbounded variance, however, pose unique challenges. In this case, the classical central limit theorem breaks down and it is well known that the scaling limit is an α-stable process under suitable conditions. However, current literature is primarily limited to forward simulations under these processes and the problem of posterior inference under such a scaling limit remains largely unaddressed, unlike in the Gaussian process case. [Loría and Bhadra (2024, UAI)](https://proceedings.mlr.press/v244/loria24a.html) provide a computationally feasible approach for fully probabilistic posterior uncertainty quantification in this setting for a network with one hidden layer. Deployment to networks with multiple hidden layers with deep α-stable kernel machines is considered by [Loría and Bhadra (2025, ICLR)](https://openreview.net/forum?id=usFdPd4Ghs).


### Global-local shrinkage and the horseshoe+ estimator
{: .accent}

<figure class="research-fig">
  <img src="/assets/img/research/horseshoe_plus.png" alt="Marginal prior densities" loading="lazy">
  <figcaption><strong>The <a href="https://dx.doi.org/10.1214/16-BA1028">horseshoe+ prior</a> has a sharper spike at zero and heavier tails than the horseshoe; the Laplace prior has no spike and exponential tails.</strong> </figcaption>
</figure>

The horseshoe estimator of Carvalho, Polson and Scott (2010, Biometrika) was one of the first works to demonstrate the power of "global-local" shrinkage in ultra-sparse Bayesian variable selection problems. Since then, multiple attractive theoretical properties of this estimator have been discovered. In a collaborative work with [Nick Polson](http://www.chicagobooth.edu/faculty/directory/p/nicholas-polson), [Jyotishka Datta](https://www.stat.vt.edu/people/stat-faculty/datta-jyotishka.html) and [Brandon Willard](https://scholar.google.com/citations?user=g0oUxG4AAAAJ&hl=en), we propose a new estimator, termed the "horseshoe+ estimator," that improves upon the horseshoe, both theoretically and empirically. [Bhadra et al. (2017, BA)](https://dx.doi.org/10.1214/16-BA1028) give the details. It also appears global-local shrinkage priors are good candidates for default priors for low-dimensional, nonlinear functions in a normal means model, where the so-called "flat" priors fail. [Bhadra et al. (2016, Biometrika)](https://dx.doi.org/10.1093/biomet/asw041) demonstrate their use in a few such problems. [Bhadra et al. (2020a, Sankhya A)](https://doi.org/10.1007/s13171-019-00191-2) demonstrate the use of two integral identities for generating global-local mixtures. [Bhadra et al. (2019a, JMLR)](http://www.jmlr.org/papers/v20/18-321.html) formally demonstrate that the prediction performance for the class of global shrinkage regression methods (ridge regression, principal components regression etc.) can be improved by using local, component-specific shrinkage parameters. [Bhadra et al. (2020b, Sankhya B)](https://doi.org/10.1007/s13571-019-00217-7) derive fast computational algorithms to perform feature selection using the non-convex horseshoe regularization penalty. [Li, Craig and Bhadra (2019, JCGS)](https://doi.org/10.1080/10618600.2019.1575744) propose the use of the horseshoe prior in estimating the precision matrix for multivariate Gaussian data. [Bhadra et al. (2019b, Stats. Sci.)](https://doi.org/10.1214/19-STS700) is a review article summarizing the important developments in global-local shrinkage methods in linear models in the past decade. [Bhadra et al. (2020c, ISR)](https://doi.org/10.1111/insr.12360) is another review article focusing on recently emerging uses of horseshoe regularization in modern machine learning applications, specifically in complex and deep models.

### Bayesian models for joint mean-covariance estimation and for mixed discrete-continuous data
{: .accent}

<figure class="research-fig">
  <img src="/assets/img/research/HSGHS_graph.png" alt="Graph of MAPK pathway by HSGHS" loading="lazy">
  <figcaption><strong>Inferred graph of gene expressions in the MAPK pathway by the <a href="https://doi.org/10.1016/j.jmva.2020.104716">HS-GHS</a> estimate.</strong> </figcaption>
</figure>

Bayesian variable and covariance selections have been treated separately in the statistics literature for a long time. We do a combined analysis in the context of a Gaussian sparse seemingly unrelated regression (SSUR) model to infer jointly the important sparse set of predictors as well as the important sparse set of non-zero partial correlations in the responses. We apply our technique to expression quantitative trait loci ([eQTL](https://en.wikipedia.org/wiki/Expression_quantitative_trait_loci)) analysis where the expression level of a gene (response) is typically affected by a set of important SNPs (predictors) and the responses exhibit conditional dependence among themselves. Both the number of predictors and the number of correlated responses routinely exceed the sample size. We find that a marginalization-based collapsed Gibbs sampler offers a computationally efficient solution. The first ideas appeared in [Bhadra and Mallick (2013, Biometrics)](http://dx.doi.org/10.1111/biom.12021). Building on that, [Feldman, Bhadra and Kirshner (2014, Stat)](http://dx.doi.org/10.1002/sta4.60) found a way to relax the need to be restricted to decomposable graphs. [Bhadra and Baladandayuthapani (2013, GENSIPS)](http://dx.doi.org/10.1109/GENSIPS.2013.6735913) is an application of the methodology to brain cancer (glioblastoma) data. [Bhadra, Rao and Baladandayuthapani (2018, Biometrics)](https://dx.doi.org/10.1111/biom.12711) developed a technique to perform network inference in presence of multivariate data that are of mixed discrete and continuous nature and [Chakraborty et al. (2024, AoAS)](https://doi.org/10.1214/24-AOAS1936) extended it to chain graph models for multiplatform genomic data in lung cancer. [Li et al. (2021, JMVA)](https://doi.org/10.1016/j.jmva.2020.104716) perform joint mean-covariance estimation in SUR models combining the horseshoe and graphical horseshoe priors.



