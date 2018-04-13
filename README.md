# Measuring the viewing angle of GW170817 with electromagnetic and gravitational waves

**Daniel Finstad<sup>1</sup>, Soumi De<sup>1</sup>, Duncan A. Brown<sup>1</sup>, Edo Berger<sup>2</sup>, Christopher M. Biwer<sup>1,3</sup>**

**<sup>1</sup>Department of Physics, Syracuse University, Syracuse, NY 13244, USA**

**<sup>2</sup>Harvard-Smithsonian Center for Astrophysics, Cambridge, Massachusetts 02139, USA**

**<sup>3</sup>Applied Computer Science (CCS-7), Los Alamos National Laboratory, Los Alamos, NM, 87545, USA**

## License

![Creative Commons License](https://i.creativecommons.org/l/by-sa/3.0/us/88x31.png "Creative Commons License")

This work is licensed under a [Creative Commons Attribution-ShareAlike 3.0 United States License](http://creativecommons.org/licenses/by-sa/3.0/us/).

## Introduction

This notebook is a companion to the paper posted at [arxiv:1804.04179](https://arxiv.org/abs/1804.04179). It demonstrates how to read and use our posterior proability density files from the MCMC and shows how to reconstruct Figure 1 in the paper from the raw data.

We encourage use of these data in derivative works. If you use the material provided here, please cite the paper using the reference:
```
bibtex key here
```

The data provided contain the thinned posterior samples from the MCMC chains used to produce the posterior proability density plots shown in Figure 1. These data are stored in the files:

 1. [gw_only_posteriors.hdf](https://github.com/sugwg/gw170817-inclination-angle/blob/master/gw_only_posteriors.hdf)  contains the posterior samples from the MCMC where we only use the gravitational-wave data.
 2. [gw_and_skyloc_posteriors.hdf](https://github.com/sugwg/gw170817-inclination-angle/blob/master/gw_and_skyloc_posteriors.hdf) containes the posterior samples from the MCMC where we use the gravitational-wave data and fix the sky location of GW170817 to RA = 197.450374, Dec = -23.381495 from [Soares-Santos et al. (2017).](http://iopscience.iop.org/article/10.3847/2041-8213/aa9059/meta)

 3. [gw_skyloc_and_dist_posteriors.hdf](https://github.com/sugwg/gw170817-inclination-angle/blob/master/gw_skyloc_and_dist_posteriors.hdf) contains the posterior samples from the MCMC where we use the gravitational-wave data, fix the sky location of GW170817 to RA = 197.450374, Dec = -23.381495 from [Soares-Santos et al., (2017)](http://iopscience.iop.org/article/10.3847/2041-8213/aa9059/meta), and use a Gaussian prior on the luminosity distance taken from [Cantiello et al. (2018).](http://iopscience.iop.org/article/10.3847/2041-8213/aaad64/meta)

The results used in the paper were generated with the [PyCBC v1.9.4 release.](https://github.com/gwastro/pycbc/releases/tag/v1.9.4)

## Runing this notebook in a Docker container

This notebook can be run from a PyCBC Docker container, or a machine with PyCBC installed. Instructions for [downloading the docker container](http://gwastro.github.io/pycbc/latest/html/docker.html) are available from the [PyCBC home page.](https://pycbc.org/) To start a container with instance of Jupyter notebook, run the commands
```sh
docker pull pycbc/pycbc-el7:v1.9.4
docker run -p 8888:8888 --name pycbc_notebook -it pycbc/pycbc-el7:v1.9.4 /bin/bash -l
```
Once the container has started, this git repository can be downloaded with the command:
```sh
git clone https://github.com/sugwg/gw170817-inclination-angle.git
```
The notebook server can be started inside the container with the command:
```sh
jupyter notebook --ip 0.0.0.0 --no-browser
```
You can then connect to the notebook server at the URL printed by ``jupyter``. Navigate to the directory `gw170817-inclination-angle` in the cloned git repository and open [data_release_companion.ipynb](https://github.com/sugwg/gw170817-inclination-angle/blob/master/data_release_companion.ipynb), the notebook that demonstartes use of these reults.

## Acknowlegdements

We thank Stefan Ballmer and Steven Reyes for useful discussions. We thank Alexander H. Nitz and Collin D. Capano for useful discussions on setting up this notebook.
We particularly thank Collin D. Capano for contributing to the development of PyCBC Inference; unfortunately, he did not wish to be an author of this work because of restrictions required by the LIGO Scientific Collaboration policies. 

### Funding

This work was supported by U.S. National Science Foundation awards PHY-1404395 (DAB, CMB), PHY-1707954 (DAB, SD, DF) and AST-1714498 (EB). Computational work was supported by Syracuse University and National Science Foundation award OAC-1541396. DAB, EB, and SD acknowledge the Kavli Institute for Theoretical Physics which is supported by the National Science Foundation award PHY-1748958. 

### Authors contributions:
Conceptualization, DAB and EB; Methodology, DAB, EB, CMB, SD, and DF; Software: CMB and CDC; Validation: SD; Formal Analysis: DF; Investigation: SD and DF; Resources: DAB; Data Curation: DAB and DF; Writing – Original Draft: DF; Writing – Review and Editing: DAB, EB, CMB, SD, and DF; Visualization: DF, CDC, AHN; Supervision: DAB; Project Administration: DAB; Funding Acquisition: EB, DAB.



