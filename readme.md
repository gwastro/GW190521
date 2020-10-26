# GW190521
**Alexander H. Nitz<sup>1,2</sup>, Collin D. Capano<sup>1,2</sup>**

 <sub>1. [Albert-Einstein-Institut, Max-Planck-Institut for Gravitationsphysik, D-30167 Hannover, Germany](http://www.aei.mpg.de/obs-rel-cos)</sub>  
 <sub>2. Leibniz Universitat Hannover, D-30167 Hannover, Germany</sub> 
  

This repository is a companion to [Nitz and Capano (https://arxiv.org/abs/2010.12558)](https://arxiv.org/abs/2010.12558). 
It contains posterior probability density files from the parameter estimation analysis described in the paper and the
configuration files needed to run the analysis. We encourage use of these data in derivative works. 
If you use the material provided here, please cite the paper using the reference:

```
@article{Nitz:2020,
    author = "Nitz, Alexander H. and Collin D. Capano",
    title = "{GW190521 may be an intermediate mass ratio inspiral}",
    eprint = "2010.12558",
    archivePrefix = "arXiv",
    primaryClass = "gr-qc",
    month = "10",
    year = "2020"
}
```
## Abstract for "GW190521 may be an intermediate mass ratio inspiral" ##

GW190521 is the first confident observation of a binary black hole merger with total mass M >
100 M. Given the lack of observational constraints at these masses, we analyze GW190521 considering
two different priors for the binary’s masses: uniform in mass ratio and source-frame total mass, and
uniform in source-frame component masses. For the uniform in mass-ratio prior, we find that the
component masses are msrc
1 = 168+15
−61 M and msrc
2 = 16+33
−3 M. The uniform in component-mass
prior yields a bimodal posterior distribution. There is a low-mass-ratio mode (q < 4) with msrc
1 =
100+17
−18 M and msrc
2 = 57+17
−16 M and a high-mass-ratio mode (q ≥ 4) with msrc
1 = 166+16
−35 M and
msrc
2 = 16+14
−3 M. Although the two modes have nearly equal posterior probability, the maximumlikelihood parameters are in the high-mass ratio mode, with msrc
1 = 171 M and msrc
2 = 16 M, and
a signal-to-noise ratio of 16. These results are consistent with the proposed “mass gap” produced
by pair-instability in supernova. Our results are inconsistent with those published in Abbott et al.
(2020b). We find that a combination of the prior used and the constraints applied may have prevented
that analysis from sampling the high-mass-ratio mode. An accretion flare in AGN J124942.3+344929
was observed in possible coincidence with GW190521 by the Zwicky Transient Facility (ZTF). We
report parameters assuming a common origin; however, the spatial agreement of GW190521 and the
EM flare alone does not provide convincing evidence for the association (ln B & −4).

## Posterior files ##

HDF files containing posterior samples are in the `posteriors` directory. Each posterior is split into 5 files (due to github file size constraints). 
Samples are stored as 1D arrays in the `samples` group in the posterior files.
There is a separate dataset for each parameter that was varied in the analysis, along with a dataset for the log likelihood at that point. The parameters are:

Parameter | Description
--------- | -----------
`srcmass1` | The source-frame mass of the larger object, in solar masses.
`srcmass2` | The source-frame mass of the smaller object, in solar masses.
`spin1_a` | The magnitude of the dimensionless spin of the larger object.
`spin2_a` | "" smaller object.
`spin1_azimuthal` | The azimuthal angle of the dimensionless spin of the larger object.
`spin2_azimuthal` | "" smaller object.
`spin1_polar`| The polar angle of the dimensionless spin of the smaller object.
`spin2_polar` | "" smaller object.
`ra` | The right ascension of the binary, in radians.
`dec` | The declination of the binary, in radians.
`comoving_volume` | The comoving volume (in Mpc<sup>3</sup>). To convert to luminosity distance we use standard Lambda-CDM cosmology, with values from the [Planck 2015 results](https://doi.org/10.1051/0004-6361/201525830).
`inclination` | The angle between the orbital angular momentum and the line of sight to the binary at the reference frequency (stored as `f_ref` in the file's `attrs`), in radians.
`delta_tc` | The difference between the measured coalescence time of the event and a reference GPS time, which is stored in the file's `attrs` as `trigger_time`.
`loglikelihood` | The log of the likelihood at the given point.
`maxl_coa_phase` | Phase is marginalized in the likelihood. This gives the maximum likelihood phase for each sample.
`maxl_polarization` | The polarization angle is marginalized in the likelihood. This gives the maximum likelihood angle for each sample.
`maxl_loglr` | The unmarginalized (over phase and polarization angle) maximum likelihood for each sample. 

The files contain metadata about the analysis, including the parameters that were fixed. These can be found in the files' `attrs`.
There are five file sets, the posteriors IMRPhenomXPN and NRSur7dq4 both with and without constraint
on the EM flare location. There is also a reweighted set that converts the XPHM gw-only results into 
source-frame uniform in component mass priors.

## Configuration files

The configuration files used in the analyses are in the `configuration` directory. These specify the prior, sampler, model used, and the data analyzed. 

## License ##
![Creative Commons License](https://i.creativecommons.org/l/by-sa/3.0/us/88x31.png "Creative Commons License")

This work is licensed under a [Creative Commons Attribution-ShareAlike 3.0 United States License](http://creativecommons.org/licenses/by-sa/3.0/us/).

