BootStrap: docker
From: nvidia/cuda:8.0-devel-ubuntu16.04

%post
    apt-get -y update
    apt-get -y install git
    git clone https://github.com/torch/distro.git /torch --recursive
    cd /torch;
    sed 's/sudo/ /g' install-deps > install-deps_no_sudo 
    bash install-deps_no_sudo;
    ./install.sh
    /torch/install/bin/luarocks install torch
    /torch/install/bin/luarocks install nn
    /torch/install/bin/luarocks install image
    /torch/install/bin/luarocks install lua-cjson
    /torch/install/bin/luarocks install https://raw.githubusercontent.com/qassemoquab/stnbhwd/master/stnbhwd-scm-1.rockspec
    /torch/install/bin/luarocks install https://raw.githubusercontent.com/jcjohnson/torch-rnn/master/torch-rnn-scm-1.rockspec
    /torch/install/bin/luarocks install cutorch
    /torch/install/bin/luarocks install cunn
    git clone https://github.com/jcjohnson/densecap.git /densecap

%environment
    export LC_ALL=C
    
%runscript
    echo hello
