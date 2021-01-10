FROM buildpack-deps:stretch

ARG RUST_VERSION=nightly-2021-01-09
ARG RUST_ARCH=x86_64-unknown-linux-gnu
ARG RUSTUP_VERSION=1.23.1
# ARG MDBOOK_VERSION=0.4.5
ARG MDBOOK_GIT_REPO="https://github.com/rust-lang-ja/mdBook"
ARG MDBOOK_GIT_BRANCH="summary-with-html-comments"

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
    # cargo install mdbook --root ${CARGO_HOME} --vers "^${MDBOOK_VERSION}"; \
    cargo install mdbook --root ${CARGO_HOME} --git ${MDBOOK_GIT_REPO} --branch ${MDBOOK_GIT_BRANCH}; \
    mdbook --version; \
    rm -rf $CARGO_HOME/git;

WORKDIR /data
VOLUME ["/data"]
CMD [ "/bin/bash" ]
