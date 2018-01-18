[![license](https://img.shields.io/github/license/mashape/apistatus.svg)](https://raw.githubusercontent.com/DeepLearnPhysics/larcv2-singularity/master/LICENSE)
# larcv2-singularity
Singularity build scripts for [singularity hub](https://www.singularity-hub.org/collections/459). 
To build the container, simply try
```
TAG=ubuntu16.04-larcv_develop
singularity build local.simg shub://DeepLearnPhysics/larcv2-singularity:$TAG
```
To run the container after the build, try
```
singularity exec local.simg bash
```
If you are to use "gpu" tags and want to use gpus, don't forget `--nv` option
```
singularity exec --nv local.simg bash
```
For more fun things to do, you can singularity's [Quick Start](http://singularity.lbl.gov/quickstart) guide.
## Tags
There are 2 Ubuntu16.04 tags used as the base image for larcv builds.
* **ubuntu16.04-basic**
  * Python packages: `pip` `numpy` `larcv` `matplotlib` `pandas` `ipython` `jupyter notebook`
  * Development kit: `g++`/`gcc` `libqt4-dev` `python-dev` `nvcc`
  * Utility kit    : `git` `wget` `emacs` `vim`
* **ubuntu16.04-gpu**
  * ubuntu16.04-basic + `cuda8.0` + `cudnn6` + `tensorflow`

There are 2 tags with compiled larcv2 with ready-to-use shell environment
* **ubuntu16.04-larcv_develop**
  * Built on `ubuntu16.04-basic` tag
* **ubuntu16.04-gpu-larcv_develop**
  * Built on `ubuntu16.04-gpu` tag

# Docker images?
Checkout built images on our [docker hub](https://hub.docker.com/u/deeplearnphysics/dashboard/).
