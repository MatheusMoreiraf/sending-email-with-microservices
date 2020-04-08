# Sending email with microservices
Project for sending email with workers (microservices). Project architecture image:

![alt text](https://github.com/MatheusMoreiraf/sending-email-with-microservices/blob/master/arq.png?raw=true)
## Require

+ Docker
+ Docker-composer

## Usage

### Boot containers  

```
docker-compose up [options]
``` 
> Option '-d', runs the containers in the background, print new container names.
### Delete containers  
```
docker-compose down
```

> ContainerDelete command does NOT delete data and contents.  

## Bug fixing

### Fixed PostgreSQL password error
```
docker-compose exec db psql -U postgres -c "ALTER USER postgres WITH PASSWORD 'postgres'"
```
> To do this, start the database container. Then restart the container.

## Credits
This project is part of a module of the course "Docker: Ferramenta essencial para Desenvolvedores" [link](https://www.udemy.com/course/curso-docker/).