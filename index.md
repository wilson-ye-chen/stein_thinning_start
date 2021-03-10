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
has a positive and differentiable density <img alt="formula" src="https://render.githubusercontent.com/render/math?math=p(x)" /> on <img alt="formula" src="https://render.githubusercontent.com/render/math?math=\mathbb{R}^d" />.

In [Python](https://github.com/wilson-ye-chen/stein_thinning#getting-started),
[MATLAB](https://github.com/wilson-ye-chen/stein_thinning_matlab#getting-started),
or R, it takes a single function call to start Stein Thinning:
```python
indices = thin(samples, gradients, m)
```

Here 
* ```samples``` is an array with <img alt="formula" src="https://render.githubusercontent.com/render/math?math=n" /> rows and <img alt="formula" src="https://render.githubusercontent.com/render/math?math=d" /> columns, whose rows are the samples <img alt="formula" src="https://render.githubusercontent.com/render/math?math=x" /> produced by a sampling method, such as MCMC
* ```gradients``` is an array with <img alt="formula" src="https://render.githubusercontent.com/render/math?math=n" /> rows and <img alt="formula" src="https://render.githubusercontent.com/render/math?math=d" /> columns, whose rows contain <img alt="formula" src="https://render.githubusercontent.com/render/math?math=\nabla%20\log%20p(x)" /> where <img alt="formula" src="https://render.githubusercontent.com/render/math?math=x" /> is the corresponding row of ```samples```
* ```m``` is an integer, specifying the number of representative samples required
* ```indices``` is a sequence of integers in <img alt="formula" src="https://render.githubusercontent.com/render/math?math=\{1,\dots,n\}" />, indicating which samples were selected

### Stan Examples

Stein Thinning can be used to post-process the output from:
* [PyStan](https://github.com/wilson-ye-chen/stein_thinning#pystan-example)
* MatlabStan
* RStan

### Citing Stein Thinning

Riabiz M, Chen WY, Cockayne J, Swietach P, Niederer SA, Mackey L, Oates CJ.
Optimal Thinning of MCMC Output. [arXiv](https://arxiv.org/abs/2005.03952)
