FROM elixir:1.15

WORKDIR /app/src

RUN apt-get update && apt-get install -y \
  inotify-tools \
  git \
  npm \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

RUN mix do \
  local.hex --force, \
  archive.install --force hex phx_new
