FROM openjdk:17.0.2-jdk

LABEL maintainer="Alex Sobiek <alex@alexsobiek.com>"

ENV RUST_VERSION=1.59.0 \
	PATH=$HOME/.cargo/bin:$PATH

RUN curl -O https://static.rust-lang.org/rustup/dist/x86_64-unknown-linux-gnu/rustup-init && \
	chmod +x rustup-init && \
	./rustup-init -y --no-modify-path --default-toolchain $RUST_VERSION && \
	rm rustup-init && \
    source $HOME/.cargo/env && \
	rustc --version && \
	cargo --version

RUN java --version