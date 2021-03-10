### About
Stein Thinning is a tool for post-processing the output of a sampling procedure,
such as Markov chain Monte Carlo (MCMC). It aims to minimise a Stein discrepancy,
selecting a subsequence of samples that best represent the distributional target.

The user provides two arrays: one containing the samples and another containing
the corresponding gradients of the log-target. Stein Thinning returns a vector
of indices, indicating which samples were selected. In favourable circumstances, 
Stein Thinning is able to:

* automatically identify and remove the burn-in period from MCMC output,
* perform bias-removal for biased sampling procedures,
* provide improved approximations of the distributional target,
* offer a compressed representation of sample-based output.

### Installation

Implementations of Stein Thinning are currently available for Python and MATLAB:

* [Install for Python](https://github.com/wilson-ye-chen/stein_thinning#installing-via-git)
* [Install for MATLAB](https://github.com/wilson-ye-chen/stein_thinning_matlab#installation)
* Install for R (Coming soon!)

### Get Started

First, it is important to parametrise the distributional target so that it 
has a positive density on $`R^d`$.

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
