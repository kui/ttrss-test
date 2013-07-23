ttrss-test
================

[Tiny Tiny RSS][ttrss] を試しに使うための Vagrant。

[ttrss]: http://tt-rss.org

インストール
---------------

このリポジトリをクローンして:

```sh
# インストールしていないなら2つのプラグインをインストール
vagrant plugin install vagrant-omnibus
vagrant plugin install vagrant-berkshelf

gem install bundler
bundle
vagrant up
```

http://localhost:8080/install/ へアクセス。

* データベース名、ユーザ名、パスワードすべて `tt-rss` と入力して `config.php` の作成が終われば完了


使い方
-------

http://localhost:8080/ にアクセスして、ユーザ名: `admin`, パスワード: `password` でログインできる。


注意
-------

ホスト OS のポート番号 `8080` が開いていることを確認してください。
