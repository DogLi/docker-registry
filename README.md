# docker-registry

# set insecure registry

## method 1: edit /etc/init.d/docker
in directory: `/etc/systemd/system`, find `docker.service`,
find `ExecStart` field, we can see, docker use the `$DOCKER_SOPTS` env

so we can add the  `--incesure-registry` in `/etc/init.d/docker` file:
`DOCKER_OPTS=--insecure-registry <ip>:30001`

info: https://www.bbsmax.com/A/kvJ3oYeXJg/

## method 2: set insecure-registry

some one said edit `/etc/default/docker`, add `DOCKER_OPTS="$DOCKER_OPTS --insecure-registry 192.168.75.129:30001"`
and then restart docker, but this does't work for ubuntu 16.04

