# Lenses Box

[Lenses Box](https://lenses.io/boxs) is an all-in-one instance of Lenses, a Kafka Broker, Schema Registry, Kafka Connect and sample data streams

# Quick Links

* Official page: [Lenses.io](https://lenses.io/) | [Lenses Box](https://lenses.io/box/)
* Documentation: [Lenses/documentation/](https://docs.lenses.io/)
* Local Dashboard: [localhost:3030](http://localhost:3030/) (available after 30-45 seconds)

# Requirements

By default, the stack exposes the following ports:
* 9092: Kafka port. Default: 9092
* 3030: Dashboard port. Default: 3030
* Default credentials are `admin` / `admin`.

> Some MacOS users may need to set ADV_HOST to 192.168.99.100 and visit http://192.168.99.100:3030 instead.

## License Required

You need to register for a license in order to use [Lenses Box](https://lenses.io/box/) and you can do it by clicking the following link to [Register for a Key](https://lenses.io/downloads/lenses/).

> The key value should be **updated before** running the stack. 
> To do so please go to `lenses.env` file and update the `EULA` variable with the license key you have received when you registered for a license.

# Usage

Start services locally using Docker Compose:

```
$ docker-compose up
```

You can also run all services in the background (detached mode) by adding the `-d` flag to the above command.

> You must rebuild the stack images with docker-compose build whenever you switch branch or update the version of an already existing stack

* Dashboard available at [http://localhost:3030](http://localhost:3030)
* Default credentials (`admin` / `admin`)


# Cleanup 

Data is peristed inside a volume by default.

To shutdown the stack **without** removing all persisted data, use the following Docker Compose command:
```
$ docker-compose down
```

In order to entirely shutdown the stack and remove all persisted data, you can add the `-v` flag to the above command:

```
$ docker-compose down -v
```

