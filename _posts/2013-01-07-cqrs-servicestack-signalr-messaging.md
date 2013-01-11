---
layout: post
title: "From CRUD to CQRS for fun and profit"
description: ""
category: Brainfarts
tags: [CQRS, ServiceStack, SignalR, Messaging]
---
{% include JB/setup %}

I recently attended Greg Young's CQRS and Advanced DDD course.
In many ways, it asked more questions than it answered. In order to crystallize some of the concepts I learnt, I will walk through creating an implementation.

Goals:
Understanding CQRS architecture benefits and drawbacks
 * Commands
 * Aggregates
 * Events
 * Handlers

Infrastructure:
 * MQs
 * Event Store
 * Read Model Store
 * Task-based UI Front End

No silver bullets.
Don't need complex heavy frameworks.
The hard bit is the thinking and the conversations (as with any DDD project)

### CQRS
CQRS is more of a mindset, or a set of concepts, than an architecture. The guiding prinicpal of CQRS is simple: separate handling of commands from the handling of queries.

"every method should either be a command that performs an action, or a query that returns data to the caller, but not both. In other words, asking a question should not change the answer" - Bertrand Meyer

- Commands return void (ack/nack), queries return data



### Event Sourcing
"..there are times when we don't just want to see where we are, we also want to know how we got there" - 
[Martin Fowler](http://martinfowler.com/eeaDev/EventSourcing.html)

There are two ways to persist changes
 * the classic way, by storing a snapshot of current state
 * store the change itself

 SIGNALR
 http://www.kevgriffin.com/maintaining-signalr-connectionids-across-page-instances/
 http://riba-escapades.blogspot.co.uk/2012/05/signalr-wire-up-connectionid-with-user.html
 http://stackoverflow.com/questions/11522090/signalr-how-is-a-duplicate-connection-id-handled
 http://stackoverflow.com/questions/9991035/securing-signalr-calls