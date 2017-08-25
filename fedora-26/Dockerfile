FROM fedora:26
MAINTAINER Denis Kolodin <DenisKolodin@gmail.com>

ENV RUST_CHANNEL=nightly

RUN mkdir /source
VOLUME ["/source"]
WORKDIR /source

RUN mkdir /source/target
VOLUME ["/source/target"]

RUN mkdir /root/.cargo
VOLUME ["/root/.cargo"]

RUN dnf update -y
RUN dnf install -y git file findutils gcc gcc-c++ make openssl-devel readline-devel
RUN curl -sSf https://static.rust-lang.org/rustup.sh | sh -s -- --channel=$RUST_CHANNEL --disable-sudo

# Warning! Don't use rustup.rs, because it installs into .cargo and overlaps with attached local cache
# We use permanent external cache folder to keep container short-lived
# RUN curl -sSf https://sh.rustup.rs | sh -s -- -y --default-toolchain nightly

ENTRYPOINT ["cargo"]
