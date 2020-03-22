# FROM hrektts/mdbook:0.3.5

# Following lines were copied from:
# https://github.com/hrektts/docker-mdbook/blob/master/Dockerfile

# -- begin --
FROM rust:1-slim
ARG MDBOOK_VERSION="0.3.6"
RUN cargo install mdbook --vers ${MDBOOK_VERSION}
WORKDIR /data
VOLUME ["/data"]
# -- end --

# Install CircleCI Requirements
# https://circleci.com/docs/2.0/custom-images/#required-tools-for-primary-containers
RUN set -eux; \
    apt-get update -qq && \
    DEBIAN_FRONTEND=noninteractive apt-get install -yy git openssh-server tar gzip ca-certificates; \
    rm -rf /var/lib/apt/lists/*;

CMD [ "/bin/bash" ]
