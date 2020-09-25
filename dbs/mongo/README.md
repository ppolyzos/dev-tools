# MongoDB 

MongoDB is a cross-platform document-oriented database program. Classified as a NoSQL database program, MongoDB uses JSON-like documents with schema. MongoDB is developed by MongoDB Inc. and licensed under the Server Side Public License.

For more info please visit MongoDB [official page](https://www.mongodb.com/)

# Requirements

By default, the stack exposes the following ports:
* [27017](http://localhost:27017): default port
* Default credentials: `root` / `<YourStrongPassw0rd>`

# Usage

Start services locally using Docker Compose:

```
$ docker-compose up
```

You can also run all services in the background (detached mode) by adding the `-d` flag to the above command.


* Default Connection available at [http://localhost:27017](http://localhost:27017)
* Default credentials: `root` / `<YourStrongPassw0rd>`

## Connect to Mongo DB

### Via Shell:
```
# connect to docker container
$ docker exec -it mongo_dev bash

# connect to mongodb
$ mongo admin -u root -p "<YourStrongPassw0rd>"
```

Sample commands to play with:
```
# Show databases:
$ show dbs

# Create new non-existant database:
$ use mydatabase

# Show collections:
$ show collections

# Show contents/documents of a collection:
$ db.your_collection_name.find()

# Save a data to a collection:
$ db.your_collection_name.save({"name":"Sony AK"})

# Show database version:
$ db.version()
```


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
