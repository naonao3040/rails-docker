# README

# 環境構築手順

## 前提準備

- [Docker Desktop](https://docs.docker.jp/get-docker.html)をインストールし、ログインして起動まで完了させ、dockerのコマンドが使用できるようにしてください。
- 下記のコマンドでversionが問題なく表示されていればOKです。（versionは異なっていてOKです）
``` 
% docker --version
Docker version 20.10.22, build 3a2c30b

% docker compose version
Docker Compose version v2.15.1
```

## Dockerを使用した環境構築手順

- ターミナルで`git clone https://github.com/naonao3040/rails-docker.git`コマンドを実行。
- 上記作業完了後に作業ディレクトリ`rails-docker`へ移動し、配下にファイルが存在するか確認する。
  - `Dockerfile`、`docker-compose.yml`が見当たれば、問題なくcloneできています。
```
  % cd rails-docker
  % ls
```
- 次に環境変数用のファイルを作成する
```
% touch .env

.envの内容に下記を追加

DB_PASSWORD=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
```

- 次に`docker compose up`コマンドでコンテナを起動をします。
  - 上記コマンドでRailsでDBの作成、migrateの実行、サーバー立ち上げ、DBの起動まで一つのコマンドで環境を作成しています。 
- ブラウザのURLに`http://localhost:3000 `を入力し、アクセス出来ているか確認する。

## Dockerでの環境構築中にエラーになった場合
- `docker compose down`で起動中のコンテナを停止、削除します。
- その後、`docker compose up --build`でコンテナを再起動してください。
- それでも改善しない場合、他のエンジニアへ質問してエラー対応してください。