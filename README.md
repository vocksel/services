# vocksel.com

All services for [vocksel.com](https://vocksel.com).

## Deploying

Login to the droplet and pull latest changes

```sh
ssh me@64.23.137.135
cd services
git pull origin main
sudo docker pull
```

If this is the first deployment, make sure to install `loki-docker-driver`:

```sh
sudo docker plugin install grafana/loki-docker-driver:latest --alias loki --grant-all-permissions
```

Sometimes you'll also need to re-enable the Loki plugin. If you see the error `Error response from daemon: error looking up logging plugin loki: plugin loki found but disabled`, run the following:

```sh
sudo docker plugin enable loki
```

Then deploy services:

```sh
sudo docker compose up -d
```
