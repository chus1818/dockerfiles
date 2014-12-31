FROM chus1818/root
MAINTAINER Jesus Prieto <prietoj@gmail.com>

# Workaround to install fuse which is a dependency of erlang in the container
USER root
WORKDIR /tmp
RUN apt-get install libfuse2
RUN apt-get download fuse
RUN dpkg-deb -x fuse_* .
RUN dpkg-deb -e fuse_*
RUN rm fuse_*.deb
RUN echo -en '#!/bin/bash\nexit 0\n' > DEBIAN/postinst
RUN dpkg-deb -b . /fuse.deb
RUN dpkg -i /fuse.deb

# Erlang dependencies
RUN apt-get -yq install build-essential libncurses5-dev openssl libssl-dev\
                             fop xsltproc unixodbc-dev

# Erlang compilation
RUN wget http://erlang.org/download/otp_src_17.4.tar.gz
RUN tar zxvf otp_src_17.4.tar.gz
WORKDIR /tmp/otp_src_17.4
RUN ./configure && make && make install

WORKDIR $DEVELOPER_HOME
USER developer