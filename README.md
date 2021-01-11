<!-- -*- coding:utf-8-unix -*- -->

# Circle CI Images

[rust-lang-ja][rust-lang-ja]がCircle CIで使用するカスタムDockerイメージ
[![Docker Repository on Quay](https://quay.io/repository/rust-lang-ja/circleci/status "Docker Repository on Quay")][quay]


## Dockerイメージタグ

| イメージ:タグ | 用途 | Gitブランチ |
| :---------- | :--- | :----------- |
| quay.io/rust-lang-ja/circleci:mdbook        | 汎用的なイメージ。[rust-lang-ja/book-ja][book-ja-repo]などのCircle CIビルドに使用 | [mdbook][mdbook-docker] |
| quay.io/rust-lang-ja/circleci:trpl2         | [rust-lang-ja/book][trpl2-repo]のCircle CIビルド | [trpl2][trpl2-docker] |
| quay.io/rust-lang-ja/circleci:trpl1         | [rust-lang-ja/the-rust-programming-language-ja][trpl1-repo]のCircle CIビルド | [trpl1][trpl1-docker] |
| quay.io/rust-lang-ja/circleci:rbe           | [rust-lang-ja/rust-by-example-ja][rbe-repo]のCircle CIビルド | [rbe][rbe-docker] |
| quay.io/rust-lang-ja/circleci:edition-guide | [rust-lang-ja/edition-guide][eg-repo]のCircle CIビルド | [edition-guide][eg-docker] |

それぞれの`Dockerfile`はタグと同名のブランチにあります。


## 廃止済みのDockerイメージ

以下のイメージは現在は使用していません。

| イメージ:タグ | Gitブランチ |
| :---------- | :----------- |
| quay.io/rust-lang-ja/circleci:atcoder-resources | [atcoder-resources][arr-docker] |



[rust-lang-ja]:  https://github.com/rust-lang-ja
[quay]:          https://quay.io/repository/rust-lang-ja/circleci

[book-ja-repo]:  https://github.com/rust-lang-ja/book-ja
[trpl2-repo]:    https://github.com/rust-lang-ja/book
[trpl1-repo]:    https://github.com/rust-lang-ja/the-rust-programming-language-ja
[rbe-repo]:      https://github.com/rust-lang-ja/rust-by-example-ja
[eg-repo]:       https://github.com/rust-lang-ja/edition-guide

[mdbook-docker]: https://github.com/rust-lang-ja/circleci-images/tree/mdbook
[trpl2-docker]:  https://github.com/rust-lang-ja/circleci-images/tree/trpl2
[trpl1-docker]:  https://github.com/rust-lang-ja/circleci-images/tree/trpl1
[rbe-docker]:    https://github.com/rust-lang-ja/circleci-images/tree/rbe
[eg-docker]:     https://github.com/rust-lang-ja/circleci-images/tree/edition-guide
[arr-docker]:    https://github.com/rust-lang-ja/circleci-images/tree/atcoder-resources
