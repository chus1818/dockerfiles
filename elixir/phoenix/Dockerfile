FROM chus1818/elixir:1.0.2
MAINTAINER Jesus Prieto <chus1818@gmail.com>

RUN git clone https://github.com/phoenixframework/phoenix.git
WORKDIR $DEVELOPER_HOME/phoenix
RUN git checkout v0.7.2
RUN yes | mix do deps.get
RUN yes | mix do compile
WORKDIR $DEVELOPER_HOME
