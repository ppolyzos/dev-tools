# Redis & Redis Commander

Run redis server and web management tool to manage and monitor your redis server.

Redis is an advanced key-value cache and store. It is often referred to as a data structure server since keys can contain strings, hashes, lists, sets, sorted sets, bitmaps and hyperloglogs.

# Info
* [Redis](https://redis.io/)
* [Bitmani Redis](https://github.com/bitnami/bitnami-docker-redis) docker image
* [Redis commander](https://www.npmjs.com/package/redis-commander) is a Redis web management written in node.js

# Requirements

By default, the stack exposes the following ports:
* 6379: Redis server
* 8081: Redis commander management ui

# Usage

Start services locally using Docker Compose:

```
$ docker-compose up
```

You can also run all services in the background (detached mode) by adding the -d flag to the above command.

> You must rebuild the stack images with docker-compose build whenever you switch branch or update the version of an already existing stack

# Cleanup 

Redis cache data is peristed inside a volume by default.

In order to entirely shutdown the stack and remove all persisted data, use the following Docker Compose command:

```
$ docker-compose down -v
```


