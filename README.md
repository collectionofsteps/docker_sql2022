# Installation of docker on windows 10 for sql 2022
## Prerequsites
```
    install windows subsystem for linux
    install docker desktop logged in as Administrator
    run the following commands
    c:
    cd\
    mkdir docker
    mkdir docker\project_sql2022
    mkdir docker\volumes_local
    mkdir docker\volumes_local\sqlbackup
    cd docker\project_sql2022
    git clone https://github.com/collectionofsteps/docker_sql2022
```
---

---
## Windows subsystem for Linux 
---
```
    cmd run as Administrator
    wsl --list
    wsl --list --running
    wsl --update
    wsl --shutdown
```
---
## Start / Stop Docker Service
---
```
    net start com.docker.service
    net stop com.docker.service
```
---
## Docker Commands
---
### Start / Stop docker image from folder
```
    docker-compose up -d
    docker-compose down --remove-orphans
```
### Update docker image from docker-compose.yml 
```
    docker-compose up --force-recreate --build -d
    docker image prune -f
```
`OR`
```
    docker-compose pull
    docker-compose up -d --remove-orphans
    docker image prune -f
```
### Docker Container commands
```
    docker container ls
    docker exec container_sql2022 printenv
```
### Docker Volume commands
```
    docker volume --help
    docker volume ls
    docker volume rm project-mssql2022_sqlbackup rm
    docker volume rm project-mssql2022_sqldata
    docker volume rm project-mssql2022_sqllog
    docker volume rm project-mssql2022_sqlsystem
```
### Docker shell into container
```
    docker exec -it -u mssql container_sql2022 /bin/bash
    docker exec -it -u root container_sql2022 /bin/bash
```
---
## References:

- __[GitHub](https://github.com/dbafromthecold/SqlServerDockerCompose)__ - SqlServerDockerCompose
- __[MS install SQL on Ubuntu](https://learn.microsoft.com/en-us/sql/linux/quickstart-install-connect-ubuntu?view=sql-server-linux-ver16&preserve-view=true)__
---
