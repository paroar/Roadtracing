# Roadtracing

Roadtracing is a project that stores coordinates to track and identify dangerous accelerations.

&nbsp;

## Composition

The project is composed of a mobile app, a queue and a database.

### Mobile App

The [mobile-app] sends data to the queue via websockets.

### Queue

In case the database is down, Apache Kafka allow us to buffer the data until the database is up and running again.

For this to work we need a producer and a consumer.

The [producer] receives data via websocket and sends it to kafka.

The [consumer] consumes data from kafka and inserts it into a databse.

### Database

Mongodb, an easy to use database.

&nbsp;

## Usage

The provided docker-compose file is a basic configuration of roadtracing. We can configure kafka to have more partitions and brokers.

Run containers.

```sh
docker-compose up
```

Stop containers.

```sh
docker-compose stop
```

Remove containers.

```sh
docker-compose down
```

&nbsp;

## Contact

Pablo Rodríguez - [@linkedin][linkedin-url] - prodriguezarmida@gmail.com

<!--LINKS-->
[mobile-app]: https://github.com/paroar/roadtracing-mobile
[producer]: https://github.com/paroar/roadtracing-rest-kafka
[consumer]: https://github.com/paroar/roadtracing-kafka-mongo
[linkedin-url]: https://linkedin.com/in/paroar