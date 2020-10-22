# GW190521
**Alexander H. Nitz<sup>1,2</sup>, Collin D. Capano<sup>1,2</sup>**

 <sub>1. [Albert-Einstein-Institut, Max-Planck-Institut for Gravitationsphysik, D-30167 Hannover, Germany](http://www.aei.mpg.de/obs-rel-cos)</sub>  
 <sub>2. Leibniz Universitat Hannover, D-30167 Hannover, Germany</sub> 

This repository is a companion to [Nitz and Capano (arXiv:XXXX.XXXXX)](https://arxiv.org/abs/XXXX.XXXXX). 
It contains posterior probability density files from the parameter estimation analysis described in the paper and the
configuration files needed to run the analysis. We encourage use of these data in derivative works. 
If you use the material provided here, please cite the paper using the reference:

```
@article{Nitz:2020dix,
    author = "Capano, Collin D. and Nitz, Alexander H.",
    title = "{PLACEHOLDER}",
    eprint = "2008.02248",
    archivePrefix = "arXiv",
    primaryClass = "gr-qc",
    month = "8",
    year = "2020"
}
```

## Posterior files ##

HDF files containing posterior samples are in the `posteriors` directory. Each posterior is split into 5 files (due to github file size constraints). 
Samples are stored as 1D arrays in the `samples` group in the posterior files. T
here is a separate dataset for each parameter that was varied in the analysis, along with a dataset for the log likelihood at that point. The parameters are:

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

## Configuration files

The configuration files used in the analyses are in the `configuration` directory. These specify the prior, sampler, model used, and the data analyzed. 

## License ##
![Creative Commons License](https://i.creativecommons.org/l/by-sa/3.0/us/88x31.png "Creative Commons License")

This work is licensed under a [Creative Commons Attribution-ShareAlike 3.0 United States License](http://creativecommons.org/licenses/by-sa/3.0/us/).

