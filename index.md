### About

The user provide two arrays: one storing the MCMC samples and another containing
the corresponding gradient values of the log-posterior, and get a vector of indices
of the selected MCMC states. The resulting "thinned" chain will:

* be free of initial bias caused by the burn-in period,
* gain statistical efficiency in approximating the posterior distribution,
* be a more compact representation of the unprocessed MCMC output.

### Installation

Implementations of Stein Thinning are currently available for Python and MATLAB:

* [Install for Python](https://github.com/wilson-ye-chen/stein_thinning#installing-via-git)
* Install for MATLAB
* Install for R (Coming soon!)

### Get Started
### PyStan Examples
### Citing Stein Thinning
