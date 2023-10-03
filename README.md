# Docker で開発用 Phoenix を立てる雛形

```
$ docker compuse up -d
$ docker compuse run app bash
```

ここで Phoenix を作る。

```
# mix phx.new . --app my_app
```

config/dev.exs の変更。

```
config :hello, Hello.Repo,
  username: "postgres",
  password: "postgres",
  hostname: "db",         #<==== docker の service

...

config :hello, HelloWeb.Endpoint,
	http: [ip: {0, 0, 0, 0}, port: 4000],
```

```
# mix ecto.create
```

docker-compose.yml で mix phx.server を設置。

```
$ docker compose up
```

