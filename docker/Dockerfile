FROM buildpack-deps:stretch

ENV RUSTUP_HOME=/usr/local/rustup \
    CARGO_HOME=/usr/local/cargo \
    RUST_VERSION=1.11.0 \
    RUST_ARCH=x86_64-unknown-linux-gnu \
    RUSTUP_VERSION=1.13.0 \
    RUSTBOOK_GIT_URL=https://github.com/rust-lang-ja/rustbook.git \
    RUSTBOOK_GIT_BRANCH=master \
    PATH=/usr/local/cargo/bin:$PATH \
    NODE_VERSION=v4.2.6 \
    NVM_DIR=/root/.nvm

# Install Requirements
RUN set -eux; \
    apt-get update -qq && \
    # Circle CI requirements \
    DEBIAN_FRONTEND=noninteractive apt-get install -yy git openssh-server tar gzip ca-certificates; \
    # GitBook requirements \
    unset NVM_DIR; \
    curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash; \
    bash -c 'export NVM_DIR=/root/.nvm; source $NVM_DIR/nvm.sh; nvm install $NODE_VERSION' \
    DEBIAN_FRONTEND=noninteractive apt-get install -yy subversion; \
    rm -rf /var/lib/apt/lists/*;

RUN set -eux; \
    rustupSha256='f69dafcca62fe70d7882113e21bb96a2cbdf4fc4636d25337d6de9191bdec8da'; \
    url="https://static.rust-lang.org/rustup/archive/${RUSTUP_VERSION}/${RUST_ARCH}/rustup-init"; \
    wget "$url"; \
    echo "${rustupSha256} *rustup-init" | sha256sum -c -; \
    chmod +x rustup-init; \
    ./rustup-init -y --no-modify-path --default-toolchain $RUST_VERSION; \
    rm rustup-init; \
    chmod -R a+w $RUSTUP_HOME $CARGO_HOME; \
    rustup --version; \
    rustc --version; \
    cargo --version;

# If you are builing this image in China mainland, uncomment this.
# COPY ./cargo-config-cn /root/.cargo/config

CMD [ "/bin/bash" ]
