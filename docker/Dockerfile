FROM rust:1.49.0-slim

ARG MDBOOK_GIT_REPO="https://github.com/rust-lang-ja/mdBook"

# mdbook-0.1 branch of the above repository has a cherry-picked commit to address CVE-2020-26297:
# https://github.com/rust-lang-ja/mdBook/commit/3bb522d8f10e890f9dd6f0250776584810a78cfe
ARG MDBOOK_GIT_BRANCH="mdbook-0.1"

# Install CircleCI requirements
RUN set -eux; \
    apt-get update -qq && \
    DEBIAN_FRONTEND=noninteractive apt-get install -yy git openssh-server tar gzip ca-certificates; \
    rm -rf /var/lib/apt/lists/*;

# Install mdBook and sd
RUN set -eux; \
    cargo install --force mdbook --git ${MDBOOK_GIT_REPO} --branch ${MDBOOK_GIT_BRANCH}; \
    cargo install --force sd; \
    rustc --version; \
    mdbook --version; \
    sd --version; \
    rm -rf $CARGO_HOME/git $CARGO_HOME/registry;

CMD [ "/bin/bash" ]
