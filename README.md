# multiESS

Compute the multivariate effective sample size (*mESS*) of a Markov chain,
using the multivariate dependence structure of the process.

This is a Python implementation of the [MATLAB implementation][3] of the *mESS*
estimation method described in [Vats et al. (2015)][1]

The MATLAB code has some minor tweaks for the choice of batch size *b* for the 
computation of the Monte Carlo covariance matrix.

See also the R package [mcmcse][1] for a separate implementation.

*Disclaimer:* This is a stripped down version of the original MATLAB code.
Most notably it does neither accept nor return the Monte Carlo covariance
matrix and does snot return the batch size.

## Details

The effective sample size of a Markov chain is the size of an i.i.d. sample
with the same covariance structure as the current chain.

*mESS* is given by

    *mESS* = *n* |Λ|^{1/*p*}/ |Σ|^{1/*p*}

where *n* is the current sample size, Λ is the sample covariance matrix,
*p* is the number of parameters and Σ is an estimate of the Monte Carlo
covariance matrix for the Markov chain (here obtained by batch estimation).

### Reference

[Vats, D., Flegal, J. M., & Jones, G. L. "Multivariate Output Analysis for
Markov chain Monte Carlo", arXiv preprint arXiv:1512.07713 (2015)][2]

[1]: https://cran.r-project.org/web/packages/mcmcse/index.html
[2]: http://arxiv.org/abs/1512.07713
[3]: https://github.com/lacerbi/multiESS
