## Create `.env`

```shell
cp example.local.env .env
```

## Create network

```shell
docker network create --driver=overlay traefik
```

## Create stack

```shell
export $(grep -v '^#' .env | xargs) && \
docker stack deploy -c local.yml web
```

## Endpoints

<http://traefik.localhost:8000>

<http://portainer.localhost:8000>
