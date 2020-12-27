# AllRice
Code for rice genome analyses (but not necessarily only rice)

## Quick Start [![https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg](https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg)](https://singularity-hub.org/collections/5032)

The easiest way to access the code is via the
[Singularity](https://www.sylabs.io/docs/) containers available from
[Singularity Hub](https://singularity-hub.org/).
Thus, once you know what you are doing, execution could be as simple as

```bash
singularity pull --name AllRice.sif shub://BrendelGroup/AllRice:latest
singularity pull --name DDN.sif     shub://BrendelGroup/AllRice:ddn
```

which provides, for example:

```bash
singularity exec -e -B ${PWD} AllRice.sif  ngsutilsj help
singularity exec -e -B ${PWD} AllRice.sif  umi_tools --help
singularity exec -e -B ${PWD} DDN.sif      DiscovarDeNovo -h
```

## Projects

* [LTRWBY2021](./prj/LTRWBY2021) Computational analyses discussed in

  Dangping Luo, Jose Huguet-Tapia, Taylor R. Raborn, Frank F. White2, Volker P. Brendel, and Bing Yang (2021)
  The TAL effector-induced R gene Xa7 of rice protects the S gene SWEET14.
  submitted




