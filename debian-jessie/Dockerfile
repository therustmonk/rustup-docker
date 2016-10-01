FROM debian:jessie
MAINTAINER Denis Kolodin <DenisKolodin@gmail.com>

ENV RUST_CHANNEL=nightly

RUN mkdir /source
VOLUME ["/source"]
WORKDIR /source

RUN mkdir /source/target
VOLUME ["/source/target"]

RUN mkdir /root/.cargo
VOLUME ["/root/.cargo"]

RUN apt-get update
RUN apt-get install -y --no-install-recommends git file curl build-essential ca-certificates libssl-dev
RUN curl -sSf https://static.rust-lang.org/rustup.sh | sh -s -- --channel=$RUST_CHANNEL --disable-sudo

ENTRYPOINT ["cargo"]
