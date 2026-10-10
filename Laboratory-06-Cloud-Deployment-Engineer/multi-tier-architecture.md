# Multi-Tier Architecture

## What Is a Two-Tier Architecture?
A two-tier architecture separates an application into two main parts: a web/application tier and a database tier. In this laboratory, Nextcloud provides the web application and MariaDB stores database information. Docker Compose defines both services so they work together as one application stack.

## The Web/Application Tier
The web/application tier is the part users access through a browser. The Nextcloud container serves the user interface and handles HTTP requests. The configuration maps host port `8080` to container port `80` using `8080:80`.

## The Database Tier
The database tier stores persistent application data such as user accounts and file metadata. This lab uses the `mariadb:10.6` image. The Compose configuration supplies the database name, username, and passwords through environment variables.

## Why Separate Them?
Keeping Nextcloud and MariaDB in separate containers gives each service a clear responsibility and allows them to be managed independently. It also makes the deployment easier to configure and maintain than combining the web application and database in one container. Docker Compose coordinates the services while keeping their roles distinct.
