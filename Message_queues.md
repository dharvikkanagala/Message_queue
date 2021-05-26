# Message queues

### queue
A queue is a row of things waiting to be processed, starting from the beginning of the line and processing them in order. The message queue is a message sent between applications. It includes a series of work objects waiting to be processed.

### message
Messages are data transferred between the sender and receiver applications. It is essentially a byte array with some headers at the top. An example of a message can be a message that tells a system to start processing a task, it can contain information about a completed task, or it can be just a normal message.

The basic architecture of a message queue is simple; there are client applications called producers that create messages and deliver them to the message queue. Another application, called a consumer, connects to the queue and gets the messages to be processed. Messages placed onto the queue are stored until the consumer retrieves them.

![Message queue](https://www.cloudamqp.com/img/blog/message-queue-small.png)

## Message queues
A message queue provides an asynchronous communications protocol, which is a system that puts a message onto a message queue and does not require an immediate response to continuing processing. Email is probably the best example of asynchronous communication. When an email is sent, the sender continues to process other things without needing an immediate response from the receiver. This way of handling messages decouples the producer from the consumer so that they do not need to interact with the message queue at the same time.

In modern cloud architecture, applications are decoupled into smaller, independent building blocks that are easier to develop, deploy and maintain. Message queues provide communication and coordination for these distributed applications. Message queues can significantly simplify the coding of decoupled applications while improving performance, reliability, and scalability.

Message queues allow different parts of the system to communicate and process operations asynchronously. The message queue provides a lightweight buffer for the temporary storage of messages and also provides endpoints that allow software components to connect to the queue to send and receive messages. These messages are usually small and can be information such as requests, replies, error messages, or just simple messages. To send a message, a component called a producer adds the message to the queue. The message will be stored in the queue until another component called the consumer retrieves the message and processes it.

![Message Queue](https://d1.awsstatic.com/product-marketing/Messaging/sqs_seo_queue.1dc710b63346bef869ee34b8a9a76abc014fbfc9.png)

Many producers and consumers can use the queue, but each message is processed only once, by a single consumer. For this reason, this messaging pattern is often called one-to-one, or point-to-point, communications. When a message needs to be processed by more than one consumer, message queues can be combined with Pub/Sub messaging in a fanout design pattern. See ["What is Pub/Sub messaging?"](https://aws.amazon.com/pub-sub-messaging/) 

## Benefits

Message queuing solutions are widely used across industries and can offer an array of benefits to developers and system administrators alike, including the following:

- **Reliable message delivery**: Using a message queue can ensure that business-critical messages between applications will not be lost and that they will be only be delivered to the recipient once. With this feature in place, additional de-duplication or loss-prevention logic is unnecessary.

- **Inter-application connectivity**: Some message queue solutions can handle message encryption, transactionality, and other communication aspects between applications and services. This simplifies application development and enables disparate architectures to work together.
Versatility: Message queue solutions can support multiple languages, such as Java, Node.js, COBOL, C/C++, Go, .NET, Python, Ruby, and C#. They can also support numerous application programming interfaces (APIs) and protocols, including MQTT, AMQP, and REST, as well as others.

- **Resilience**: Asynchronous messaging ensures application-specific faults won’t impact the system. If one component in the system stalls, all others can continue interacting with the queue and processing messages. This decreases the chance that the entire system’s stability will be impacted by one part’s failure.

- **Improved security**: A message queue may be able to identify and authenticate all messages, and in some message queue solutions, they can be set to encrypt messages at rest, in transit, or end-to-end. This can contribute to the overall security of the applications and/or infrastructure.
- **Integrated file transfers**: Some message queue solutions include additional features, such as the ability to transfer files. This can be used as an alternative to FTP within enterprises where such solutions are in use.

## Best Message Queue Tools

1. Kafka

2. RabbitMQ

3. Amazon SQS

4. Celery

5. MQTT

6. ActiveMQ

7. Apache NiFi

8. Azure Service Bus

9. ZeroMQ

10. Confluent

## Enterprise Service Bus (ESB)

An Enterprise Service Bus (ESB) is fundamentally an architecture. It is a set of rules and principles for integrating numerous applications over a bus-like infrastructure. ESB products enable users to build this type of architecture but vary in the way that they do it and the capabilities that they offer. The core concept of the ESB architecture is that you integrate different applications by putting a communication bus between them and then enable each application to talk to the bus. This decouples systems from each other, allowing them to communicate without dependency on or knowledge of other systems on the bus. The concept of ESB was born out of the need to move away from point-to-point integration, which becomes brittle and hard to manage over time. Point-to-point integration results in custom integration code being spread among applications with no central way to monitor or troubleshoot. This is often referred to as "spaghetti code" and does not scale because it creates tight dependencies between applications.

Increasing organizational agility by reducing time to market for new initiatives is one of the most common reasons that companies implement an ESB as the backbone of their IT infrastructure. An ESB architecture facilitates this by providing a simple, well-defined, "pluggable" system that scales well. Additionally, an ESB provides a way to leverage your existing systems and expose them to new applications using its communication and transformation capabilities.

## Reference
https://www.ibm.com/cloud/learn/message-queues

https://www.cloudamqp.com/blog/what-is-message-queuing.html

https://stackshare.io/message-queue

https://aws.amazon.com/pub-sub-messaging/

https://www.mulesoft.com/resources/esb/what-esb