bootstrap: docker
From: fedora:33

%help
    This container provides working software versions for the AllRice project.

%post
    dnf -y update
    dnf -y install bc bzip2 findutils git lftp mlocate tcsh unzip zip wget which
    dnf -y install gcc-c++ make ruby
    dnf -y install cairo-devel pango-devel zlib-devel
    dnf -y install libnsl
    dnf -y install python python-biopython
    dnf -y install pandoc


### Installing software ...

    echo 'Installing BLAST+ version 2.10.1 from NCBI'
    cd /opt
    wget ftp://ftp.ncbi.nlm.nih.gov/blast/executables/blast+/2.10.1/ncbi-blast-2.10.1+-x64-linux.tar.gz
    tar -xzf ncbi-blast-2.10.1+-x64-linux.tar.gz
    cd ncbi-blast-2.10.1+/bin
    cp * /usr/local/bin/
    cd ../..
    rm ncbi-blast-2.10.1+-x64-linux.tar.gz
    cd ..

    echo 'Installing the GenomeTools package:'
    cd /opt
    git clone https://github.com/genometools/genometools.git
    cd genometools
    make
    make install
    make clean
    sh -c 'echo "/usr/local/lib" > /etc/ld.so.conf.d/genometools-x86_64.conf'
    ldconfig
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
