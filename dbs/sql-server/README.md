# SQL Server 2019

SQL Server 2019 (15.x) builds on previous releases to grow SQL Server as a platform that gives you choices of development languages, data types, on-premises or cloud environments, and operating systems.

For more info please visit SQL Server 2019 [official page](https://www.microsoft.com/en-us/sql-server/sql-server-2019) and [documentation](https://docs.microsoft.com/en-us/sql/sql-server/what-s-new-in-sql-server-ver15?view=sql-server-ver15).

# Requirements

By default, sql serve 2019 exposes the following ports:
* [1433](http://localhost:1433): SQL Server's default port

# Usage

Start services locally using Docker Compose:

```
$ docker-compose up
```

You can also run all services in the background (detached mode) by adding the `-d` flag to the above command.

# Restore AdventureWorks
## Step 1. Download AdventureWorks sample database files
You can download AdventureWorks by following this [link](https://docs.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver15&tabs=ssms)

or through `curl` / `wget`
```
$ wget https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorks2019.bak

# or

$ curl -L -o AdventureWorks2019.bak 'https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorks2019.bak'

```

## Step 2. Create a backup folder for .bak files inside sql container
```
$ sudo docker exec -it sql1 mkdir /var/opt/mssql/backup
```

## Step 3. Copy sample database
```
$ sudo docker cp AdventureWorks2019.bak sql1:/var/opt/mssql/backup
```

### Step 5. Restore sample database
#### 5.1 Run sqlcmd inside the container to list out logical file names and paths inside the backup.
```
$ sudo docker exec -it sql1 /opt/mssql-tools/bin/sqlcmd -S localhost \
   -U SA -P '<YourStrong@Passw0rd>' \
   -Q 'RESTORE FILELISTONLY FROM DISK = "/var/opt/mssql/backup/AdventureWorks2019.bak"' \
   | tr -s ' ' | cut -d ' ' -f 1-2
```

#### 5.2 Restore database 
```
$ sudo docker exec -it sql1 /opt/mssql-tools/bin/sqlcmd \
   -S localhost -U SA -P '<YourStrong@Passw0rd>' \
	 -Q 'RESTORE DATABASE [AdventureWorks] FROM DISK = "/var/opt/mssql/backup/AdventureWorks2019.bak" WITH FILE = 1, MOVE "AdventureWorks2017" TO "/var/opt/mssql/data/AdventureWorks.mdf", MOVE "AdventureWorks2017_log" TO "/var/opt/mssql/data/AdventureWorks_log.ldf", NOUNLOAD, STATS = 5'
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
