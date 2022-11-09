# Git-Docker-Hands

Docker演習の時間になったら。。

以下のコマンドでRailsのDockerコンテナの中でRailsアプリケーションを作成

```
docker-compose run --no-deps backend rails new . --force -d mysql --api --skip-test
```

Railsアプリケーションが作成できたら、docker-composeでDBに接続するために、database.ymlのdefultの箇所にhost: dbを追加します。
ここを追加しないと、Railsがdocker-composeで立ち上がっているMySQLへ接続することができません。

◆backend/config/database.yml
```
default: &default
  adapter: mysql2
  encoding: utf8mb4
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  username: root
  password:
  socket: /tmp/mysql.sock
  host: db #ここを追加
```

```
```
```
```
