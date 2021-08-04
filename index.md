### About
Stein Thinning is a tool for post-processing the output of a sampling procedure,
such as Markov chain Monte Carlo (MCMC). It aims to minimise a Stein discrepancy,
selecting a subsequence of samples that best represent the distributional target.

<iframe width="520" height="293" src="https://www.youtube.com/embed/WwmTeLrNmOQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe><br/>

The user provides two arrays: one containing the samples and another containing
the corresponding gradients of the log-target. Stein Thinning returns a vector
of indices, indicating which samples were selected.

In favourable circumstances, Stein Thinning is able to:

* automatically identify and remove the burn-in period from MCMC,
* perform bias-removal for biased sampling procedures,
* provide improved approximations of the distributional target,
* offer a compressed representation of sample-based output.

### Installation

Implementations of Stein Thinning are available for Python, R, and MATLAB:

* [Install for Python](https://github.com/wilson-ye-chen/stein_thinning#installing-via-git)
* [Install for R](https://github.com/wilson-ye-chen/stein.thinning#installing-via-github)
* [Install for MATLAB](https://github.com/wilson-ye-chen/stein_thinning_matlab#installation)

### Get Started

First, it is important to parametrise the distributional target so that it
has a positive and differentiable density <img alt="formula" src="https://render.githubusercontent.com/render/math?math=p(x)" /> on <img alt="formula" src="https://render.githubusercontent.com/render/math?math=\mathbb{R}^d" />.

In [Python](https://github.com/wilson-ye-chen/stein_thinning#getting-started),
[R](https://github.com/wilson-ye-chen/stein.thinning#getting-started),
or [MATLAB](https://github.com/wilson-ye-chen/stein_thinning_matlab#getting-started),
it takes a single function call to start Stein Thinning:
```python
indices = thin(samples, gradients, m)
```

Here
* ```samples``` is an array with <img alt="formula" src="https://render.githubusercontent.com/render/math?math=n" /> rows and <img alt="formula" src="https://render.githubusercontent.com/render/math?math=d" /> columns, whose rows are the samples <img alt="formula" src="https://render.githubusercontent.com/render/math?math=x" /> produced by a sampling method, such as MCMC,
* ```gradients``` is an array with <img alt="formula" src="https://render.githubusercontent.com/render/math?math=n" /> rows and <img alt="formula" src="https://render.githubusercontent.com/render/math?math=d" /> columns, whose rows contain the gradients <img alt="formula" src="https://render.githubusercontent.com/render/math?math=\nabla%20\log%20p(x)" /> where <img alt="formula" src="https://render.githubusercontent.com/render/math?math=x" /> is the corresponding row of ```samples```,
* ```m``` is an integer, specifying the number of representative samples required,
* ```indices``` is a vector of length <img alt="formula" src="https://render.githubusercontent.com/render/math?math=m" />, whose elements are integers in <img alt="formula" src="https://render.githubusercontent.com/render/math?math=\{1,\dots,n\}" />, indicating which samples were selected.

### Stan Examples

Stein Thinning can be used to post-process the output directly from the Stan family of probabilistic programming languages:
* [PyStan](https://github.com/wilson-ye-chen/stein_thinning#pystan-example)
* [RStan](https://github.com/wilson-ye-chen/stein.thinning#rstan-example)
* [MatlabStan](https://mc-stan.org/users/interfaces/matlab-stan)

### Citing Stein Thinning

Riabiz M, Chen WY, Cockayne J, Swietach P, Niederer SA, Mackey L, Oates CJ (2021) Optimal Thinning of MCMC Output. Journal of the Royal Statistical Society, Series B, to appear. [arXiv](https://arxiv.org/abs/2005.03952)

### Papers Inspired By Stein Thinning

Teymur O, Gorham J, Riabiz M, Oates CJ (2021) Optimal Quantisation of Probability Measures Using Maximum Mean Discrepancy. International Conference on Artificial Intelligence and Statistics (AISTATS 2021). [Paper](http://proceedings.mlr.press/v130/teymur21a.html)

Chopin N, Ducrocq G (2021) Fast compression of MCMC output. [arXiv](https://arxiv.org/abs/2107.04552)

South LF, Riabiz M, Teymur O, Oates C (2021) Post-Processing of MCMC. Annual Reviews of Statistics and its Application, to appear. [arXiv](https://arxiv.org/abs/2103.16048)

### Acknowledgements

This work was supported by the Lloyd’s Register Foundation Programme on Data-Centric Engineering and the Programme on Health and Medical Sciences at The Alan Turing Institute (UK), the British Heart Foundation (SP/18/6/33805, RG/15/9/31534, PG/15/91/31812, FS/18/27/33543), the UK Research and Innovation Strategic Priorities Fund (EP/T001569/1), the UK Engineering and Physical Sciences Research Council (EP/P01268X/1, NS/A000049/1, EP/M012492/1), the UK National Institute for Health Research (II-LB-1116-20001) and the Wellcome Trust (WT 203148/Z/16/Z).
