FROM rust:1-slim
ARG MDBOOK_VERSION="0.3.7"
ARG MDBOOK_TRANSCHECK_VERSION="0.2.4"

# Following lines were copied from:
# https://github.com/hrektts/docker-mdbook/blob/master/Dockerfile

# -- begin --
RUN cargo install mdbook --vers ${MDBOOK_VERSION}
WORKDIR /data
VOLUME ["/data"]
# -- end --

RUN cargo install mdbook-transcheck --vers ${MDBOOK_TRANSCHECK_VERSION}

# Install CircleCI Requirements
# https://circleci.com/docs/2.0/custom-images/#required-tools-for-primary-containers
RUN set -eux; \
    apt-get update -qq && \
    DEBIAN_FRONTEND=noninteractive apt-get install -yy git openssh-server tar gzip ca-certificates; \
    rm -rf /var/lib/apt/lists/*;

CMD [ "/bin/bash" ]
