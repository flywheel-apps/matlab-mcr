# Download and install Matlab Compiler Runtime v9.6 (2019a)
#
# This docker file will configure an environment into which the Matlab compiler
# runtime will be installed and in which stand-alone matlab routines (such as
# those created with Matlab's deploytool) can be executed.
#
# See http://www.mathworks.com/products/compiler/mcr/ for more info.

FROM ubuntu:xenial

# Install the MCR dependencies and some things we'll need and download the MCR
# from Mathworks -silently install it
RUN apt-get -qq update && apt-get -qq install -y \
        unzip \
        xorg \
        wget \
        curl && \
        mkdir /mcr-install && \
        mkdir /opt/mcr && \
        cd /mcr-install && \
        wget http://ssd.mathworks.com/supportfiles/downloads/R2019a/Release/2/deployment_files/installer/complete/glnxa64/MATLAB_Runtime_R2019a_Update_2_glnxa64.zip && \
        cd /mcr-install && \
        unzip -q MATLAB_Runtime_R2019a_Update_2_glnxa64.zip && \
        ./install -destinationFolder /opt/mcr -agreeToLicense yes -mode silent && \
        cd / && \
        rm -rf mcr-install

# Configure environment variables for MCR
ENV LD_LIBRARY_PATH /opt/mcr/v96/runtime/glnxa64:/opt/mcr/v96/bin/glnxa64:/opt/mcr/v96/sys/os/glnxa64:/opt/mcr/v96/extern/bin/glnxa64
