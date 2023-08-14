# python-intro
A very quick lesson for getting started with Python. 

Written by Joseph Plummer for demonstration purposes only.

## Recommended settings:
I tested this code on Ubuntu 20.04 through WSL2, inside my Windows terminal.
I have an NVIDIA GPU, working on Windows, WSL2, and Linux. This code should work for all operating systems. 
If the following settings fail, conda create an environment yourself, and install the pip packages manually/through git.
Also, make sure you have your git SSH keys set (you may have to do this for each terminal/git browser/VScode that you operate).


## Installation.

Navigate to the folder containing this code inside the terminal. Run the following commands in sequence to create your environment.

1. `conda update -n base -c defaults conda`
2. `make conda`
3. `conda activate qia`
4. `make pip`

**Troubleshooting**:

1. This repository was tested on an NVIDIA GPU. If running on a system without
   the same, please remove the following packages from `environment.yaml`:
   - `cudnn`
   - `nccl`
   - `cupy`
2. If not using an NVIDIA GPU, please set `devnum = -1` where called.
3. When running `make pip`, `git clone git+https://github.com/mikgroup/sigpy.git@main`
   will error if GitHub ssh keys are not set. Please replace that line in the
   `Makefile` with `git clone https://github.com/mikgroup/sigpy.git@main` and
   run `make pip` again.

## For activating display in WSL2:

Install XLaunch in Windows if not done already. 

1. `export DISPLAY=`grep -oP "(?<=nameserver ).+" /etc/resolv.conf`:0.0`
2. `export LIBGL_ALWAYS_INDIRECT=1`
3. Open XLaunch and set up (tick all three boxes)
4. Test with `xeyes`

## Uninstall.

To uninstall, run the following commands:

1. `conda activate`
2. `make clean`

## Packages used:

- [SigPy](https://github.com/mikgroup/sigpy) [![DOI](https://zenodo.org/badge/doi/10.5281/zenodo.5893788.svg)](https://doi.org/10.5281/zenodo.5893788)

