[![license](https://img.shields.io/github/license/mashape/apistatus.svg)](https://raw.githubusercontent.com/DeepLearnPhysics/larcv2-singularity/master/LICENSE)
[![https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg](https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg)](https://singularity-hub.org/collections/1864)

# larcv2-singularity
This repo is forked from the Deep Learn Physics larcv2-singularity repo.  That repo is focused on ubuntu images, here most images are available on top of centos7 instead and designed for an HPC environment.

Singularity build scripts for [singularity hub](https://www.singularity-hub.org/collections/459). You can learn about Singularity in [our wiki](https://github.com/DeepLearnPhysics/playground-singularity/wiki) or [official doc](https://www.sylabs.io/docs/).

For more fun things to do, you can read [our wiki](https://github.com/DeepLearnPhysics/playground-singularity/wiki).

## What's in the build?
All builds are based on **Centos7** with some highlighted packages below
  * Python packages: `pip` `numpy` `scipy` `scikit` `opencv-python` `h5py` `tables` `pandas` `matplotlib` `ipython` `jupyter notebook` `pyyaml` `zmq`
  * Development kit: `g++`/`gcc` `libqt4-dev` `python-dev` `cython`
  * Utility kit    : `git` `wget` `emacs` `vim` `asciinema`
 
For the cuda images: `cuda-9.0` `cudnn-7`
 
We build 3 flavors of image:
 * CUDA - bootstrapped from nvidia docker files
 * CPU - basic CPU implementations 
 * MKL-DNN CPU - optimized images for KNL nodes with MKL-DNN
 
For each flavor of images, there can be (but is not always) a tensorflow or a pytorch build.  Both are kept to the latest versions.  Pytorch typically comes with the tools needed for Submanifold Sparse Convolutions.
 
We build 3 types of images for each flavor/framework combination.
* _Base_ image
 * Core development tools (including upgraded gcc) as well as the basic framework (pytorch/tensorflow) with support for the acceleration as needed.
  
* _MPI_ image (include _Base_)
  * Adds MPICH3.2.1, and horovod if possible (not yet working for pytorch GPU, has to be built by hand).  Adds NCCL2 for GPU builgs
  
* _ROOT_ image (include _MPI_)
  * Additional python package `ROOT`
 
