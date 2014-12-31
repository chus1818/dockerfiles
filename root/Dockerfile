FROM ubuntu:14.04
MAINTAINER Jesus Prieto <chus1818@gmail.com>

# Installing utilities
RUN apt-get update
RUN apt-get -y install sudo curl wget git vim

# Setting locales
RUN locale-gen en_US.UTF-8  
ENV LANG en_US.UTF-8  
ENV LANGUAGE en_US:en  
ENV LC_ALL en_US.UTF-8 

# Users in the sudo group won't be asked for root password
RUN echo '%sudo ALL=NOPASSWD: ALL' >> /etc/sudoers

# Adding the developer user as sudoer
ENV DEVELOPER_HOME /home/developer
RUN useradd developer --create-home --home-dir $DEVELOPER_HOME --shell /bin/bash -G sudo

USER developer
WORKDIR $DEVELOPER_HOME