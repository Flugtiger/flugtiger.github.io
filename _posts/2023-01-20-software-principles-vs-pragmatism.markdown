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
In philosophy and mathematics it denotes a fundamental law that cannot be derived from other laws.
A moral principle is a belief that induces a specific behavior.
But when it comes to software development we are in another context: complex systems.

A complex system is a system that has uncountable many parameters that all influence the behavior or the outcome of this system.
Software development projects are most often complex.
The outcome of such a project depends on many different parameters like budget, goals, requirements, luck and all the many decisions made by the project members (How many decisions does a software developer make on an average day? Many!).
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
Using this principle, we can not say exactly how high the temperature will raise, because it depends on many more factors (wind, moisture, slope, ...) but if we would eliminate all those factors, we would be left with the physical laws of thermal radiation.
Using this law, we can exactly calculate how much a specific object is getting warmer when we expose it to a specific amount of radiation.
As you see, the principle of the complex system has a foundation in a natural law.
If we know these underlying rules, the statement "the more sunlight, the higher the air temperature" seems to be quite obvious.
But sometimes we don't know the underlying laws (yet).
This seems to be mostly true for software development.
In this case we cannot start from a natural law and derive the corresponding principle.
Instead we have to carefully monitor how the system behaves in many different situation and derive a principle thereof.
This might be the reason why many people see principles as something very vague and brittle.
But once we have found a principle (or what we think might be one) by monitoring the system, we can then try to deduce the law that the principle is based upon.

When a principle is based upon a natural law, it inherits some of its properties, for example its applicability.
So if we found the law, we can reason much better about the principle.
We can predict when the principle will be in effect and how it relates to other laws and principles.
Also, when the same law also applies to other systems (which most natural laws do), the principle will as well.
In that way we can transfer principles between multiple kinds of systems with confidence.

## A software principle analyzed

Let's analyze one of the SOLID principles as an example: The single responsibility principle.

> A class should have only one reason to change

First we need to take a look at the parameters of the system that are included in the principle.
In this case it is the "size" of a component of the software.
More specifically: the number of responsibilities that a component has or in other words: the number of features that a specific class implements.

Now that we know the parameter, what does the principle say about the outcome, that we can expect from the system if we temper with the parameter?
Nothing!

It only says, that the parameter should be kept at a specific value (one responsibility per class).
What happens if we do not follow this recommendation is not part of the formulation of the principle.
So let's make an educated guess:
the maintainability of the software will decrease, if we increase the parameter.
Adding this information, we can make a much clearer formulation of the principle:

> The more responsibilities a component has, the worse the maintainability of the component becomes.

In comparison to the first version, this version makes it easier to reason about the principle since it includes the predicted outcome (less maintainability).
On the other hand, it is missing the information of how exactly the parameter should be in order to build "good software" (only one responsibility per class).

The next step of the analysis would be to try to find the underlying law (if there is one).
This will be part of the next article on that topic, so stay tuned.

## TL; DR

Principle in software development are principle in complex systems.
They describe the behavior of such a system by using only some of its input and output parameters.
If we disregard all other parameters that also effect the outcome of the system, we might find a natural law and be able to reason much better about the principle.
The way principles in software development are often formulated (without giving the outcome and without saying what law it is based on) might be a reason, why many developers don't like to accept principles as something that is broadly applicable and very helpful when making decisions.
