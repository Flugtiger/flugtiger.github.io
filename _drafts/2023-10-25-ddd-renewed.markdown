---
layout: post
title:  "DDD renewed"
category: tech
---

* strategic DDD -> still very important
  * splitting teams -> team topologies
  * make or buy
  * prioritizing teams
* tactical DDD
  * use cases
    * -> should still reflect business needs / intends, no CRUD! (smart UI -> dumb API)
  * document DBs -> aggregates come naturally
  * domain model: entities and value objects
    * no one builds a model out of a document
    * instead: somehow replaced with functional programming
      * one function for validation of the request
      * one function for execution of the use case
  * dependencies between aggregates (even of different teams) -> events
  * events -> outbox pattern
    * pro: transactional safety
    * con: business intend gets lost (event types: CUD)
    * pattern matching to retrieve the business action that was done -> added complexity
    * instead: write the last business action into the document
  * events -> sent from application after updating the document
    * pro: business intend is still known
    * updating the document must be idempotent
    * if the event could not be sent, the request is retried and the document is updated again