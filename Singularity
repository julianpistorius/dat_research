Bootstrap: debootstrap
OSVersion: xenial

MirrorURL:  http://us.archive.ubuntu.com/ubuntu/

%help
Help me. I'm in the container.

%setup
    touch ${SINGULARITY_ROOTFS}/tacos.txt
    touch avocados.txt

%post 
    apt-get install --yes wget git
    wget https://deb.nodesource.com/setup_9.x -O nodesource_setup.sh
    bash nodesource_setup.sh
    apt-get install --yes nodejs
    npm install -g dat
    

%runscript
    echo "Going to share the /share/ directory"
    echo "Bind a local directory to it when you run it: singularity -B ../bigdata/:/share run dat_share.img"
    echo "Arguments received (and ignored for now): $*"
    exec dat share "/share/"
