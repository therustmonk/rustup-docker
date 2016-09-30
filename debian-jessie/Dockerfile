FROM jimmycuadra/rust:latest
MAINTAINER Denis Kolodin <DenisKolodin@gmail.com>

RUN mkdir /source/target
VOLUME ["/source/target"]

RUN mkdir /root/.cargo
VOLUME ["/root/.cargo"]

ENTRYPOINT ["cargo"]
