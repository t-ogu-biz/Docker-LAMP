# Docker-LAMP
## 利用前提
Dockerをインストール済みで利用可能な状態になっていること ([Windowsの場合](https://qiita.com/dai-andy1976/items/24228211f2bb1a4cd09e))

## デプロイ手順
- プロジェクトフォルダの作成
```
# 任意の場所に作成
mkdir プロジェクト名
```
- 作成したプロジェクトフォルダ直下に当該リポジトリをクローンしコンテナを起動
```
# コンテナの作成・起動
docker-compose up -d

# コンテナの状態を確認しUPになっていれば起動完了
docker ps -a
  
CONTAINER ID   IMAGE                   COMMAND                  CREATED        STATUS                    PORTS                               NAMES
83b9cbbb1d94   mysql:5.7               "docker-entrypoint.s…"   3 hours ago    Up 10 seconds             0.0.0.0:3306->3306/tcp, 33060/tcp   mysql
a0a31312cac4   php73                   "docker-php-entrypoi…"   3 hours ago    Up 9 seconds              0.0.0.0:8080->80/tcp                apache-php
291f3f4d06f3   phpmyadmin/phpmyadmin   "/docker-entrypoint.…"   3 hours ago    Up 10 seconds             0.0.0.0:4040->80/tcp                phpmyadmin
```
- コンテナの操作
```
# 停止
docker-compose stop

# 再起動
docker-compose start

# 削除
docker-compose rm
```
