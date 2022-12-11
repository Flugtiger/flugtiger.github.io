---
layout: post
title:  "[DRAFT] Software: Principles vs. Pragmatism?"
category: software architecture
---

When studying computer science you'll sooner or later come into contact with different principles of software development.
E.g. the SOLID principles or the DRY principle.
But only few developers seem to take principles important.
Some even reject principles, since "a good developer has to be pragmatic" and "every principle has exemptions".
So are principles only good for scientific examples or do they help us in our daily work as software developers and architects?
What even are "principles"?

The word "principle" has different meanings depending on the context in which it is used.
In philosophy and science it denotes a fundamental law that is the basis for other derived rules and laws.
A moral principle is a belief that induces a specific behavior.
But when it comes to software development we are in another context: complex systems.

A complex system is a system that has uncountable many parameters that all influence the behavior or the outcome of this system.
A common example of such a system is the weather system on our planet.
How the weather at a specific place is developing depends on many different parameters like air pressure, temperature, moisture, sun intensity, clouds etc.
So to predict the weather (the behavior of the complex system), one needs to know all those parameters.
But it does not suffice to know those parameters at one single place but one needs to know all those parameters at many (sufficiently dense) points on the surface of our earth.
And it gets even worse: One would further need to know those parameters also at different heights of our atmosphere.
That are far too many parameters to be ever measured by humans.
Even when we would be able to measure them, we do not have nearly enough computational resources to put them into a weather model to calculate a prediction.
That's the reason we do not have fully accurate weather forecasts: weather is complex.

Software development projects are also complex.
The outcome of such a project depends on many different parameters like budget, goals, requirements, luck and not to forget all the many decisions made by the project members (how many decisions does a software developer make on an average day?).

Back to principles: A Principle in context of complex systems is a logical correlation that connects one or multiple specific parameter to a specific outcome.
In other words: A principle in a complex system is also a kind of law or rule in the way the system works.

The reason why we do not call it a law or rule in this context is, that because of the many different parameters that the outcome depends on, we cannot definitely quantify the influence of the principle.
There are always other parameters that are not part of the principle, that also influence the outcome.
But if we could simplify the system to only contain the parameters that are included in a specific principles, we would get a rule that most often even has it's foundation a a natural law.


Simply because a complex system has many parameters does not mean that there are no rules and laws