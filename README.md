# Creazione immagine con servizio rabbitMQ

Immagine per la gestione di RabbitMQ

## Per il build dell'immagine

docker build -f rabbit.Dockerfile -t docker-locale/rabbit .

## Per lanciare il container

docker run -id -p 15673:15672 docker-locale/rabbit bash

## Attivare web admin alla porta 15672

Accedere al container con docker exec -ti <CONTAINER-ID> bash
e lanciare i seguenti comandi facendo attenzione a sostituire 
myadminuser e myadminpassword

Enable web management, OPEN ADMIN AT http://localhost:15672
rabbitmq-plugins enable rabbitmq_management

Delete admin user with ignore error ( for first run )
rabbitmqctl delete_user admin

Delete default guest admin user with ignore error ( if already run )
rabbitmqctl delete_user guest

Add RabbitMQ admin user with password
rabbitmqctl add_user myadminuser myadminpassword

Set administration tag for admin
rabbitmqctl set_user_tags myadminuser administrator