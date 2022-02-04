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

* [LHRWBY2021](./prj/LHRWBY2021) Computational analyses discussed in

__Dangping Luo, Jose C. Huguet-Tapia, R. Taylor Raborn, Frank F. White, Volker P. Brendel & Bing Yang (2021)__
__Luo, D., Huguet-Tapia, J.C., Raborn, R.T., White, F.F., Brendel, V.P. & Yang, B. (2021)__
_The Xa7 resistance gene guards the rice susceptibility gene SWEET14 against exploitation by the bacterial blight pathogen._
[Plant Communications 2, 100164](https://www.sciencedirect.com/science/article/pii/S2590346221000390). 
