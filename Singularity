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
#        ln -s /usr/lib/x86_64-linux-gnu /usr/lib64



%environment
	export IMAGE_NAME="CERES SOLVER AND COLMAP"
#	ln -s /usr/lib/x86_64-linux-gnu /usr/lib64
