# lsio-mod-more-processes

Docker mod to increase the number of processes run for applications inside the container.

By default, any LSIO nginx installation ships using [4 worker processes](https://github.com/linuxserver/docker-baseimage-alpine-nginx/blob/master/root/defaults/nginx.conf#L4), which is inefficient for high-core machines. I've [opened](https://github.com/linuxserver/docker-baseimage-alpine-nginx/pull/53) PRs [before](https://github.com/linuxserver/docker-baseimage-alpine-nginx/pull/56), but they were all rejected for "backwards compatibility".

- Set Nginx' `worker_processes` to `auto`.
- Increase `pm` values for `php-fpm` to better deal with more requests.

## Usage

On any of your LSIO containers, set the following environment variable:

```
DOCKER_MODS=theorangeone/lsio-mod-more-processes:latest
```

[More about docker mods](https://github.com/linuxserver/docker-mods#using-a-docker-mod)
