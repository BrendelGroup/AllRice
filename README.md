# AllRice
Code for rice genome analyses (but not necessarily only rice)

## Quick Start

The simplest way to get going is to use the AllRice
[Singularity](https://apptainer.org/) container available from our
[Singularity Hub](http://BrendelGroup.org/SingularityHub/) site; e.g.:


```bash
cd
git clone https://github.com/BrendelGroup/AllRice
cd AllRice
wget https://BrendelGroup.org/SingularityHub/AllRice.sif
alias rws="singularity exec -e -B ~/AllRice/prj/LHRWBY2021  ~/AllRice/AllRice.sif"
rws ngsutilsj help
rws umi_tools --help
rws flye --help
wget https://BrendelGroup.org/SingularityHub/DDN.sif
singularity exec -e -B ~/AllRice/prj/LHRWBY2021  ~/AllRice/DDN.sif  DiscovarDeNovo -h
```

In the above example, you clone this repository into your Linux home directory,
go into the thus created AllRice directory, download the AllRice Singularity
container, define the bash alias _rws_ ("run with singularity"), and check that
everything works by showing help information on some of the installed programs.
You then also download the DDN.sif image and show that you have the DiscoverDeNovo
assembler accessible.
For a listing of included software, see our [CATALOG](https://github.com/BrendelGroup/bgSingularityHub/blob/main/CATALOG.md).

Of course this assumes that you have [Apptainer/Singularity](https://apptainer.org/) installed on your system.
Check whether there is package built for your system.
Otherwise, follow the instructions to [install Singularity from source code](https://apptainer.org/user-docs/master/quick_start.html#quick-installation-steps).


## Projects

* [LHRWBY2021](./prj/LHRWBY2021) Computational analyses discussed in

__Luo, D., Huguet-Tapia, J.C., Raborn, R.T., White, F.F., Brendel, V.P. & Yang, B. (2021)__
_The Xa7 resistance gene guards the rice susceptibility gene SWEET14 against exploitation by the bacterial blight pathogen._
[Plant Communications 2, 100164](https://www.sciencedirect.com/science/article/pii/S2590346221000390). 

Follow the instructions in [0README](https://github.com/BrendelGroup/AllRice/blob/main/prj/LHRWBY2021/0README)
to reproduce the work (or use the workflow as a template for analysis of your own data sets).


## Contact

Please direct all comments and suggestions to
[Volker Brendel](<mailto:vbrendel@indiana.edu>)
at [Indiana University](http://brendelgroup.org/).
