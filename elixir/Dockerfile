FROM chus1818/root
MAINTAINER Jesus Prieto <chus1818@gmail.com>

RUN wget http://packages.erlang-solutions.com/erlang-solutions_1.0_all.deb && sudo dpkg -i erlang-solutions_1.0_all.deb
RUN rm erlang-solutions_1.0_all.deb
RUN sudo apt-get update
RUN sudo apt-get -y install elixir