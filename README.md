<!-- -*- coding:utf-8-unix -*- -->

# Circle CI Images &mdash; edition-guide

[rust-lang-ja](https://github.com/rust-lang-ja)がCircle CIで使用するカスタムDockerイメージ
[![Docker Repository on Quay](https://quay.io/repository/rust-lang-ja/circleci/status "Docker Repository on Quay")](https://quay.io/repository/rust-lang-ja/circleci)

このページでは[rust-lang-ja/edition-guide](https://github.com/rust-lang-ja/edition-guide)のCircle CIビルドで使用する`quay.io/rust-lang-ja/circleci:edition-guide`イメージについて説明します。
他のイメージについて知りたい時は[`master`ブランチの`README.md`](https://github.com/rust-lang-ja/circleci-images/blob/master/README.md)を参照してください。


## Dockerイメージの内容について覚え書き

- 本来`mdbook`コマンドをビルド・実行するにはstable版の`rustc`で問題ないが、Edition Guide中のサンプルコードをコンパイルするためにnightly版の`rustc`が必要。
  * バージョンは`Dockerfile`中の`RUST_VERSION`環境変数で指定している。
