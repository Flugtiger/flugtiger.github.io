Happy to be a bottleneck

Let me tell you a story of two teams in software development.
Let's call them team "Red" and team "Blue" and they are both part of a company called "eRetail".
Team Red is responsible for something called the "service plattform" at eRetail.
It's meant to be the central place, where B2B services are ordered by partners of eRetail.
Team Blue is responsible for one such service, namely a marketing campaign service that enables partners to create and maintain discount campaigns.

For delivering a service, team Red provides an API to all service providers to configure a booking form.
This form is meant to collect all the necessary data from a partner to enable a service provider to deliver the service.
Team Red then generates a GUI based on the configuration and shows it to the partner.
The partner enters their data, which is then sent to Team Red.
Team Red saves the data as an "order" and sends it to the service provider (team Blue).
When the partner wants to change something, he needs to edit his order at team Red and team Red then notifies team Blue about the update.

It doesn't take long until team Blue is dissatisfied with this architecture.
They find out, that the API/form provided by team Red is not sufficient to describe their service completely.
So team Red needs to extend their API to fit the variations the team Blue needs for their service.
The problem is that team Red is already busy with the implementation of requirements regarding booking and billing of the orders.
Therefor it takes a long time until team Red changes their API to fulfill the needs of team B.
During this time, team B cannot deliver its service in the extend that the partner wants.
This situation repeats every time team B wants to deliver a feature to the partners of eRetail that doesn't fit into the service abstraction of team Red.
This really disturbs the capability of team B to deliver.
And not only that.
Other teams, that also want to provide a service to partners of eRetailer face similiar problems.

Team Red has effectively become the bottleneck for the whole B2B business of eRetailer.
This leads to slower delivery of new features and therefore lost revenue.

How did this happen?

The original intention for creating the "service plattform" in the first place was, to have a uniform look and feel of all services.
Also there are some crosscutting requirements for the booking and billing of services with which the service provider shouldn't be concerned.
Third, it seemed to be beneficial, that the service providers don't need to implement the booking GUI by themselves.

These goals are all legit, but how it was tried to reach them in this example, isn't.
At the root of this lies a big misconception: services cannot be treated like products!
A product is something that's thoroughly standardised.
It is often replicated in big counts, put onto a shelf and the customer can make exactly one decision: buy it or not.
A service on the other hand is always tailored to the needs of the individual customer.
How a service is exactly delivered is often up for negotiation between the service provider and the customer.
Sometimes the customer even decides on-the-fly how to use a service.
This makes it really hard to "order" a service by simply filling out a form.
This is especially true for Web services like in this example.
There already is an abstraction of a Web service that is widely accepted: the HTTP protocol.
The web service provider is expected to deliver features based on this abstraction.
So if you put another abstraction in between the service provider and the HTTP protocol (like team Red does),
you either need to tailer this abstraction to the provider (all of them) or make it as wide as HTTP itself if you don't want to hinder the ability of the provider to deliver.
Tailoring the abstraction is not an option, since this would effectively make team Red implement all the services, which would blow their capacity.
Making the abstraction as wide as HTTP itself is a valid option, but since HTTP is a standard, there's no need to develop such an abstraction anew.
Instead, you can use API Gatways like Kong or API Specs like OpenAPI to abstract web services.

But how to reach the goals (uniform look&feel, crosscutting concerns, reusing of UI components), when you are not allowed to introduce an abstraction over all the services?
Well, there are already solutions to these problems on the technological layers below the application layer.
A uniform look&feel can be reached by providing a styling framework and a style guide to the service providers.
The crosscutting concerns can still be implemented by team Red at a central point.
They only need to provide APIs for these concrete crosscutting concerns (like billing) without requiring an abstraction of the complete services.
Reusability of code and GUI can be fostered by maintaining a library of such things that is shared between the service providers.
In that way, the service providers a free to deliver value quickly to the customers while team Red can concentrate on excelling in their own domain (booking and billing).
