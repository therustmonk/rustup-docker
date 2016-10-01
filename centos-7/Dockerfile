FROM centos:7
MAINTAINER Denis Kolodin <DenisKolodin@gmail.com>

ENV RUST_CHANNEL=nightly

RUN mkdir /source
VOLUME ["/source"]
WORKDIR /source

RUN mkdir /source/target
VOLUME ["/source/target"]

RUN mkdir /root/.cargo
VOLUME ["/root/.cargo"]

RUN yum update -y
RUN yum install -y git file gcc gcc-c++ make openssl-devel
RUN curl -sSf https://static.rust-lang.org/rustup.sh | sh -s -- --channel=$RUST_CHANNEL --disable-sudo

ENTRYPOINT ["cargo"]
