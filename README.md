<!-- -*- coding:utf-8-unix -*- -->

# Circle CI Images

[rust-lang-ja](https://github.com/rust-lang-ja)がCircle CIで使用するカスタムDockerイメージ
[![Docker Repository on Quay](https://quay.io/repository/rust-lang-ja/circleci/status "Docker Repository on Quay")](https://quay.io/repository/rust-lang-ja/circleci)


## Dockerイメージタグ

| イメージ:タグ | 用途 | Gitブランチ |
| :---------- | :--- | :----------- |
| quay.io/rust-lang-ja/circleci:trpl1 | [rust-lang-ja/the-rust-programming-language-ja](https://github.com/rust-lang-ja/the-rust-programming-language-ja)のCircle CIビルド | [trpl1](https://github.com/rust-lang-ja/circleci-images/tree/trpl1) |
| quay.io/rust-lang-ja/circleci:rust-by-example | [rust-lang-ja/rust-by-example-ja](https://github.com/rust-lang-ja/rust-by-example-ja)のCircle CIビルド | [rust-by-example](https://github.com/rust-lang-ja/circleci-images/tree/rust-by-example) |
| quay.io/rust-lang-ja/circleci:edition-guide | [rust-lang-ja/edition-guide](https://github.com/rust-lang-ja/edition-guide)のCircle CIビルド | [edition-guide](https://github.com/rust-lang-ja/circleci-images/tree/edition-guide) |

それぞれの`Dockerfile`はタグと同名のブランチにあります。
