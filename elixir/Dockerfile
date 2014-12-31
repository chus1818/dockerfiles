FROM chus1818/erlang:17.4
MAINTAINER Jesus Prieto <chus1818@gmail.com>

USER root
WORKDIR /tmp
RUN wget https://github.com/elixir-lang/elixir/archive/v1.0.2.tar.gz
RUN tar -zxvf v1.0.2.tar.gz
WORKDIR elixir-1.0.2
RUN make
RUN make install

WORKDIR $DEVELOPER_HOME
USER developer