# Sending email with microservices
Project for sending email with workers (microservices). Project architecture image:

![alt text](https://github.com/MatheusMoreiraf/sending-email-with-microservices/blob/master/arq.png?raw=true)
## Require

+ Docker
+ Docker-composer

## Usage

### Boot containers  

```
docker-compose up [options] [--scale SERVICE=NUM...]
``` 
> Ex: docker-compose up -d --scale worker=3

### Stop containers  
```
docker-compose down
```  

## Bug fixing

### Fixed PostgreSQL password error
```
docker-compose exec db psql -U postgres -c "ALTER USER postgres WITH PASSWORD 'postgres'"
```
> To do this, start the database container. Then restart the container.

### AppArmor on Linux Deepin
```
$ sudo mkdir -p /etc/default/grub.d
$ echo 'GRUB_CMDLINE_LINUX_DEFAULT="$GRUB_CMDLINE_LINUX_DEFAULT apparmor=0"' | sudo tee /etc/default/grub.d/apparmor.cfg
$ sudo update-grub
$ sudo reboot
```
> [stackoverflow](https://stackoverflow.com/questions/55767067/nginx-emerg-socket-0-0-0-080-failed-13-permission-denied-on-docker)

## Credits
This project is part of a module of the course "Docker: Ferramenta essencial para Desenvolvedores" [link](https://www.udemy.com/course/curso-docker/).
