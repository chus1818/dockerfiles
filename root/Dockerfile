FROM ubuntu:14.04
MAINTAINER Jesus Prieto <chus1818@gmail.com>

RUN apt-get update
RUN apt-get -y install sudo curl wget git vim

# Users in the sudo group won't be asked for root password
RUN echo '%sudo ALL=NOPASSWD: ALL' >> /etc/sudoers

RUN useradd developer --create-home --home-dir /home/developer --shell /bin/bash -G sudo

USER developer
WORKDIR /home/developer