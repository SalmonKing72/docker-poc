FROM debian:jessie

#If working from behind a proxy make sure the 
#Copy commands below are uncommented
#and the files exist as sibling files of this Dockerfile.

#COPY apt.conf /etc/apt/apt.conf
#COPY environment /etc/environment

RUN apt-get update \
    && apt-get upgrade -y \
	&& apt-get install -y unzip wget build-essential \
		cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev \
		python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libdc1394-22-dev

RUN wget https://github.com/opencv/opencv/archive/2.4.13.3.zip

RUN unzip 2.4.13.3.zip \
	&& cd opencv-2.4.13.3 \
	&& mkdir build \
	&& cd build \
	&& cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local .. \
	&& make \
	&& make install \
    && cd / \
    && rm 2.4.13.3.zip