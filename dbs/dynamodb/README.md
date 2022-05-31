# DynamoDB 

Amazon DynamoDB is a fully managed NoSQL database service that provides fast and predictable performance with seamless scalability. DynamoDB lets you offload the administrative burdens of operating and scaling a distributed database so that you don't have to worry about hardware provisioning, setup and configuration, replication, software patching, or cluster scaling. DynamoDB also offers encryption at rest, which eliminates the operational burden and complexity involved in protecting sensitive data. For more information, see DynamoDB Encryption at Rest.

For more info please visit AWS DynamoDB's [official documentation](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html)

# Requirements

By default, the stack exposes the following ports:
* [8000](http://localhost:8000): default port

# Usage

Start services locally using Docker Compose:

```
$ docker-compose up
```

You can also run all services in the background (detached mode) by adding the `-d` flag to the above command.


* Default Connection available at [http://localhost:8000](http://localhost:8000)

## Connect to Dynamo DB

Please read the documentation [here](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/AccessingDynamoDB.html)

# Local Web UI - dynamodb-admin

If you want to visualize and manipulate locally, in your development environment, you can use [dynamodb-admin](https://github.com/aaronshaf/dynamodb-admin)

You can install it globally in your machine and then when you have started your dynamodb instance you can connect to it, using the following command:
```
npm install -g dynamodb-admin

# For Windows:
set DYNAMO_ENDPOINT=http://localhost:8000
dynamodb-admin

# For Mac/Linux:
DYNAMO_ENDPOINT=http://localhost:8000 dynamodb-admin
```


# Cleanup 

Data is persisted inside a volume by default.

To shutdown the stack **without** removing all persisted data, use the following Docker Compose command:
```
$ docker-compose down
```

In order to entirely shutdown the stack and remove all persisted data, you can add the `-v` flag to the above command:

```
$ docker-compose down -v
```
