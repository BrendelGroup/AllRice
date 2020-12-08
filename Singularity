bootstrap: docker
From: ubuntu:14.04

%help
    This container provides a working version of DiscovarDeNovo.
    (Note: The code does not compile on newer gcc versions in our hands.)

%post
    export DEBIAN_FRONTEND=noninteractive
    apt -y update
    apt -y install build-essential
    apt -y install git tcsh tzdata unzip wget zip
    apt -y install ncurses-dev libcurl4-openssl-dev zlib1g-dev libbz2-dev liblzma-dev
    apt -y install libjemalloc-dev
    apt -y install python python-biopython


### Installing prerequisites and DiscovarDeNovo

    echo 'Installing HTSLIB from http://www.htslib.org/ '
    cd /opt
    git clone git://github.com/samtools/htslib.git htslib
    cd htslib
    make && make install

    echo 'Installing SAMTOOLS from http://www.htslib.org/ '
    cd /opt
    git clone git://github.com/samtools/samtools.git samtools
    cd samtools
    make && make install

    echo 'Installing DiscovarDenovo from https://software.broadinstitute.org/software/discovar/blog/ '
    cd /opt
    wget ftp://ftp.broadinstitute.org/pub/crd/DiscovarDeNovo/latest_source_code/discovardenovo-52488.tar.gz
    tar xzf discovardenovo-52488.tar.gz
    cd discovardenovo-52488
    ./configure
    make && make install


### Installing additional software

    echo 'Installing scripts from AllRice repository '
    cd /opt
    git clone https://github.com/BrendelGroup/AllRice
    cp AllRice/bin/* /usr/local/bin

    echo 'Installing BLAST+ version 2.10.1 from NCBI'
    wget ftp://ftp.ncbi.nlm.nih.gov/blast/executables/blast+/2.10.1/ncbi-blast-2.10.1+-x64-linux.tar.gz
    tar -xzf ncbi-blast-2.10.1+-x64-linux.tar.gz
    cd ncbi-blast-2.10.1+/bin
    cp * /usr/local/bin/
    cd ../..
    rm ncbi-blast-2.10.1+-x64-linux.tar.gz
    cd ..

    echo 'Installing GenomeThreader version 1.7.3 spliced aligner '
    cd /opt
    wget http://genomethreader.org/distributions/gth-1.7.3-Linux_x86_64-64bit.tar.gz
    tar -xzf gth-1.7.3-Linux_x86_64-64bit.tar.gz
    rm gth-1.7.3-Linux_x86_64-64bit.tar.gz
    ln -s gth-1.7.3-Linux_x86_64-64bit GENOMETHREADER


%environment
    export LC_ALL=C
    export PATH=$PATH:/opt/GENOMETHREADER/bin
    export BSSMDIR="/opt/GENOMETHREADER/bin/bssm"
    export GTHDATADIR="/opt/GENOMETHREADER/bin/gthdata"

%labels
    Maintainer vpbrendel
    Version v1.1
