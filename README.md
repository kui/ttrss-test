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
echo 'my-tinyrss.com 127.0.0.1' | sudo tee -a /etc/hosts
```

http://my-tinyrss.com:8080/install/ へアクセス。

* データベース名、ユーザ名、パスワードすべて `tt-rss` と入力して `config.php` の作成が終われば完了

使い方
-------

http://my-tinyrss.com:8080/ にアクセスして、ユーザ名: `admin`, パスワード: `password` でログインできる。
