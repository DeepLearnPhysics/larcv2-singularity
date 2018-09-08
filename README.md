[![license](https://img.shields.io/github/license/mashape/apistatus.svg)](https://raw.githubusercontent.com/DeepLearnPhysics/larcv2-singularity/master/LICENSE)
[![https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg](https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg)](https://singularity-hub.org/collections/459)
# larcv2-singularity
Singularity build scripts for [singularity hub](https://www.singularity-hub.org/collections/459). You can learn about Singularity in [our wiki](https://github.com/DeepLearnPhysics/playground-singularity/wiki) or [official doc](https://www.sylabs.io/docs/).

To `pull` the container, simply try
```
TAG=latest
singularity pull -n local.img shub://DeepLearnPhysics/larcv2-singularity:$TAG
```

For more fun things to do, you can read [our wiki](https://github.com/DeepLearnPhysics/playground-singularity/wiki).

## What's in the build?
All builds are based on **Ubuntu16.04 LTS** with some highlighted packages below
  * Python packages: `pip` `numpy` `scipy` `scikit` `opencv-python` `h5py` `tables` `pandas` `matplotlib` `ipython` `jupyter notebook` `pyyaml` `zmq`
  * Development kit: `g++`/`gcc` `libqt4-dev` `python-dev` `cuda-9.0` `cudnn-7` `cython`
  * Utility kit    : `git` `wget` `emacs` `vim` `asciinema`
 
We build 3 types of images.
* _Base_ image
  * Latest tag: **ub16.04-tf1.10.1-torch0.4.1**
  * `tensorflow-gpu` 1.10.1, `pytorch` 0.4.1
  * ```singularity pull -n local.img shub://DeepLearnPhysics/larcv2-singularity:ub16.04-tf1.10.1-torch0.4.1```
* _ROOT_ image (include _Base_)
  * Latest tag: **ub16.04-tf1.10-torch0.4.1-root6.14.04**
  * `ROOT` 6.14.04, additional python package `root_numpy`
  * ```singularity pull -n local.img shub://DeepLearnPhysics/larcv2-singularity:ub16.04-tf1.10.1-torch0.4.1-root6.14.04```
* _LArCV_ image (include _ROOT_)
  * Tag: **latest**
  * Additional python package `larcv`
  * ```singularity pull -n local.img shub://DeepLearnPhysics/larcv2-singularity:latest```

# Docker images?
Checkout built images on our [docker hub](https://hub.docker.com/u/deeplearnphysics/dashboard/).
