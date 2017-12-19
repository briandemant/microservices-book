# Glossary
These are the definitions we work with.

## Monolith 
A monolithic application is built as a single unit where all aspects are mixed
up. But even if there are separate components, but these components can be
written in a way where they are too coupled for them to be reused og rewritten
easily. a service is a service of services

## Microservice
A system where each component can be deployed and scaled independently from the rest of the system

for more details see service / component

## Service
An isolated set of functionality that runs independently of the rest of the system

## System
A collection of components/modules/services that works in tandem.

## Scalability
The ability of a system to make use of more computing resources in order to increase its performance to meet increased demands. But also the ability to decrease once these demands are waning off.

## Idempotent
An action is indempotent if the outcome is unchanged if the action is taken
multiple times.

An example going from bad to ok

* delete *file.txt*
* delete *file.txt* if exists
* delete *file.txt* if hash is *xxx*
* delete *file.txt* if hash is *xxx*, and creation time is *"2017-02-23 12:43"*

Another way to achieve this is marking the message/command with a uuid and
checking if that action has already been executed

## Component
An isolated piece of the system. I can be a complete service or a module.

## Client
A consumer of a service. This can be a human, but also another service.

## upstream

A client/service the connects to a downstream service or resource

## Downstream
A service/resource that receives connection from upstream

## Resource
A special kind of "service" (ie. database, storage a.s.o.)

## Asynchronous
Asynchronous means “not existing or occurring at the same time”. In this context it means not a direct request => response. The caller is able continue on and maybe react to a response later.

## Back pressure
When one services is struggling to keep up with messages from other services. The system as a whole should be able to respond in a sensible way. It is unacceptable for the service under stress to fail catastrophically or to drop messages in an uncontrolled fashion. Since it can’t cope and it can’t fail it should communicate the fact that it is under stress to upstream services and so get them to reduce the load.

## Batching 
Instead of sending request / doing related work piece by piece it is sometimes beneficial to wait and do the work in "batches" where it makes sense. Ie. instead of saving each property of a user one by one it makes sense to save the complete record. 

## Protocol
A protocol defines the formats and rules for the exchange or transmission of messages between components/services.
Protocol can be layered (GRPC uses http2 which in turn uses https .. tcp .. ip .. ethernet)

## Encoding format
The format used to serialize/deserialize messages when two or more services are communicating. (ie. JSON, XML, YAML, Protocol Buffer).

## Delegation
Delegating a task asynchronously to another component or service means that the task will take place in the context of that other component. The purpose of delegation is to hand over the responsibility of a task to another component, so that the delegating component can focus om more time critical tasks.

## Non Blocking
Offloading resource heavy tasks to other threads so that the main thread can focus om more time critical tasks.

## Bounded Context
Bounded Context is a pattern from DDD where the system is divided into collections of components (Business contexts) 

## section
A set of "pages" that are related and relatively isolated from the rest.
ie. "Labels" (Pakkepost) or "Listing creation"

## Responsible design
Responsible design adapts the layout to the viewing environment by using fluid, proportion-based grids, flexible images, and CSS3 media queries.

[A good explanation](https://www.uxpin.com/studio/blog/responsive-vs-adaptive-design-whats-best-choice-designers/)

see Adaptive vs Responsive the definition management uses

## Adaptive design
Adaptive design was originally defined as a process of server-side detection that chooses a design layout and size to display, which is then static until reload.

[A good explanation](https://www.uxpin.com/studio/blog/responsive-vs-adaptive-design-whats-best-choice-designers/)

see Adaptive vs Responsive the definition management uses

## Adaptive vs Responsive
changes width and placement of elements using:
* Responsive :  fluid (%) widths
* Adaptive :  fixed (px) widths (snaps to fixed widths)

[see also](https://css-tricks.com/the-difference-between-responsive-and-adaptive-design/)

# Progressive Enhanced
A strategy for web design where the user at first get a basic html+css page which then is enhanced with additional presentation and behaviour asynchronously 