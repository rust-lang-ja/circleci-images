<!-- -*- coding:utf-8-unix -*- -->

# Circle CI Images

[rust-lang-ja][rust-lang-ja]がCircle CIで使用するカスタムDockerイメージ
[![Docker Repository on Quay](https://quay.io/repository/rust-lang-ja/circleci/status "Docker Repository on Quay")][quay]


## Dockerイメージタグ

| イメージ:タグ | 用途 | Gitブランチ |
| :---------- | :--- | :----------- |
| quay.io/rust-lang-ja/circleci:trpl2             | [rust-lang-ja/book][trpl2-repo]のCircle CIビルド                             | [trpl2][trpl2-docker] |
| quay.io/rust-lang-ja/circleci:trpl1             | [rust-lang-ja/the-rust-programming-language-ja][trpl1-repo]のCircle CIビルド | [trpl1][trpl1-docker] |
| quay.io/rust-lang-ja/circleci:rust-by-example   | [rust-lang-ja/rust-by-example-ja][rbe-repo]のCircle CIビルド                 | [rust-by-example][rbe-docker] |
| quay.io/rust-lang-ja/circleci:edition-guide     | [rust-lang-ja/edition-guide][eg-repo]のCircle CIビルド                       | [edition-guide][eg-docker] |
| quay.io/rust-lang-ja/circleci:atcoder-resources | [rust-lang-ja/atcoder-rust-resources][arr-repo]のCircle CIビルド             | [atcoder-resources][arr-docker] |


それぞれの`Dockerfile`はタグと同名のブランチにあります。

[rust-lang-ja]: https://github.com/rust-lang-ja
[quay]:         https://quay.io/repository/rust-lang-ja/circleci

[trpl2-repo]:   https://github.com/rust-lang-ja/book
[trpl1-repo]:   https://github.com/rust-lang-ja/the-rust-programming-language-ja
[rbe-repo]:     https://github.com/rust-lang-ja/rust-by-example-ja
[eg-repo]:      https://github.com/rust-lang-ja/edition-guide
[arr-repo]:     https://github.com/rust-lang-ja/atcoder-rust-resources

[trpl2-docker]: https://github.com/rust-lang-ja/circleci-images/tree/trpl2
[trpl1-docker]: https://github.com/rust-lang-ja/circleci-images/tree/trpl1
[rbe-docker]:   https://github.com/rust-lang-ja/circleci-images/tree/rust-by-example
[eg-docker]:    https://github.com/rust-lang-ja/circleci-images/tree/edition-guide
[arr-docker]:   https://github.com/rust-lang-ja/circleci-images/tree/atcoder-resources
