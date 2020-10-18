FROM rust:1.47.0

ENV MDBOOK_VERSION=0.1.8

# Install CircleCI requirements
RUN set -eux; \
    apt-get update -qq && \
    DEBIAN_FRONTEND=noninteractive apt-get install -yy git openssh-server tar gzip ca-certificates; \
    rm -rf /var/lib/apt/lists/*;

# Install mdBook and sd
RUN set -eux; \
    cargo install --force mdbook --vers "^$MDBOOK_VERSION"; \
    cargo install --force sd; \
    rustc --version; \
    mdbook --version; \
    sd --version; \
    rm -rf $CARGO_HOME/git $CARGO_HOME/registry;

CMD [ "/bin/bash" ]
