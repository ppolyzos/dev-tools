# Docker tools for your dev environment

![Dev tools](assets/dev-tools.png)

A collection of tools, links & recipes that runs in docker and can help you during development locally. Each folder contains info and/or a `docker-compose.yml` so you can easily spin up different stacks at will.

## Quick Links

* [Docker Desktop](https://www.docker.com/products/docker-deskto): Native application that provides an easy-to-use development environment for building, shipping, and running dockerized apps
* [Docker docs](https://docs.docker.com/): A lot of documentation around docker, images, containers, etc.


## Tools / Recipes

List of docker recipes to help you start:

* [Redis & Redis-Commander](/redis/README.md)
* [Portainer.io](/portainer/README.md)
* [RabbitMQ](/rabbitmq/README.md)
* [Lenses Box](/lenses/README.md)
* [ELK](/elk/README.md)

## Usage

### Start Services

Start services locally using Docker Compose either by `cd` to the appropriate folder and run `docker-compose up`:
```
$ cd <folder_tool>
$ docker-compose up
```
or by starting the tool from root folder:
```
$ docker-compose -f <folder_tool>/docker-compose.yml up
```

#### Example
```
# To start Redis
$ cd redis
$ docker-compoose up
```
or 
```
# Start redis by running
$ docker-compose -f redis/docker-compose.yml up 
```

> You can also start all services in the background (detached mode) by adding the `-d` flag to the above command.

### Cleanup

To shutdown the stack **without** removing all persisted data, use the following Docker Compose command:
```
$ cd <folder_tool>
$ docker-compose down
```
or cleanup from root folder:
```
$ docker-compose -f <folder_tool>/docker-compose.yml down
```

> In order to entirely shutdown the stack and remove all persisted data, you can add the `-v` flag to the above command:

```
$ docker-compose down -v
```


## References

* Featured image from [undraw.co](https://undraw.co/)
