### About
Stein Thinning is able to post-process the output of any Markov chain Monte Carlo
(MCMC) procedure by optimally selecting a subset of realised states w.r.t. a kernel
Stein discrepancy.

The user provide two arrays: one storing the MCMC samples and another containing
the corresponding gradient values of the log-posterior, and get returned a vector
of indices of the selected MCMC states. The resulting "Stein thinned" chain will:

* be free of initial bias caused by the burn-in period,
* gain statistical efficiency in approximating the posterior distribution,
* offer a compressed representation of the MCMC output.

### Installation

Implementations of Stein Thinning are currently available for Python and MATLAB:

* [Install for Python](https://github.com/wilson-ye-chen/stein_thinning#installing-via-git)
* [Install for MATLAB](https://github.com/wilson-ye-chen/stein_thinning_matlab#installation)
* Install for R (Coming soon!)

### Get Started

In [Python](https://github.com/wilson-ye-chen/stein_thinning#getting-started),
[MATLAB](https://github.com/wilson-ye-chen/stein_thinning_matlab#getting-started),
or R, it takes a single function call to start Stein Thinning:
```python
indices = thin(samples, gradients, 100)
```

### Stan Examples

Stein Thinning can be used to post-process the output from:
* [PyStan](https://github.com/wilson-ye-chen/stein_thinning#pystan-example)
* MatlabStan
* RStan

### Citing Stein Thinning

Riabiz M, Chen WY, Cockayne J, Swietach P, Niederer SA, Mackey L, Oates CJ.
Optimal Thinning of MCMC Output. [arXiv](https://arxiv.org/abs/2005.03952)
