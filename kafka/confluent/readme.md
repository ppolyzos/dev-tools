# Kafka Confluent Platform

Use [Confluent Platform](https://docs.confluent.io/platform/current/overview.html) and a few SQL statements to build a real-time application that processes example data streams.

For more info you can click [here](https://docs.confluent.io/platform/current/platform-quickstart.html#quick-start-for-cp)

# Usage

Start services locally using Docker Compose:

```
$ docker-compose up
```

You can also run all services in the background (detached mode) by adding the `-d` flag to the above command.

# Access to Control Center

In order to access Confluent Control Center you can visit the following link:

* [localhost:9021](http://localhost:9021)


# Cleanup 

Kafka Confluent data is peristed inside a volume by default.

To shutdown the stack **without** removing all persisted data, use the following Docker Compose command:
```
$ docker-compose down
```

In order to entirely shutdown the stack and remove all persisted data, you can add the `-v` flag to the above command:

```
$ docker-compose down -v

```
