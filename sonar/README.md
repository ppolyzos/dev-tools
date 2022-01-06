# SonarQube

Run SonarQube tool to analyze a project and detect bugs, vulnerabilities, and code smells in your code. I.

# Info
* [SonarQube](https://www.sonarqube.org/) official website
* [SonarQube Documentation](https://docs.sonarqube.org/latest/)
* [bitnami/sonarqube](https://hub.docker.com/r/bitnami/sonarqube/) docker 
image

# Requirements

By default, the stack exposes the following ports:
* 9000: SonarQube community server

# Usage

Start services locally using Docker Compose:

```
$ docker-compose up
```

You can also run all services in the background (detached mode) by adding the -d flag to the above command.

> You must rebuild the stack images with docker-compose build whenever you switch branch or update the version of an already existing stack

* SonarQube host url: `localhost:9000`

# Cleanup 

SonarQube data is persisted inside a volume by default.

To shutdown the stack **without** removing all persisted data, use the following Docker Compose command:
```
$ docker-compose down
```

In order to entirely shutdown the stack and remove all persisted data, you can add the `-v` flag to the above command:

```
$ docker-compose down -v
```
