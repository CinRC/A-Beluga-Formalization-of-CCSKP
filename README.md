# Overview
This repository contains the source code for the paper "A Formalization of the Reversible Concurrent Calculus CCSK<sup>P</sup> in Beluga", accepted at [ICE 2025](https://ice-workshop.github.io/). The artifact is also available in [Zenodo](https://doi.org/10.5281/zenodo.15660906). Below are install and usage instructions.

The `code\` repository provides an overview of the files and a paper-to-artifact table. The `.github\workflows\` repository contains a workflow that can be built to automatically check the code. ![Build status](https://github.com/CinRC/Beluga_implementation/actions/workflows/build.yaml/badge.svg)

## Install instructions
This mechanization is compatible with [Beluga](https://complogic.cs.mcgill.ca/beluga/) version 1.1.1.

For installation, please refer to the [installation guide](https://github.com/Beluga-lang/Beluga/blob/master/INSTALL) in the GitHub repository of Beluga. Below is a summary.

### Prerequisites
The following must be installed before proceeding with the installation of Beluga:

- opam 2.1.4+:             https://opam.ocaml.org/doc/Install.html
- GNU Make 4.0+:           https://www.gnu.org/software/make/
- (optional, for improved beli mode) rlwrap:                  https://github.com/hanslub42/rlwrap


### Debian/Ubuntu
All the necessary prerequisites can be installed with the following commands:

```
$ apt-get install opam
$ opam init --bare
```
And then, from the Beluga directory:
```
$ make setup-install
$ make install
```

### macOS
The easiest way to install the prerequisites is via opam, and the easiest way to install opam is via Homebrew (https://brew.sh/):

```
$ brew install opam
$ opam init --bare
```
And then, from the Beluga directory:
```
$ make setup-install
$ make install
```

### Windows
One option is to install the Ubuntu WSL distribution (https://docs.microsoft.com/en-us/windows/wsl/install) and follow the instructions for Debian/Ubuntu systems.

Another option is to build and execute Beluga on Windows through Cygwin. The necessary prerequisites can be installed using opam for Windows. Here are the steps to follow for the installation through Cygwin:

1. Download opam for Windows' graphical installer OCaml32/64.exe https://fdopen.github.io/opam-repository-mingw/installation/

2. Run OCaml32/64.exe and step through the installation wizard. Note: if you don't already have Cygwin installed, it will be installed for you.

3. Run the following commands from Beluga directory within cygwin terminal.

```
$ opam switch create ocaml-variants.4.09.0+mingw64c
$ eval $(opam env)
```
And then, from the Beluga directory:
```
$ opam install --deps-only ./beluga.opam
```

## Usage instructions
Once Beluga is installed, it is possible to run Beluga programs with the newly built "beluga" executable. Before, it might be necessary to execute the command `eval $(opam env)` to enable the correct opam switch.

To type-check this artifact, you can run the "beluga" executable on the file `all.cfg`. The following is the expected output:

```
>> beluga all.cfg
## Type Reconstruction begin: code/1_definitions.bel ##
## Type Reconstruction done:  code/1_definitions.bel ##
## Type Reconstruction begin: code/2_basic_properties.bel ##
## Type Reconstruction done:  code/2_basic_properties.bel ##
## Type Reconstruction begin: code/3_lemmas_connectivity_relationship_one.bel ##
## Type Reconstruction done:  code/3_lemmas_connectivity_relationship_one.bel ##
## Type Reconstruction begin: code/4_connectivity_relationship_one.bel ##
## Type Reconstruction done:  code/4_connectivity_relationship_one.bel ##
## Type Reconstruction begin: code/5_lemmas_connectivity_relationship_two.bel ##
## Type Reconstruction done:  code/5_lemmas_connectivity_relationship_two.bel ##
## Type Reconstruction begin: code/6_connectivity_relationship_two.bel ##
## Type Reconstruction done:  code/6_connectivity_relationship_two.bel ##
## Type Reconstruction begin: code/7_complementarity.bel ##
## Type Reconstruction done:  code/7_complementarity.bel ##
```
