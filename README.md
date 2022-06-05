# grafana & loki

[Grafana](https://grafana.com/) service with [loki](https://grafana.com/oss/loki/) and [promtail](https://grafana.com/docs/loki/latest/clients/promtail/) log aggregation.

## Loki docker driver

To upload logs from docker containers to loki, install [docker loki plugin](https://grafana.com/docs/loki/latest/clients/docker-driver/). 

```yaml
services:
  some-service:
    image: some-image
    logging:
      driver: loki
      options:
        loki-url: http://localhost:3100/loki/api/v1/push
        loki-external-labels: service=some-service,env=dev
```

## resources

* [Grafana loki docker](https://grafana.com/docs/loki/latest/installation/docker/)
* [Outdated blogpost about loki](https://blog.ruanbekker.com/blog/2020/08/13/getting-started-on-logging-with-loki-using-docker/)