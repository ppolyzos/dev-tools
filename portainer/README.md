# Portainer.io

[Portainer.io](https://www.portainer.io/) is a very handy tool that simplifies docker management through a web ui.

# Quick Links

* Official page: [portainer.io](https://www.portainer.io/)
* Documentation: [portainer.io/documentation/](https://www.portainer.io/documentation/)
* Local Dashboard: [localhost:9000](http://localhost:9000/)

# Requirements

By default, the stack exposes the following ports:
* 8000: Is used exclusively by the EDGE agent for the reverse tunnel function. If you do not plan to use the edge agent, you do not need to expose port 8000.
* 9000: Port 9000 is the general port used by Portainer for the UI access.

# Usage

Start services locally using Docker Compose:

```
$ docker-compose up
```

You can also run all services in the background (detached mode) by adding the `-d` flag to the above command.

> You must rebuild the stack images with docker-compose build whenever you switch branch or update the version of an already existing stack

* Dashboard available at [http://localhost:9000](http://localhost:9000)

> The first time you access the [dashboard](http://localhost:9000) you have to create a user, which remains available next time you start the tool, unless you perform a full cleanup.


# Cleanup 

Portainer data is peristed inside a volume by default.

To shutdown the stack **without** removing all persisted data, use the following Docker Compose command:
```
$ docker-compose down
```

In order to entirely shutdown the stack and remove all persisted data, you can add the `-v` flag to the above command:

```
$ docker-compose down -v
```
