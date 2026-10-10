# Docker Compose Guide

## Compose Configuration
The following YAML follows the structure and values provided in the laboratory handout:

```yaml
version: '3'

services:
  database:
    image: mariadb:10.6
    environment:
      - MYSQL_ROOT_PASSWORD=cloudnova_root
      - MYSQL_PASSWORD=cloudnova_pass
      - MYSQL_DATABASE=nextcloud_db
      - MYSQL_USER=nextcloud_user

  app:
    image: nextcloud
    ports:
      - 8080:80
    environment:
      - MYSQL_PASSWORD=cloudnova_pass
      - MYSQL_DATABASE=nextcloud_db
      - MYSQL_USER=nextcloud_user
      - MYSQL_HOST=database
```

**Important:** This reproduces the configuration provided in the handout. For real deployments, verify current Nextcloud database setup requirements and use secrets management rather than publishing real passwords in a public repository.

## What Does `services:` Do?
The `services:` block defines the containers in the application. Here, `database` describes MariaDB and `app` describes Nextcloud. Each service specifies its image and configuration.

## How Does Nextcloud Find the Database?
`MYSQL_HOST=database` names the database service as the host. On a Docker Compose network, services can generally communicate using their service names, so `database` is the intended database hostname.

## Environment Variables
- `MYSQL_ROOT_PASSWORD` sets the MariaDB root password.
- `MYSQL_PASSWORD` supplies the database user's password.
- `MYSQL_DATABASE` specifies the database name.
- `MYSQL_USER` specifies the database user.
- `MYSQL_HOST` tells the app which hostname to use for the database.

Environment variables separate configuration from the container image, but they are not a secure secrets-management system by themselves.

## `docker run` vs. `docker-compose up -d`
- `docker run` starts an individual container by specifying its options in a command.
- `docker-compose up -d` reads a Compose YAML file and creates or starts the defined services in the background. This is convenient for multi-container applications because configuration is saved and reusable.

## Deployment Steps
```bash
mkdir nextcloud-deployment
cd nextcloud-deployment
nano docker-compose.yml
docker-compose up -d
docker-compose ps
```

In KillerCoda, open **Traffic / Ports** or **Custom Ports**, access port `8080`, and check for the Nextcloud installation page. Then stop and remove the stack:

```bash
docker-compose down
```

## Screenshots
Add your actual screenshots to `screenshots/`:
- `compose-deployment.png`
- `nextcloud-web.png`
- `compose-teardown.png`
