
## a. What is AMQP?

AMQP (Advanced Message Queuing Protocol) is an open standard protocol used for message-oriented middleware. It enables systems to communicate by sending messages via a message broker (like RabbitMQ), decoupling the sender and receiver and allowing for reliable, asynchronous communication between services.

---

## b. What does it mean? guest:guest@localhost:5672

This is a connection URI for an AMQP-compatible message broker (usually RabbitMQ).

- **First `guest`**: This is the **username** used to authenticate with the message broker.
- **Second `guest`**: This is the **password** for that username.
- **`localhost`**: This refers to the **host address** where the message broker is running. `localhost` means it's running on the same machine.
- **`5672`**: This is the **port number** used by RabbitMQ (or any AMQP broker) to accept connections using the AMQP protocol.

So, `guest:guest@localhost:5672` is a way of connecting to RabbitMQ using the default `guest` user over the default AMQP port on your local machine.