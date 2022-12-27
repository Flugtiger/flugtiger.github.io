---
layout: post
title:  "[DRAFT] Software: Principles vs. Pragmatism?"
category: software architecture
---

When studying computer science you'll sooner or later come into contact with different principles of software development.
E.g. the SOLID principles or the DRY principle.
But only few developers seem to take principles important.
Some even reject principles, since "a good developer has to be pragmatic" and "every principle has exemptions".
So are principles only good for scientific examples?
Do they help us at all in our daily work as software developers and architects?
What even are "principles"?

## The word "principle" explained

The word "principle" has different meanings depending on the context in which it is used.
In philosophy and mathematics it denotes a fundamental law that is the basis for other derived rules and laws.
A moral principle is a belief that induces a specific behavior.
But when it comes to software development we are in another context: complex systems.

A complex system is a system that has uncountable many parameters that all influence the behavior or the outcome of this system.
Software development projects are most often complex.
The outcome of such a project depends on many different parameters like budget, goals, requirements, luck and not to forget all the many decisions made by the project members (How many decisions does a software developer make on an average day? Many!).
Another example of a complex system is the weather.
How the weather at a specific place is developing depends on parameters like air pressure, temperature, moisture, sun intensity, clouds etc. not only at that specific place but all over the atmosphere.
In general a complex system has too many parameters to be able to calculate an exact prediction of the behavior of such a system.

Nevertheless, we would like to predict the behavior of those systems.
When it comes to weather, we need those predictions to make better decisions for example in agriculture or transportation (pilots like to know in advance if a storm is coming).
If we can influence the system, like in software development, we'd like to know how our decisions influence the end result.

This is where principles come into play: A Principle in context of complex systems is a logical correlation that connects one or multiple specific parameters to a specific outcome.
So we can use the principle to make a prediction based on those parameters.
In other words: A principle in a complex system is also a kind of law or rule in the way the system works.

The reason why we do not call it a law or rule in this context is, that because of the many different parameters that the outcome depends on, we cannot definitely quantify the influence of the principle.
There are always other parameters that are not part of the principle, that also influence the outcome.
But if we could simplify the system to only contain the parameters that are included in a specific principle, we would get a rule that most often even has it's foundation in a natural law.
This is true regardless of the kind of complex system that we are talking about (weather, software projects, the economy, ...).

An example:
In the weather system, one principle would be that the more sunlight reaches the ground, the higher the air temperature will be.
Using this principle, we can not say exactly how high the temperature will be, because it depends on many more factors (wind, moisture, slope, ...) but if we would eliminate all those factors, we would be left with the physical laws of thermal radiation.
Now we can exactly calculate how much a specific object is getting warmer when we expose it to a specific amount of radiation.
The principle of the complex system has a foundation in a natural law.
If we know these underlying rules, the statement "the more sunlight, the higher the air temperature" seems to be quite obvious.
But sometimes we don't know the underlying laws (or don't care about them).

When a principle is based upon a natural law, it inherits some of its properties, for example its applicability:
The principle will work for as long as the underlying law is applicable in the situation at hand.
Since natural laws often apply very generally, principles based upon natural laws do too.
This leads to principles that can be transferred between different complex systems.

## A software principle analyzed

Let's analyze one of the SOLID principles as an example: The single responsibility principle.

> A class should have only one reason to change

First we need to take a look at the parameters of the system that are included in the principle.
In this case it is obviously the "size" of a component of the software.
More specifically: the number of responsibilities that a component has or in other words: the number of features that a specific class implements.

Now that we know the parameter, what does the principle say about the outcome, that we can expect from the system if we temper with the parameter?
Nothing!

It only says, that the parameter should be kept at a specific value (one responsibility per class).
What happens if we do not follow this recommendation is not something the author wanted to let us know.
So let's make an educated guess:
the maintainability of the software will decrease, if we increase the parameter.
Adding this information, we can make a slightly clearer formulation of the principle:

> The more responsibilities a component has, the worse the maintainability of the software becomes.

In comparison to the first version, this version makes it a lot clearer to reason about the principle since it includes the predicted outcome (less maintainability).
On the other hand, it is missing the information of how exactly the parameter should be in order to build "good software".

Let's take it a step further.
If we eliminate all other parameters of the system that influence the outcome, do we get a law?
To be able to transform this principle into a law, we first have to formalize some of the terms of the principle.
First, let's say that a "component" in a software system is a part of the system that communicates with other components at the same level of the system only through well defined interfaces.
"Well defined" in turn, means that the interface can easily be understood by a human that reads the source code of the interface (how to do that is an entire different story).











The way the principles are formulated might be a reason, why many developers don't like to accept them as generally valid.
They sound too much like the opinion of a specific author.
