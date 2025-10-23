FROM ubuntu:22.04

LABEL base_image="ubuntu:22.04"
LABEL version="1"
LABEL software="cellpose"
LABEL software.version="4.0.7"
LABEL about.summary="A generalist algorithm for cell and nucleus segmentation."
LABEL about.home="https://github.com/MouseLand/cellpose"
LABEL about.license="BSD-3-Clause"
LABEL about.license_file="https://github.com/MouseLand/cellpose/blob/main/LICENSE"
LABEL about.documentation="https://cellpose.readthedocs.io/en/latest/"
LABEL extra.identifiers.biotools=cellpose

MAINTAINER Yi Sun <sunyi000@gmail.com>
MAINTAINER Florian Wuennemann <flowuenne@gmail.com>

ARG DEBIAN_FRONTEND="noninteractive"
ARG CELLPOSE_VERSION="4.0.7"

ENV LANG en_US.UTF-8 \
    LC_ALL en_US.UTF-8 \
    LANGUAGE en_US:en

ENV MPLCONFIGDIR=/tmp/mpl_cache
ENV NUMBA_CACHE_DIR=/tmp/numba_cache
ENV CELLPOSE_LOCAL_MODELS_PATH=/tmp/cellpose_models
ENV QT_PLUGIN_PATH=/usr/local/lib/python3.10/dist-packages/PyQt6/Qt6/plugins/platforms/

RUN apt-get update -qq && \
    apt-get install -y -q --no-install-recommends \
            gcc \
            python3-dev \
            python3-pip \
            python3-wheel \
            libblas-dev \
            liblapack-dev \
            libatlas-base-dev \
            libgl1 \
            mesa-utils \
            libxcb-cursor0 \
            libxext6 \
            libxrender1 \
            libxcb1 \
            libgl1-mesa-glx \
            libxcb-xinerama0 \
            gfortran \
            apt-utils \
            bzip2 \
            ca-certificates \
            curl \
            locales \
            gnupg \
            libfontconfig1 \
            libxkbcommon0 \
            libxkbcommon-x11-0 \
            libxcb-icccm4 \
            libxcb-keysyms1 \
            libxcb-shape0 \
            software-properties-common \
            unzip && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* 

RUN sed -i '/en_US.UTF-8/s/^# //g' /etc/locale.gen && \
    locale-gen

RUN pip install --no-cache-dir -U pip \
    numpy \
    numba>=0.43.1 \
    wheel \
    scipy \
    pyqt6 \
    pyqt6-qt6 \
    torch>=1.6 \
    opencv-python-headless \
    pyqtgraph>=0.11.0rc0 \
    natsort \
    scikit-image matplotlib \
    scikit-learn \
    tqdm \
    tifffile \
    fastremap \
    'cellpose[gui]'==$CELLPOSE_VERSION
