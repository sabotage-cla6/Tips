# Docker 上にDesktop環境を持ったUbuntuを導入する

下記を参照にIPアドレス固定でDockerのプロセスを作成

[Dockerで固定IPアドレスを使う](https://qiita.com/paihu/items/17aa47906dd2bf935a25)

実行コマンドは下記
```
docker network create --subnet=192.168.56.0/24 user_defined_nw
docker network create --help

docker run -it --name test --net=user_defined_nw --ip=192.168.56.100 -d ubuntu:lastest /bin/bash
```
