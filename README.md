Open Access Compliance Project (OCAP)
=====================================

This version is [forked from Manchester University Lirary](https://github.com/UoMLibrary/OACP.git) 

Some modificaiton added for simpler development exploration.

Setup to run OACP application in local laptop
=============================================

Install Java development tools

## Install JAVA SDK 8

## Install Maven

## Clone repository
```
git clone https://github.com/digital-york/OACP.git
```

## Import project in IDE

For example in Exlipse IDE folow:

Eclipse-->"File"-->"Existing Maven Projects"

## Configure PostgreSQL

### Install DB
For example with docker
```
docker pull postgres
docker run --name postgres -p 5432:5432 -e POSTGRES_PASSWORD=<password> postgres
```

#### Manage PostgresSQL docker container

- `docker ps`- List all running Docker containers.
- `docker stop postgres` - Stop the PostgreSQL container.
- `docker start postgres` - Start the PostgreSQL container.
- `docker rm postgres` - Delete the PostgreSQL container.

### Connect to PostgreSQL and create DB
Connect with local PostSLQ DB
```
psql -U postgres -h localhost -p 5432
```

Create DB
```
CREATE DATABASE oacp;
```

# Configure application properties

Set expected varianles as per `src/main/resources/application.properties` file. Note default configuration require setting up some shell variables so that password are not stored in source code reopository.

In Linux/MacOS
```
export DB_USER="postgres - e.g or other PostgreSQL Admin user as configured in Docker"
export DB_PASSWORD="...."
export SCHOLARLY_API_KEY="..."
export PURE_URL="..."
export PURE_API_KEY="..."
export PURE_USER="..."
export PURE_PASSWORD="..."

```

# Run spring-boot local server
With Maven cli:
```
mvn spring-boot:run
```

## visit application with browser
 Open localhost url http://localhost:8080 

 Search for example pureId: 99829207, 99569551, 99568563, 99568343, 99567735	


