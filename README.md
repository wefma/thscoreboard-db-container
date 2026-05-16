# thscoreboard-db-container

## これ is 何

[サイレントセレナ](https://github.com/n-rook/thscoreboard)の開発環境初期セットアップの [Database Configuration](https://github.com/n-rook/thscoreboard#database-configuration) の `1.` ～ `4.` をdockerコンテナで自動で行うためのもの。
Dockerを使うので手元環境を汚さずにサイレントセレナの開発を行うことができる。


## 使い方

### thscoreboard-db-container を使用したサイレントセレナの開発環境の初期セットアップ

#### 公式の手順

1. [Setting up a development environment](https://github.com/n-rook/thscoreboard#setting-up-a-development-environment) の [Generating the replay parsers](https://github.com/n-rook/thscoreboard#generating-the-replay-parsers) まで行う。
1. [Dockerをインストール](https://docs.docker.com/engine/install/) する。
1. `.env` ファイルを `docker-compose.yml` と同じ階層に作成する。`LOCAL_DATABASE_PASSWORD` にthscoreboardユーザのパスワードを記載し、 `POSTGRES_USER` と `POSTGRES_PASSWORD` にはスーパーユーザのユーザ名とパスワードを書いておく。 `.env_template` に従って書くとよい。
1. `sudo docker compose up -d`
1. [Database configuration](https://github.com/n-rook/thscoreboard#database-configuration) の `5.` から先を行っていく。

### DBを削除する

1. `sudo docker compose down`
1. `sudo docker volume rm thscoreboard-postgres`


## その他このレポジトリに関係ないけど覚えておくべき追加事項

- `python manage.py createsuperuser` で管理者を作成することができる
