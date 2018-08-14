FROM buildpack-deps:stretch

ENV RUSTUP_HOME=/usr/local/rustup \
    CARGO_HOME=/usr/local/cargo \
    RUST_VERSION=nightly-2016-06-01 \
    RUST_ARCH=x86_64-unknown-linux-gnu \
    RUSTUP_VERSION=1.13.0 \
    RUSTBOOK_GIT_URL=https://github.com/rust-lang-ja/rustbook.git \
    RUSTBOOK_GIT_BRANCH=master \
    PATH=/usr/local/cargo/bin:$PATH

# Install CircleCI requirements
RUN set -eux; \
    apt-get update -qq && \
    DEBIAN_FRONTEND=noninteractive apt-get install -yy git openssh-server tar gzip ca-certificates; \
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

RUN set -eux; \
    cargo install --force --root $CARGO_HOME --git $RUSTBOOK_GIT_URL --branch $RUSTBOOK_GIT_BRANCH; \
    export LD_LIBRARY_PATH=$(rustc --print sysroot)/lib; \
    rustbook help; \
    rm -rf $CARGO_HOME/git;

CMD [ "/bin/bash" ]
