Bootstrap: docker
From: ubuntu:16.04

%labels
Author "Randall Cab White - rcwhite@stanford.edu"

#########
#%setup
#########

##Just grabbing default packages from ubuntu repository
%post
	apt-get -ym update
	apt-get -ym install \
    git \
    cmake \
    build-essential \
    libboost-program-options-dev \
    libboost-filesystem-dev \
    libboost-graph-dev \
    libboost-regex-dev \
    libboost-system-dev \
    libboost-test-dev \
    libeigen3-dev \
    libsuitesparse-dev \
    libfreeimage-dev \
    libgoogle-glog-dev \
    libgflags-dev \
    libglew-dev \
    qtbase5-dev \
    libqt5opengl5-dev \
    libcgal-dev
    apt-get -ym install libcgal-qt5-dev
    apt-get -ym install libatlas-base-dev libsuitesparse-dev
    
    git clone https://ceres-solver.googlesource.com/ceres-solver
    git clone https://github.com/colmap/colmap.git
    
    cd ceres-solver
	git checkout $(git describe --tags) # Checkout the latest release
	mkdir build
	cd build
	cmake .. -DBUILD_TESTING=OFF -DBUILD_EXAMPLES=OFF
	make
	make install
	
	cd ../..
	
	cd colmap
	git checkout dev
	mkdir build
	cd build
#	cmake -DCMAKE_EXE_LINKER_FLAGS="-static -ldl -lc" \
#    -DCMAKE_FIND_LIBRARY_SUFFIXES=".a" ..
	cmake ../
	make
	make install

%environment
	export IMAGE_NAME="CERES SOLVER AND COLMAP"
#	export LANGUAGE = ""
#    export LC_ALL = (unset)
#	export LANG = "en_US.UTF-8"



