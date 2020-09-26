# docker-mod-nginx-auto

Docker mod to set worker processes to auto for [LSIO](https://www.linuxserver.io/) containers.

By default, any LSIO nginx installation ships using [4 worker processes](https://github.com/linuxserver/docker-baseimage-alpine-nginx/blob/master/root/defaults/nginx.conf#L4), which is inefficient for high-core machines. I've [opened](https://github.com/linuxserver/docker-baseimage-alpine-nginx/pull/53) PRs [before](https://github.com/linuxserver/docker-baseimage-alpine-nginx/pull/56), but they were all rejected for "backwards compatibility".

This docker mod modifies the nginx config prior to startup, setting it to `auto`, which makes it match the number of available CPU cores. This matches how nginx is configured by default in Docker, so is stable.

## Usage

On any of your LSIO containers, set the following environment variable:

```
DOCKER_MODS=theorangeone/docker-mod-nginx-auto:latest
```

[More about docker mods](https://github.com/linuxserver/docker-mods#using-a-docker-mod)
