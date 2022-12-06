# README

docker rails mysql の環境構築（redis sidekiq等はなし）
①mkdir myapp
　cd myapp

②touch {docker-compose.yml,Dockerfile,Gemfile,Gemfile.lock,entrypoint.sh}
作成したファイルにそれぞれ記述

③docker-compose run --rm web rails new . --force --database=mysql

④docker-compose build

⑤mysqlの設定変更（database.yml）
password: 何もなしから何かテキトーにパスワード書く
host: localhost -> db

⑥dbの作成
docker-compose run --rm web rails db:create

⑦コンテナの作成と起動
docker-compose up -d