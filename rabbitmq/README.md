# RabbitMQ

[RabbitMQ](https://www.rabbitmq.com/) is one of the most widely deployed open source message broker.

# Quick Links

* Official page: [RabbitMQ](https://www.rabbitmq.com/)
* Documentation: [RabbitMQ/documentation/](https://www.rabbitmq.com/documentation.html)
* Bitnami image for more advanced scenarios [bitnami-docker-rabbitmq](https://github.com/bitnami/bitnami-docker-rabbitmq)
* Local Dashboard: [localhost:15672](http://localhost:15672/)

# Requirements

By default, the stack exposes the following ports:
* 5672: Node port. Default: 5672
* 15672: Management port. Default: 15672
* credentials: `admin` /  `admin`

# Usage

Start services locally using Docker Compose:

```
$ docker-compose up
```

You can also run all services in the background (detached mode) by adding the `-d` flag to the above command.

> You must rebuild the stack images with docker-compose build whenever you switch branch or update the version of an already existing stack

* Dashboard available at [http://localhost:15672](http://localhost:15672)
> To access dasbhoard you can use default credentials which are: `admin` / `admin`. 

> You can change them in [docker-compose](docker-compose.yml) file by updating `RABBITMQ_DEFAULT_USER` and `RABBITMQ_DEFAULT_PASS` properties. Credentials remain available also the next time you start the tool, unless you perform a full cleanup.


# Cleanup 

RabbitMQ data is peristed inside a volume by default.

To shutdown the stack **without** removing all persisted data, use the following Docker Compose command:
```
$ docker-compose down
```

In order to entirely shutdown the stack and remove all persisted data, you can add the `-v` flag to the above command:

```
$ docker-compose down -v
```
