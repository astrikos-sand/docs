# Thingsboard

ThingsBoard is an open-source IoT platform for data collection, processing, visualization, and device management.

## Installation

- [Thingsboard Installation](https://thingsboard.io/docs/user-guide/install/building-from-source/)
- [Guide for contributor](https://thingsboard.io/docs/user-guide/contribution/how-to-contribute/)
- We are currently working on the top of `release-3.6` branch of Thingsboard

### Requirements

This is as per `release-3.6` branch

- Java 11
- Maven around 3.6
- TimescaleDB - PostgreSQL based time-series database. We are currently using the docker image `timescale/timescaledb-ha:pg16`
- RabbitMQ - Message broker. We are currently using the docker image `rabbitmq:3.13.0-alpine`

### TimescaleDB

- Run `docker compose up timescaledb --build -d` to start the TimescaleDB container. The username and password are configured in the `docker-compose.yml` file
- We are using docker volume to persist the data

### RabbitMQ

- Run `docker compose up broker --build -d` to start the RabbitMQ container. The username and password are configured in the `docker-compose.yml` file

### Steps

The following steps are for `ubuntu 22.04 LTS`

- Run `git clone https://github.com/astrikos-sand/thingsboard`
- Run `sudo apt update` to update the package list
- Run `sudo apt install openjdk-11-jdk` to install Java 11
- Run `sudo update-alternatives --config java` to set the default java version to 11
- Run `java -version` to check the java version
- Run `sudo apt-get install maven` to install maven
- Run `mvn -version` to check the maven version
- Make sure the DB and broker configurations are correctly set
- Run `mvn clean install -DskipTests` to build the project skipping the tests
- The above steps will create a jar file in the `application/target` directory
- Run the following command to populate the db
```
cd application/target/bin/install
chmod +x install_dev_db.sh
./install_dev_db.sh
```

### Commands

- `mvn install -DskipTests` - Use this command when there are changes in the source code and you want to build the project reusing the previous build
- `lsb_release -a` - To check the ubuntu version
- `java -jar application/target/thingsboard-3.6.4-boot.jar` - To run the jar file

## Good to know

- `ui-ngx` is the Angular based UI for Thingsboard

## References

- [Thingsboard Website](https://thingsboard.io/)
- [Thingsboard Documentation](https://thingsboard.io/docs/) - Switch to community edition
- [Thingsboard GitHub](https://github.com/thingsboard/thingsboard)
