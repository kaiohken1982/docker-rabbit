# Creazione immagine con servizio rabbitMQ

Immagine per la gestione di RabbitMQ

## Per il build dell'immagine

docker build -f rabbit.Dockerfile -t docker-locale/rabbit .

## Per lanciare il container

docker run -id docker-locale/rabbit bash