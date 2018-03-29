## Reference
https://docs.docker.com/compose/rails/

https://qiita.com/hogehoge1234/items/28be70b674e24427491e

## Description
This is the tutorial project for Docker workshop

## Usage

```
$ docker-compose run web rails new . --force --database=postgresql
```

Create the Rails project on working directory.

- --force option overwrites Rails project.
- --database option describes which db is used.

Gemfile
```
gem 'pg', '~> 0.20.0'
```

Default version of pg is too old to get error.

```
$ docker-compose build
```

You must build again every time when a gem is added to your project.

config/database.yml
```
default: &default
  adapter: postgresql
  encoding: unicode
  host: db
  username: postgres
  password:
```

Important configuration is "host".

host must designates the container running as database.

```
$ docker-compose up -d
$ docker-compose exec web <command you want to use>
```

You can see that Rails operate correctly on localhost:3000
