# AdvProg-Module9
Name : Siti Shofi Nadhifa <br>
NPM : 2306152172 <br>
Class : AdPro B

### a. How much data your publisher program will send to the message broker in one run?
The publisher program sends 5 messages to the message broker in one run. Each message is a `UserCreatedEventMessage` containing a `user_id` and a `user_name`, and they are sent one by one using the `publish_event` method. All these messages are directed to the same queue named `user_created`. I think this means the total data sent depends on the serialized size of each message using Borsh, but from a message-count perspective, it always sends exactly five messages per execution.

### b. What does it mean? guest:guest@localhost:5672 , what is the first guest, and what is the second guest, and what is `localhost:5672` is for?
The connection string `amqp://guest:guest@localhost:5672` is used to connect to an AMQP-compatible message broker, such as RabbitMQ. In this string, the first `guest` represents the username, and the second `guest` represents the password used for authentication with the broker. The `localhost` part indicates that the broker is running on the same machine where the code is being executed, and `5672` is the default port on which RabbitMQ listens for AMQP connections. This URL allows the program to establish a connection to the message broker so it can send or receive messages through defined queues. In this tutorial, this connection is used by the `CrosstownBus` listener to subscribe to a queue named `user_created` and process incoming messages using a custom handler.
