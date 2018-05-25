# mpugach/monerod

A [monerod](https://getmonero.org/resources/developer-guides/daemon-rpc.html) docker image.

## Tags

- `v0.12.0.0`, `latest` ([v0.12.0.0/Dockerfile](https://github.com/mpugach/docker_monerod/blob/master/v0.12.0.0/Dockerfile))

## Examples

`docker-compose` example:

```yml
version: '3'

services:
  monerod:
    image: mpugach/monerod
    volumes:
      - monero:/root/.bitmonero/testnet
    ports:
      - "18080:18080"
      - "28081:28081"
    command: "monerod --testnet --offline"

volumes:
  monero:
```

command-line example:

```sh
docker run --rm -it mpugach/monerod monerod --testnet --offline
```
