FROM chus1818/root
MAINTAINER Jesus Prieto <chus1818@gmail.com>

USER root
# Dependencies and tools for compiling
RUN apt-get -y install build-essential libffi-dev zlib1g-dev openssl libssl-dev

WORKDIR /tmp
# Compilation
RUN wget http://cache.ruby-lang.org/pub/ruby/2.2/ruby-2.2.0.tar.gz
RUN tar -zxvf ruby-2.2.0.tar.gz
WORKDIR ruby-2.2.0
RUN ./configure
RUN make
RUN make install

USER developer
WORKDIR $DEVELOPER_HOME

# Setting gem installation dir
RUN mkdir $DEVELOPER_HOME/.gem
ENV GEM_DEVELOPER_HOME $DEVELOPER_HOME/.gem
ENV GEM_PATH $DEVELOPER_HOME/.gem
ENV PATH $PATH:$DEVELOPER_HOME/.gem/bin

# Installing global gems
RUN gem install bundler