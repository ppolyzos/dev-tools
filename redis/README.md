# Redis & Redis Commander

Run redis server and web management tool to manage and monitor your redis server.

Redis is an advanced key-value cache and store. It is often referred to as a data structure server since keys can contain strings, hashes, lists, sets, sorted sets, bitmaps and hyperloglogs.

# Info
* [Redis](https://redis.io/)
* [Bitmani Redis](https://github.com/bitnami/bitnami-docker-redis) docker image
* [Redis commander](https://www.npmjs.com/package/redis-commander) is a Redis web management written in node.js
* [RedisInsights](https://redislabs.com/redis-enterprise/redis-insight/) is an alternative web management tool for your redis db

# Requirements

By default, the stack exposes the following ports:
* 6379: Redis server
* 8081: Redis commander management ui
* 8001: RedisInsights

# Usage

Start services locally using Docker Compose:

```
$ docker-compose up
```

You can also run all services in the background (detached mode) by adding the -d flag to the above command.

> You must rebuild the stack images with docker-compose build whenever you switch branch or update the version of an already existing stack

* Redis Connection string: `localhost:6379`
* Redis Commander Dashboard available at [http://localhost:8081](http://localhost:8081)
* Redis Insights Dashboard available at [http://localhost:8001](http://localhost:8001)

### Redis Insights setup
When you open Redis Insights Dashboard for the first time at [http://localhost:8001](http://localhost:8001) you are prompt to connect to your redis database.
To do so setup the following:
* host -> redis
* port -> 6379
* name -> redis
* username / password -> according to your setup


# Cleanup 

Redis cache data is peristed inside a volume by default.

To shutdown the stack **without** removing all persisted data, use the following Docker Compose command:
```
$ docker-compose down
```

In order to entirely shutdown the stack and remove all persisted data, you can add the `-v` flag to the above command:

```
$ docker-compose down -v
```