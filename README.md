## Reference
https://docs.docker.com/compose/rails/

https://qiita.com/hogehoge1234/items/28be70b674e24427491e

## Description
This is the project for Docker workshop

## Usage

```
$ docker-compose run web rails new . --force --database=postgresql
```

Gemfile
```
gem 'pg', '~> 0.20.0'
```

```
$ dcoker-compose build
```

config/database.yml
```
default: &default
  adapter: postgresql
  encoding: unicode
  host: db
  username: postgres
  password:
```

```
$ docker-compose up -d
$ docker-compose run web rake db:create
```
