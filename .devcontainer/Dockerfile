FROM ubuntu:kinetic

# switch to root
USER root

# install a few tools for more convenient developing
RUN  apt-get update; \
    apt-get -y install --fix-missing \
    git python3 cmake g++ python-is-python3
