##  Description 

This directory contains datafiles storing the analysis of:

* average _N<sub>c</sub>_ (number of heavy-atoms with residue i)
* average _N<sub>h</sub>_ (number of backbone hydrogen bonds)

for 72 amides of ubiquitin and 30 amides of BPTI.

As described in Wan et al. (JCTC 2020), a number of parameters are explored in computing these averages. The number of heavy-atom contacts are computed using sigmoidal distance-cutoff: 

N_c = \sum_j exp(-b(x - x_c)/(1 + exp(-b(x - x_c))


If _x_ is the distance backbone amide nitrogen of residue i to other heavy atoms j 

_N<sub>c</sub>_(x<sub>c<\sub>, b) 
_N<sub>h</sub>_(x<sub>h<\sub>, b)



### Trajectory data

We analyzed:

* a native-state ubiquitin simulation (performed at 300 K with 5581 water molecules, DEShaw Research) containing 50000 snapshots taken every 20 ns.
* a (71−83.5 μs) segment of native-state BPTI simulation (performed at 300 K with 4215 water molecules, DEShaw Research) containing 50000 frames taken every 250 ps.

## Data files




results1: all o xygens for h-bond
results2: only c=o oxygen for h-bond


## References

Hongbin Wan, Yunhui Ge, Asghar Razavi and Vincent A. Voelz*
Reconciling Simulated Ensembles of Apomyoglobin with Experimental Hydrogen/Deuterium Exchange Data Using Bayesian Inference and Multiensemble Markov State Models
J. Chem. Theory Comput. 2020, 16, 2, 1333-1348
https://doi.org/10.1021/acs.jctc.9b01240

