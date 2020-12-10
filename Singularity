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
    dnf -y install python python-biopython python-wheel-wheel python3-virtualenv python3-pip
    dnf -y install pandoc
    dnf -y install java-11-openjdk java-11-openjdk-devel ant


### Read quality control

    echo 'Installing FASTQC from http://www.bioinformatics.babraham.ac.uk/projects/fastqc/ '
    cd /opt
    wget http://www.bioinformatics.babraham.ac.uk/projects/fastqc/fastqc_v0.11.8.zip
    unzip fastqc_v0.11.8.zip
    chmod +x FastQC/fastqc

    echo 'Installing Trimmomatic from http://www.usadellab.org/cms/index.php?page=trimmomatic '
    cd /opt
    wget http://www.usadellab.org/cms/uploads/supplementary/Trimmomatic/Trimmomatic-0.39.zip
    unzip Trimmomatic-0.39.zip
#   Use:	java -jar /opt/Trimmomatic-0.39/trimmomatic-0.39.jar


### Read manipulation

    echo 'Installing SRATOOLKIT from http://www.ncbi.nlm.nih.gov/books/NBK158900/ '
    cd /opt
    wget http://ftp-trace.ncbi.nlm.nih.gov/sra/sdk/2.10.5/sratoolkit.2.10.5-ubuntu64.tar.gz
    tar -xzf sratoolkit.2.10.5-ubuntu64.tar.gz

    echo 'Installing UMI-tools from https://github.com/CGATOxford/UMI-tools '
    pip3 install --upgrade umi-tools


### Alignment software

    echo 'Installing BLAST+ version 2.10.1 from NCBI'
    cd /opt
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


### Utilities

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

    echo 'Installing ngsutilsj '
    cd /opt
    git clone https://github.com/compgen-io/ngsutilsj
    cd ngsutilsj
    ant jar
    ln -s /opt/ngsutilsj/dist/ngsutilsj /usr/local/bin/ngsutilsj


%environment
    export LC_ALL=C
    export PATH=$PATH:/opt/FastQC
    export PATH=$PATH:/opt/sratoolkit.2.10.5-ubuntu64/bin
    export PATH=$PATH:/opt/GENOMETHREADER/bin
    export BSSMDIR="/opt/GENOMETHREADER/bin/bssm"
    export GTHDATADIR="/opt/GENOMETHREADER/bin/gthdata"

%labels
    Maintainer vpbrendel
    Version v1.1
