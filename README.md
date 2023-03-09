# Docker-LAMP
## 利用前提
- Dockerをインストール済みで利用可能な状態になっていること
  - [Windows](https://qiita.com/dai-andy1976/items/24228211f2bb1a4cd09e) (「Docker for Windowsのインストール」まで)
  - [Mac](https://www.docker.com/products/docker-desktop/)

## デプロイ手順
- プロジェクトフォルダの作成
```
# 任意の場所に作成
mkdir プロジェクト名
```

- 作成したプロジェクトフォルダ直下に当該プロジェクトを設置しコンテナを起動
```
# コンテナの作成・起動
docker-compose up -d

# コンテナの状態を確認しUPになっていれば起動完了
docker ps -a
  
IMAGE                   COMMAND                  CREATED        STATUS                    PORTS                               NAMES
mysql:5.7               "docker-entrypoint.s…"   3 hours ago    Up 10 seconds             0.0.0.0:3306->3306/tcp, 33060/tcp   mysql
php73                   "docker-php-entrypoi…"   3 hours ago    Up 9 seconds              0.0.0.0:8080->80/tcp                apache-php
phpmyadmin/phpmyadmin   "/docker-entrypoint.…"   3 hours ago    Up 10 seconds             0.0.0.0:4040->80/tcp                phpmyadmin
```

- 最後に http://localhost:8080/index.php へアクセスし"docker LAMP"と表示されれば無事終了


#  コンテナ操作
```
# 停止
docker-compose stop

# 再起動
docker-compose start

# 削除
docker-compose rm
```
