Bootstrap: docker
From: ubuntu:18.10

%labels
Author "Randall Cab White - rcwhite@stanford.edu"

#########
#%setup
#########

##Just grabbing default packages from ubuntu repository
%post
	apt-get -ym update
	apt-get -ym install libceres1 libceres-dev ceres-solver-doc libcolmap-dev colmap qt5-default qtbase5-dev
	apt-get -ym install mesa-utils mesa-opencl-icd mesa-common-dev x11-utils x11-common libqt5x11extras5-dev libx11-dev libx11-xcb-dev
	apt-get -ym install wget curl cmake make autotools-dev
    mkdir -p /usr/local/lib64/ /usr/lib64/
    cp -r /usr/lib/x86_64-linux-gnu/* /usr/lib64/
    cp -r /usr/lib/x86_64-linux-gnu/* /usr/local/lib64/
	cp -r /usr/lib/* /usr/local/lib/
	ldconfig -l /usr/lib64/*
	wget https://github.com/colmap/colmap/archive/3.5.tar.gz
	tar zxvf 3.5.tar.gz
	
%environment
	export IMAGE_NAME="CERES SOLVER AND COLMAP"
