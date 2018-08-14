<!-- -*- coding:utf-8-unix -*- -->

# Circle CI Images &mdash; rust-by-example

[rust-lang-ja](https://github.com/rust-lang-ja)がCircle CIで使用するカスタムDockerイメージ
[![Docker Repository on Quay](https://quay.io/repository/rust-lang-ja/circleci/status "Docker Repository on Quay")](https://quay.io/repository/rust-lang-ja/circleci)

このページでは[rust-lang-ja/rust-by-example-ja](https://github.com/rust-lang-ja/rust-by-example-ja)のCircle CIビルドで使用する`quay.io/rust-lang-ja/circleci:rust-by-example`イメージについて説明します。
他のイメージについて知りたい時は[`master`ブランチの`README.md`](https://github.com/rust-lang-ja/circleci-images/blob/master/README.md)を参照してください。


## Dockerイメージの内容について覚え書き

- `rust-by-example-ja`リポジトリ内のRustプロジェクトをビルド・実行するには特定のバージョンの`rustc` nightlyが必要。
  * バージョンは`Dockerfile`中の`RUST_VERSION`環境変数で指定している。
- `gitbook`コマンドを実行するには特定バージョンのnode.jsが必要。
  * node.jsは`nvm`によってインストールし、バージョンは`Dockerfile`中の`NODE_VERSION`環境変数で指定している。
- Circle CIから`make book`を実行する際は以下のようにして`nvm`をアクティブにする。
  * `- run: bash -c 'source $NVM_DIR/nvm.sh; make book'`
