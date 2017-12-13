## 準備

    $ docker pull ruby:2.3.3
    $ docker pull postgres:9.6.6

## rails new
    $ docker-compose run web rails new . --force --database=postgresql

## Gemfileの更新
    $ vi Gemfile
    #コメント解除
    gem 'therubyracer', platforms: :ruby

    $ docker-compose build

## config/database.yml
    default: &default
      adapter: postgresql
      encoding: utf8
      host: db
      username: postgres
      password:
      pool: 5

## run
    $ docker-compose up
    $ docker-compose run web rake db:create

