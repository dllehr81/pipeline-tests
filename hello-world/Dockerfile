FROM fedora:28
LABEL maintainer Chris Collins <collins.christopher@gmail.com>

RUN dnf install -y tar gzip gcc make \
        && dnf clean all

RUN curl http://mirror.team-cymru.com/gnu/hello/hello-2.10.tar.gz -o /tmp/hello-2.10.tar.gz

RUN tar xvzf /tmp/hello-2.10.tar.gz -C /opt

WORKDIR /opt/hello-2.10

RUN ./configure
RUN make
RUN make install
RUN hello -v
ENTRYPOINT "/usr/local/bin/hello"
