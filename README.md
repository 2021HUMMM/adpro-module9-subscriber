
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



<img width="1280" alt="slow_subscriber" src="https://github.com/user-attachments/assets/572b4e33-cb76-445c-ba59-f92478f24984" />
In this case, the RabbitMQ management interface shows a total of 6 messages in the queue after the publisher was run twice. Each time it runs, the publisher sends 5 messages, so a total of 10 messages were published. However, only 6 messages remain in the queue, which means 4 messages have already been consumed by the subscriber. This partial consumption happens because the subscriber is intentionally slowed down by a short delay introduced through the thread::sleep(ten_millis); line in the code. This delay causes the subscriber to process messages more slowly than the publisher sends them. As a result, not all 10 messages are consumed immediately, and some remain queued. The number is not exactly 10 because the subscriber was able to consume a few messages between or during the publishing processes, leading to only 6 remaining in the queue.