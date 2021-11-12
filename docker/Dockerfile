FROM buildpack-deps:stretch

ARG RUST_VERSION=1.56.1
ARG MDBOOK_VERSION=0.4.13
ENV RUSTUP_HOME=/usr/local/rustup
ENV CARGO_HOME=/usr/local/cargo
ENV PATH=/usr/local/cargo/bin:$PATH

# Install CircleCI requirements
# https://circleci.com/docs/2.0/custom-images/#required-tools-for-primary-containers
RUN set -eux; \
    apt-get update -qq && \
    DEBIAN_FRONTEND=noninteractive apt-get install -yy git openssh-server tar gzip ca-certificates; \
    DEBIAN_FRONTEND=noninteractive apt-get install -yy curl; \
    rm -rf /var/lib/apt/lists/*;

RUN set -eux; \
    curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y  --no-modify-path --default-toolchain ${RUST_VERSION}; \
    chmod -R a+w $RUSTUP_HOME $CARGO_HOME; \
    rustup --version; \
    rustc --version; \
    cargo --version;

RUN set -eux; \
    cargo install mdbook --root ${CARGO_HOME} --vers "^${MDBOOK_VERSION}"; \
    mdbook --version; \
    rm -rf $CARGO_HOME/git;

WORKDIR /data
VOLUME ["/data"]
CMD [ "/bin/bash" ]
