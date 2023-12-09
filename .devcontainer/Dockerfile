# docker build -t seastar-dev ../contrib/seastar -f Dockerfile
FROM docker.io/ubuntu:jammy
WORKDIR /code
RUN apt -y update
COPY ./install-dependencies.sh .
RUN ./install-dependencies.sh && rm install-dependencies.sh
RUN apt-get -y install ccache clang-format htop tig vim
CMD /bin/bash
