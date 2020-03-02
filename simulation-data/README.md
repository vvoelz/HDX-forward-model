##  Description 

This directory contains datafiles storing <_N<sub>c</sub>_> (average number of heavy-atoms with residue i) and  <_N<sub>h</sub>_> (average number of backbone hydrogen bonds) for 72 amides of ubiquitin and 30 amides of BPTI.  THe anlaysis comes from

* a 1-ms native-state ubiquitin simulation (performed at 300 K with 5581 water molecules, DEShaw Research) containing 50000 snapshots taken every 20 ns.
* a (71−83.5 μs) segment of native-state BPTI simulation (performed at 300 K with 4215 water molecules, DEShaw Research) containing 50000 frames taken every 250 ps.

As described in Wan et al. (JCTC 2020), a number of parameters are explored in computing these averages. The number of heavy-atom contacts are computed using sigmoidal distance-cutoff: 

N_c = \sum_j exp(-b(x_j - x_c)/(1 + exp(-b(x_j - x_c))

where x_j is the distance between backbone amide nitrogen to other heavy atoms j, x_c is the cut-off threshold, and _b_ is the sharpness of the sigmoidal cutoff.

Similarly, the number of hydrogen bonds are computed using

N_h = \sum_j exp(-b(x_j - x_h)/(1 + exp(-b(x_j - x_h))

where x_j is the distance the amide hydrogen and oxygen H-bond acceptors j, x_h is the cut-off threshold.

* Values x_c ranged from 5.0 to 8.0 Å in increments of 0.5 Å.
* Values of x_h ranged from 2.0 to 2.7 Å in increments of 0.1 Å.
* Values of b ranges from 3.0 to 20.0 Å<sup>-1</sup> in increments of 1.0 Å<sup>-1</sup>

## Data files

The analyzed N_c and N_h for each amide, calculated for a specific (x_c, x_h, b) tuple are stored in a series of numpy arrays named:

`result1/b7/avg_Nc_Nh_xc6.5_xh2.3_b7.npy`

The first column of this file are the <N_c> for each amide; the second column is <N_h>.

The first 72 rows are the ubiquitin amides; the last 30 rows are the BPTI amides.

```
>>> x_c = 6.5   # Angstroms
>>> x_h = 2.3 # Angstroms
>>> b = 7
>>> datafile = 'result1/b%d/avg_Nc_Nh_xc%0.1f_xh%0.1f_b%d.npy'%(b, x_c, x_h, b)  
>>> data = np.load(datafile)
>>> data.shape
 (102, 2)
```


## References

Hongbin Wan, Yunhui Ge, Asghar Razavi and Vincent A. Voelz*
Reconciling Simulated Ensembles of Apomyoglobin with Experimental Hydrogen/Deuterium Exchange Data Using Bayesian Inference and Multiensemble Markov State Models
J. Chem. Theory Comput. 2020, 16, 2, 1333-1348
https://doi.org/10.1021/acs.jctc.9b01240

