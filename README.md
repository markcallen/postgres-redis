# Postgres Redis

Example on how to setup a redis cache and postgres database using a helmfile and then use codezero to access these services
from a local machine

## Setup

Install helmfile

Install codezero

## Run

Install postgres, redis and adminer

```
helmfile apply
```

Wait till they are running

```
kubectl get pods -n cz1
```

Log into codezero, create an organization and teamspace.

Select your teamspace

```
czctl space Select
```

Use the compose file to consume the services

```
czctl compose start -f cz1-compoose.yaml
```

Verify they are accessible

```
curl http://adminer.cz1/
```

```
psql -h psql-postgresql.cz1 -U my_user mydb
<password is secret>
```

```
redis-cli -h redis-master.cz1
```

## License

Distributed under the MIT License. See `LICENSE` for more information.

## Contact

Mark C Allen - [@markcallen](https://www.linkedin.com/in/markcallen/)

Project Link: [https://github.com/markcallen/postgres-redis](https://github.com/markcallen/postgres-redis)
