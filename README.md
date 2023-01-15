TIG experiment
===============

First time setup
----------------
```shell
source .env && \
docker exec influxdb influx setup \
      --username $INFLUXDB_USERNAME \
      --password $INFLUXDB_PASSWORD \
      --org $INFLUXDB_ORG \
      --bucket $INFLUXDB_BUCKET
```

Then run the services with `docker compose up`

When you get the error about `/var/run/docker.sock` file, run:

```shell
docker exec -u root -it tig_telegraf /bin/sh -c \ 
"chmod 666 /var/run/docker.sock"
```