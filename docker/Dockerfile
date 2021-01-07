FROM rust:1.49.0-slim
# ARG MDBOOK_VERSION="0.4.5"
ARG MDBOOK_GIT_REPO="https://github.com/rust-lang-ja/mdBook"
ARG MDBOOK_GIT_BRANCH="summary-with-html-comments"

# Install mdBook
# RUN cargo install mdbook --vers ${MDBOOK_VERSION}
RUN cargo install mdbook --git ${MDBOOK_GIT_REPO} --branch ${MDBOOK_GIT_BRANCH}

# Install CircleCI Requirements
# https://circleci.com/docs/2.0/custom-images/#required-tools-for-primary-containers
RUN set -eux; \
    apt-get update -qq && \
    DEBIAN_FRONTEND=noninteractive apt-get install -yy git openssh-server tar gzip ca-certificates; \
    rm -rf /var/lib/apt/lists/*;

WORKDIR /data
VOLUME ["/data"]
CMD [ "/bin/bash" ]
