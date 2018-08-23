FROM buildpack-deps:stretch

# Install CircleCI requirements
RUN set -eux; \
    apt-get update -qq && \
    DEBIAN_FRONTEND=noninteractive apt-get install -yy git openssh-server tar gzip ca-certificates; \
    rm -rf /var/lib/apt/lists/*;

CMD [ "/bin/bash" ]
