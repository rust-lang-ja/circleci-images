FROM rust:1.60.0-slim

ARG MDBOOK_VERSION="0.4.18"
ARG MDBOOK_TRANSCHECK_VERSION="0.2.8"

# Install mdBook
RUN cargo install mdbook --vers ${MDBOOK_VERSION}

# Install mdbook-transcheck
RUN cargo install mdbook-transcheck --vers ${MDBOOK_TRANSCHECK_VERSION}

# Install CircleCI Requirements
# https://circleci.com/docs/2.0/custom-images/#required-tools-for-primary-containers
RUN set -eux; \
    apt-get update -qq && \
    DEBIAN_FRONTEND=noninteractive apt-get install -yy git openssh-server tar gzip ca-certificates; \
    DEBIAN_FRONTEND=noninteractive apt-get install -yy xz-utils; \
    rm -rf /var/lib/apt/lists/*;

WORKDIR /data
VOLUME ["/data"]
CMD [ "/bin/bash" ]
