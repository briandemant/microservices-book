# Random Topics.

This section is my scratch pad where I throw in topics and ideas that I have yet to have a place in the structure or just want to remember to write about.

## Projects to look into

## proxies
https://www.envoyproxy.io/ <- supports grpc
https://istio.io <- service mesh for K8S


## Topics to cover (todo)

* The Monolith
	* Problems
	* How do we make the transition gradual
	* Moving data between systems
		* when legacy is owning it
		* When microservices are owning it
		* renaming and pruning the data (needs to work both ways)

* Layers
	1) Client (website,admin, apps (phone + tablet))
		* React?
		* Graphql?
		* SSO?
		* Style using:
			* tachions
			* tailwind
			* BEM
			* Bootstrap

	2) External clients (Partners)
		* Swagger API

	3) ?? (Loadbalancer, varnish cache, ssl)
		* Use

	4) BFF + Rendering + Rest API
	5) Services
	6) Resource (File Storage, DB, Solr, Message Server a.s.o.)
	7) Operations (kubernetes, logging, metrics)
		* Kubernetes
			* [Setting up on local dev machines](https://kubernetes.io/docs/setup/pick-right-solution/#local-machine-solutions)
			* Setting up on local servers
			* setting up using GKE
	8) External Services (Postnord, Mailchimp.)

* Hosting
	* Local, Cloud or both?
		* Cost vs Convenience
	* Scaling .. is it needed?
	* Resiliency .. how much
		* cost vs need

* Communication
	* Between Layers
		1) Clients => BFF Server
			* Protocol (http2, websocket, graphql, grpc)
			* Message Format (Json, MsgPack ??)
			* logging, throttling, anti-ddos
		2) BFF Server => Services
			* Protocol (http2, nats, zeromq, pubsub)
			* Message Format (Json, Protocol Buffer, MsgPack, Avro, Thrift)
			* Sync, Async or Both?
			* logging, tracing, backpressure
		3) Service => Service
			* Same as 2 or different?
	
	* Tracing
	* CQRS
		* Event Sourceing?

* Standadize on:
	* Languages
		* Typescript
		* Kotlin << why not just ts + go
		* Go-lang
		* PHP (oh god no..)

	* Message Formats
		* as few as possible
		* but with same structure?

	* How to test
		* client
		* is BFF tests like services?
		* test services from outside?

* Continous (Integration + Deploy)
	* which CI server

* Logging + Metrics
	* choosing the right storage

* A/B test

* Gradual roolout of features
	* Beta/Power users only
	* x % of users
	* watch metrics / error rates

* Caching strategies
	* client side (service workers)
	* BFF 
		* Pregenerated on edit?
		* Invalidate using streaming
	* BFF + Service
		* when is stale ok
		* what to return when down
		* when to say "I'm sorry I cannot do that (Dave)"

* Patterns
	* Circuit Breakers
	* Bulkhead

* Outsourceing
	* In house and/or out house?
	* What needs to be clear before this can happen?
	* Who maintains the code?

* Auth+
	* Roles vs Resource
	* JWT 
	* SSO

* Configurability
	* Feature flag
	* A/B testing

* Workflow
	* ....

[qwe](qwe.md)