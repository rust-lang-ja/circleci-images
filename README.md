<!-- -*- coding:utf-8-unix -*- -->

# Circle CI Images &mdash; trpl1

[rust-lang-ja](https://github.com/rust-lang-ja)がCircle CIで使用するカスタムDockerイメージ
[![Docker Repository on Quay](https://quay.io/repository/rust-lang-ja/circleci/status "Docker Repository on Quay")](https://quay.io/repository/rust-lang-ja/circleci)

このページでは[rust-lang-ja/the-rust-programming-language-ja](https://github.com/rust-lang-ja/the-rust-programming-language-ja)のCircle CIビルドで使用する`quay.io/rust-lang-ja/circleci:trpl1`イメージについて説明します。
他のイメージについて知りたい時は[`master`ブランチの`README.md`](https://github.com/rust-lang-ja/circleci-images/blob/master/README.md)を参照してください。


## Dockerイメージの内容について覚え書き

- `rustbook`コマンドをビルド・実行するには特定のバージョンの`rustc` nightlyが必要。
  * バージョンは`Dockerfile`中の`RUST_VERSION`環境変数で指定している。
- `rustbook`コマンドを実行するには`rustc`のライブラリが必要。
  * `LD_LIBRARY_PATH`を指定する方法と、`rustup run nightly-YYYY-MM-DD rustbook ...`を使う方法の2通りある。
  * Circle CIビルドでは前者を採用。
