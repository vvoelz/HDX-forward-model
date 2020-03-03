# HDX-forward-model

Scripts for calculating the posterior distribution of ln PF model parameters as described in Wan et al. JCTC 2020

## Contents

`experimental-data` - Experimental HDX protection factors (ln PF) data for ubiquitin and BPTI

`simulation-data` - Analysis of <N\_c> and <N\_h> from D.E.Shaw trajectory data

`posterior`  - scripts to do the posterior sampling of ln PF forward model parameters

## Requirements

The scripts are written in python 3 Jupyter notebooks.

The Anaconda python distribution is recommended: https://www.anaconda.com/distribution/ . You will need:
*  Jupyter
* `numpy` 
* `pandas` 
* `matplotlib` for plotting and visualization


## Reference

Hongbin Wan, Yunhui Ge, Asghar Razavi and Vincent A. Voelz.
Reconciling Simulated Ensembles of Apomyoglobin with Experimental Hydrogen/Deuterium Exchange Data Using Bayesian Inference and Multiensemble Markov State Models J. Chem. Theory Comput. 2020, 16, 2, 1333-1348 https://doi.org/10.1021/acs.jctc.9b01240
