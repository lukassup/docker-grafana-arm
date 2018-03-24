# docker-prometheus-arm

## BUILD

```bash
$ docker build -t prom/prometheus:2.2.1-arm32v7 -f ./Dockerfile.arm32v7 .
```

## RUN

On build machine

```bash
$ docker save -o prom-image.tar prom/prometheus:2.2.1-arm32v7
$ scp prom-image.tar root@target:~
```

On target machine

```bash
# docker load -i ~/prom-image.tar
# docker run -ti -v 9090:9090 prom/prometheus:2.2.1-arm32v7
```
