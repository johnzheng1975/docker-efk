# docker-efk

## Purpose
A simple fluentd + elastic search + kibana example.

## How to run
Run below, to start all containers
```
docker-compose up
```

Run below, to view elastic search status:
```
curl localhost:9200
```

Run below, to trigger logs:
```
for i in {1..10}; do curl http://localhost:80/; done
```

Run localhost:5601, you can view logs

## Refer to:
https://docs.fluentd.org/v0.12/articles/docker-logging-efk-compose




