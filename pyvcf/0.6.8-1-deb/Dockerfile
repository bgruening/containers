FROM biocontainers/biocontainers:debian-stretch-backports
MAINTAINER biocontainers <biodocker@gmail.com>
LABEL    software="pyvcf" \ 
    container="pyvcf" \ 
    about.summary="helper scripts for Variant Call Format (VCF) parser" \ 
    about.home="https://pypi.python.org/pypi/PyVCF" \ 
    software.version="0.6.8-1-deb" \ 
    version="1" \ 
    about.copyright="2011-2015, Population Genetics Technologies Ltd, All rights reserved." \ 
    about.license="BSD-3-clause" \ 
    about.license_file="/usr/share/doc/pyvcf/copyright" \ 
    extra.binaries="/usr/bin/vcf_filter,/usr/bin/vcf_melt,/usr/bin/vcf_sample_filter" \ 
    about.tags=""

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install -y pyvcf && apt-get clean && apt-get purge && rm -rf /var/lib/apt/lists/* /tmp/*
USER biodocker
