---
sidebar_position: 1
---

# Quick Start

To test the messaging module, you can use docker compose to configure the environment.

Play around with RabbitMQ:
```
docker-compose -f quickstart-rabbitmq.yml  up

curl -X POST localhost:8080/messaging/quickstart_testing_queue -H 'Content-type:application/json' -d '{"message":"Hello Consumer"}'

// You will see on the console :  queue1 consumer receive message: Hello Consumer

curl -X POST localhost:8080/messaging/publish/quickstart_testing_topic -H 'Content-type:application/json' -d '{"message":"Hello Subscribers"}'

// You will see on the console :  queue1 consumer receive message: Hello Subscriber
//                                queue2 consumer receive message: Hello Subscriber

```