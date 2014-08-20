---
layout: default
title: Message Transport
---

The Message Transport integrates [Service Resources]({{site_url}}/services_resources), providing a messaging infrastructure that enables services to communicate with one another.  Services use the Message Transport layer to send asynchronous messages to one another and to publish and subscribe to events.  The ACApi supports the following messaging software:

| Transport Component	| Description |
| --------------------- | ----------- |
| Oracle Service Bus (OSB)	| Service Bus and Application Server |
| RabbitMQ	| MOM broker |

Transport mechanisms and the on-ramps are provided by the following components:

| Transport Component	| Available Interfaces |
| --------------------- | ------------------- |
| Oracle Service Bus (OSB)	| HTTP, JMS |
| RabbitMQ	 | AMQP |

## Oracle Service Bus
The Oracle Service Bus (OSB) is an integration platform which exposes several legacy, DCHBX discrete services as HTTP endpoints and JMS endpoints.  HTTP clients can access these services to build a process or to simply invoke one, discrete service, as required.  The OSB is also a JMS provider through the base application server and allows JMS endpoints to be established for Pub/Sub and Point-to-Point consumption.

### Software Version

| Component	| Version	| Date	| Comments |
| --------- | --------- | ----- | -------- |
| Oracle Service Bus	| ??	| ??	|

## RabbitMQ
RabbitMQ is an open-source, message broker which implements Advanced Message Queuing Protocol (AMQP).  It receives, transports, routes, and delivers message payloads.  The RabbitMQ server component is written in the Erlang programming language and is built on the Open Telecom Platform framework for clustering and failover.  AMQP is a platform-neutral, wire level protocol.

RabbitMQ was chosen to fulfill the MQ requirements for fulfilling Resource related requests and delivering Resource related events for its lightweight, reliable, scalable, and portable characteristics.

### Software Version

| Component	| Version	| Date	| Comments |
| --------- | --------- | ----- | -------- |
| RabbitMQ	| 2.x	| 5/5/2014	| |

 
## AMQP Basics
AMQP and RabbitMQ use the following concepts:

| Component	| Description |
| --------- | ----------- |
| Producers	| Producers publish or submit messages | 
| Consumers	| Consumers receive messages and perform tasks or work | 
| Exchanges	| Exchanges are setup to accept messages from the Producers | 
| Routing Keys	| Routing Keys tell Exchanges which Queues to deliver messages to | 
| Queues	| Queues are the destinations which store messages published to Exchanges until pushed to or pulled by a Consumer  | 

AMQP is a message protocol that deals with Producers and Consumers.  Producers publish messages and consumers receive the messages and process them.  The message broker, in this case RabbitMQ, ensures that the messages from Producers get to the correct Consumers.  The key components in this delivery mechanism are Exchanges and Queues.

Producers, or publishers, send messages to named Exchanges and the Consumers pull messages from queues (or the queue may push messages to a Consumer depending on the configuration).  Connections between the Producers and Consumers need to be made and they discover each other by known Exchange, Routing, and Queue naming conventions.

Messages are routed to or bound to Queues in an Exchange by specifying a Routing Key.  A Routing Key is one of the standard headers of an AMQP message.  An AMQP message structure contains:

| AMQP Message Structure	| Description |
| ------------------------- | ----------- |
| Headers	| AMQP specification defined name/value pairs |
| Properties	| Arbitrarily defined name/value pairs – application specific |
| Data	| A sequence of bytes representing the message payload |

The Routing Key is an AMQP standard Header, “routing-key” which is used to match messages to a particular Queue or group of Queues within an Exchange.  There are multiple Exchange types which handle message delivery differently also.  An intelligent utilization of Exchange types, Routing Keys, and Queues will facilitate any pattern required by an application:

| AMQP Exchange Type	    | Description |
| ------------------------- | ----------- |
| Direct	| Delivers messages to Queues based on the message routing key |
| Topic	| Topic exchanges route messages to one or many Queues based on matching between a message Routing Key and the pattern that was used to bind a Queue to an Exchange |
| Fanout	| Delivers messages to all of the Queues that are bound to the Exchange and the Routing Key is ignored |
| Headers	| Delivers messages to Queues based on multiple attributes that are more easily expressed as message headers than a Routing Key |

## AMQP HBX Naming Conventions
The OpenHBX utilizes a fairly strict naming convention on Exchanges and Queues in order to allow for modest initial discovery.

Exchange naming convention takes on the following form:

```
For resource operations (requests and events),

    <hbx_id>.<environment>.<version>.e.<e_type>.<resource_type>, 

where
```

| Exchange Naming Component	| Definition |
| ------------------------- | ---------- |
| hbx_id  | HBX assigned exchange code where DCHBX = “DC0” or "dc0" |
| environment | HBX environment as prod = Production, dev = Development, etc. |
| version | Service version |
| e       | Denotes an AMQP Exchange |
| e_type	| AMQP Exchange Type where direct = Direct Exchange, fanout = Fanout Exchange, topic = Topic Exchange, headers = Headers Exchange |
| resource_type	| HBX named resource type (lower-case), for example, individual = Individual Resource |

Queue naming conventions take on a similar form to their Exchange parents:

```
For resource operations (requests and events),
    
    <hbx_id>.<environment>.q.<consumer_name>.<message_type>, 

where
```

| Queue Naming Component	| Definition |
| ------------------------- | ---------- |
| hbx_id  | HBX assigned exchange code where DCHBX = “DC0” or "dc0" |
| environment | HBX environment as prod = Production, dev = Development, etc. |
| version | Service version |
| q       | Denotes an AMQP Queue |
| consumer_name	| Consumer listening to this queue to consume messages |
| message_type	| Message type further categorizes the queue for request or event type messages |
