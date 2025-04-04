# docker-deployment
an example on how to deploy keepMeAlive3d with docker

## Setup

Note: skip steps with services you already have running.

1. clone the repo to where you want to the project

### Mysql

1. change in the `mysql/docker-compose.yml` the credentials
2. run `docker compose up -d`
3. (optional) add a new user to access the db

### Mqtt

1. change the password in `/mqtt/mosquitto/passwd`
2. run docker: `docker compose up -d`
3. run this command once to hash the password: `docker exec mqtt mosquitto_passwd -U /etc/mosquitto/passwd`
4. check that the password in `/mqtt/mosquitto/passwd` was hashed

### Proxy

1. change the default email in the `proxy/docker-compose.yml`
2. run `docker compose up -d`

### KeepMeAlive3d

1. change the credentials in the `kma/config.yml` according to the credentials created in the steps before
2. change the host env variables in the `kma/docker-compose.yml`