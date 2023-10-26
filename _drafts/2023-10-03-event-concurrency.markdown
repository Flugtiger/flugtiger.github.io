---
layout: post
title:  "Consistent Event Driven Systems"
category: software architecture
---

* types of events
  * fact
  * delta
* issues that can occur
  * lost events
  * lost updates
  * failed business transactions
* event processing modes
  * at least once
  * at most once
  * exactly once
* CDC + outbox pattern
* FIFO vs unordered
  * optimistic locking
* the Saga pattern

When your goal is a consistent event driven system, there is only one rule that is non-negotiable:

> Events must not get lost!

Why?
Because whenever an event gets lost in the system, all downstream entities will become out of sync with the origin of the event without even noticing.
To fix this, a downstream system first needs to detect that it is out of sync which often is not straight-forward.
Then, all events that might have been lost need to be regenerated/replayed, which is also very inconvenient (especially when events are sent by a different team) and probably not what you want as a regular process in your system.

There are more rules, that might seem to be non-negotiable but actually aren't. Like:

> Events must be processed exactly once.

This seems to be true from our experiences in the real world.
A bank transaction must not be executed twice, right?
But there is a slight difference between receiving/processing an event and executing the side-effects of that event.
Preventing the former from occurring more than once is very hard, whereas preventing the latter to occur more than once is vastly more easy.

To prevent the processing of an event from occurring multiple times, everything that is included in the processing needs to be part of a transaction.
When there is an error while the event is processed, the complete transaction needs to be rolled-back in order for the event to be made available for another try (it must not get lost).
Since you often write to databases and published follow-up events while processing an event, this transaction often needs to span multiple different technology stacks (DB, events, etc.) which is very hard to achieve.

Preventing the side-effects from happing more than once is easy on the other hand.
In case of a bank transfer for example, you can make a record of all transfers that have already been applied to the bank account (by their ID).
When an event gets processed a second time, for example because some later processing step has failed the first time, you can skip applying the transfer a second time because the ID of the transfer is already present in the bank account.
The processing can then proceed with the remaining steps.
This behavior is widely known as idempotence.
In general, this means that regardless of how often an event gets processed (at least once), the result (state/side effects) will always stay the same.

Another rule, that is negotiable is the following:

> Events must strictly be processed in the order of occurrence.

