## Overview
![img.png](images/img.png)

## Deploy Project Locally
Start Airflow on your local machine by running:

```bash
astro dev start
```

This command will spin up 4 Docker containers on your machine, each for a different Airflow component:
- Postgres
- Webserver
- Scheduler
- Triggerer

Verify that all 4 Docker containers were created by running 'docker ps'.
```bash
docker ps
```

Note: Running 'astro dev start' will start your project with the Airflow Webserver exposed at port 8080 and Postgres exposed at port 5432. If you already have either of those ports allocated, you can either [stop your existing Docker containers or change the port](https://docs.astronomer.io/astro/test-and-troubleshoot-locally#ports-are-not-available).

## Prerequisites
- Astro CLI: Make sure you have Astro CLI installed. You can find insturctions to install it [here](https://www.astronomer.io/docs/astro/cli/install-cli)
- Docker: Make sure you have Docker installed on your system. You can download it from [here](https://www.docker.com/products/docker-desktop)
- Docker Compose: Also ensure that Docker Compose is installed. You can find it [here](https://docs.docker.com/compose/install/).

## Services
| Service | Port | User    | Password     |
|---------|------|---------|--------------|
| Airflow | http://localhost:8080 | admin   | admin |
| PostgreSQL | http://localhost:5432 | airflow | airflow      |


## PostgreSQL

The PostgreSQL service is used as the backend database for Airflow. The service exposes the default PostgreSQL port `5432`.

## Airflow

The Airflow service is split into three separate services for the webserver, scheduler, and worker. For access the Airflow UI for your local Airflow project, go to http://localhost:8080/ and log in with 'admin' for both your Username and Password.

