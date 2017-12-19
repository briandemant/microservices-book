# Communication in distributed services

## Goals

* Fast
* Traceable
* Debugable
* Resilient
* "Offline"
* Streaming

## Theory

Communication can seem hard, especially asynchronous communication. But the fact is that life is mostly async (think about ordering at a restaurant).

I means that we as developers have to embrace stuff like "eventual consistency"
and network failures.

### Guaranteed Delivery?

What does "delivery guarantee" mean?

* Message handed to transport layer?
* Enqueued in the recipients inbox?
* Recipient started processing it
* .. finished?
* got a ok response?

And before you start thinking, let's just use http instead of message queues,
then consider the following.

```bash
	curl http://something/create/thing
	curl: (28) Operation timed out after 12034 milliseconds with 0 bytes received
```

Did the thing get created? or did the reciever ever get the call? was it the
proxy?

#### Solution

    Make messages *Replayable* by making them idempotent, so that you can retry if unsure of the delivery.

### Ordered Delivery

This one is easier to do with http, but only if you wait to do the next call
after the first one has finished.

Some message queues makes this easy at the cost of speed, some let you partition
your messages, so the the ones with the same "key" are guaranteed to be
delivered in an orderly fashion.

### Exactly Once Delivery

When we get a response then exactly once is also easy using http. But if the
request times out, then all luck is out. Should you call again or just pretend
it was delivered?

Queueing system are at-least-once or at-most-once, meaning 1 or more deliveries
of the same message or 1 or never. Depending on the need both can be useful.

## Transport protocols

* http, https & http2 (push?)
* grpc
* events
* combination?

## Serialisation

* JSON
* Protocol Buffer
* [MessagePack](https://msgpack.org/index.html)
* [BSON](http://bsonspec.org/)
* YAML
* Avro

https://gist.github.com/frsyuki/2908191
https://www.sitepoint.com/data-serialization-comparison-json-yaml-bson-messagepack/

## Patterns

* Request => response
* Message Bus
* Pub/Sub aka Broadcast
* Work distribution

## Sources:

* [You Cannot Have Exactly-Once Delivery](http://bravenewgeek.com/you-cannot-have-exactly-once-delivery/)
* [Exactly-once Semantics are Possible](https://www.confluent.io/blog/exactly-once-semantics-are-possible-heres-how-apache-kafka-does-it/)
