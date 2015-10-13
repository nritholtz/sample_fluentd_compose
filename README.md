Test repo for running issues running Fluentd container within Docker Compose
----------------------------------------
My current specs:
```terminal
$ docker -v
Docker version 1.8.3, build f4bf5c7

$ docker-compose -v
docker-compose version: 1.5.0dev
```

Just run:
```terminal
docker-compose up
```

I saw the following output:
```terminal
sample_fluentd_compose nritholtz$ docker-compose up
Creating samplefluentdcompose_log_1
Creating samplefluentdcompose_web_1
Cannot start container ca26fe06dd7e4d63b401b12203f5670a8b95fa0c50793fb4ab5e1ec052c4cd30: Failed to initialize logging driver: dial tcp 198.105.244.74:24224: i/o timeout
```

A little bit of cleanup:
```terminal
docker-compose stop; docker-compose rm -fv
```

However, when using host ports:

```terminal
docker-compose -f host-ports.yml up
```

It works just fine.