# Laboratory 06 - Cloud Deployment Engineer

## Mission Overview
This mission deploys a two-tier private cloud storage application using Nextcloud and MariaDB. Docker Compose defines both services in YAML and starts the stack with one command.

## Objectives
- Explain multi-tier application architecture.
- Understand the structure of `docker-compose.yml`.
- Use `nano` to create configuration files.
- Deploy Nextcloud and MariaDB using Docker Compose.
- Document deployment procedures and Infrastructure as Code (IaC).

## Commands Executed
```bash
mkdir nextcloud-deployment
cd nextcloud-deployment
nano docker-compose.yml
docker-compose up -d
docker-compose ps
docker-compose down
```
Run these commands in your own KillerCoda environment and capture the actual results.

## Skills Learned
- Understanding web/application and database tiers
- Writing correctly indented YAML
- Configuring services and environment variables
- Deploying and inspecting multi-container applications
- Accessing a web app through port forwarding
- Using Docker Compose and documenting IaC

## Required Evidence
Place your real screenshots in `screenshots/`:
- `compose-deployment.png` — deployment and running containers
- `nextcloud-web.png` — Nextcloud installation page
- `compose-teardown.png` — containers stopped and removed

## AI Assistance
AI helped draft and organize this documentation. Review it against your own lab results and follow your instructor's disclosure requirements.
