FROM cimg/openjdk:17.0.2

LABEL maintainer="Alex Sobiek <alex@alexsobiek.com>"

ENV RUST_VERSION=1.59.0

RUN curl -O https://static.rust-lang.org/rustup/dist/x86_64-unknown-linux-gnu/rustup-init && \
	chmod +x rustup-init && \
	./rustup-init -y --no-modify-path --default-toolchain $RUST_VERSION && \
	rm rustup-init

# Set PATH
ENV PATH /home/circleci/.cargo/bin:$PATH
# Some CI platforms override the PATH variable, this provides an alternate variable that build/test scripts can override
# the overridden PATH variable with.
ENV ALT_PATH $PATH

# Test
RUN rustc --version
RUN cargo --version
RUN java --version