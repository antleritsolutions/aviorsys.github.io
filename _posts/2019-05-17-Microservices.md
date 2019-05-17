---
layout: post
title: "Microservices"
tagline: "An introduction to Microservices"
categories: Technology
author: "Ruvini Ranasinghe"
---

# What are microservices?

Microservices , is an architectural Pattern that structures an application as a collection of
small autonomous interconnected services, modeled around a business domain.

This is in contrast to a traditional, "monolithic" application which is all developed all in one
piece

Each service in Microservices are self-contained and implements a single business
capability.

## Monolithic vs Microservices

![Microservices](https://github.com/aviorsys/aviorsys.github.io/raw/master/images/microservices-vs.jpg)

## Monolithic Architecture

Monolithic means composed all in one piece. The Monolithic application describes a single-tiered software application in which different components combined into a single
program from a single platform

## Challenges of monolithic Architecture

- Inflexible - Monolithic architecture is not flexible. We can’t use different
technologies. The technology stack is decided at the start and followed throughout

- Unreliable – Even if one feature of the system does not work, then the entire
application might go down

- Unscalable - difficult to scale up once they get larger. Each time the application
needs to be updated, the complete system has to be rebuilt

- Block Continuous deployment: Continuous deployment is extremely difficult. Large
monolithic applications are actually an obstacle to frequent deployments. In order to
update one component, we have to redeploy the entire application.

- Difficult to building complex applications: It's difficult to build a complex
application because of the limitations in terms of technologies.

## Microservices Architecture

- Clients – Different users from various devices send requests.

- Identity Providers – Authenticates user or clients identities and issues security
tokens

- API Gateway – Handles client requests.

- Static Content – Houses all the content of the system.

- Management – Balances services on nodes and identifies failures.

- Service Discovery – A guide to find the route of communication between microservices.

- Content Delivery Networks – Distributed network of proxy servers and their data
centers.

- Remote Service – Enables the remote access information that resides on a network
of IT device Microservices Features.

## Microservices Features

- Decoupling – Different components in a microservices architecture can be
changed, upgraded, or replaced independently without affecting the functioning of
other components. Similarly, the teams responsible for different microservices are
enabled to act independently from each other.

- Componentization – Microservices are treated as independent components that can
be easily replaced and upgraded

- Business Capabilities – Microservices are very simple and focus on a single
capability

- Autonomy – Developers and teams can work k
k
k
- Continuous Delivery – Allows frequent releases of software, through systematic
automation of software creation, testing, and approval

- Responsibility – Microservices do not focus on applications as projects. Instead, they
treat applications as products for which they are responsible

- Decentralized Governance – Microservices architectures are distributed systems
with decentralized data management. They don’t rely on a unifying schema in a
central database. Each microservice has its own view on data models. Microservices
are also decentralized in the way they are developed, deployed, managed, and
operated.

## Pros of Microservices

- Independent Development – each service is developed and deployed
independently from all the other services. This means an update to any one
component does not require the entire application to come down in order to deploy
that update, only the component in question. This allows for improved uptime and
safer deployment processes.

- Independent Deployment – Based on their services, they can be individually
deployed in any application

- Fault Isolation – Even if one service of the application does not work, the system still
continues to function

- Technology Heterogeneity – With a system composed of multiple, collaborating
services, we can decide to use different technologies inside each one. This allows us
to pick the right tool for each job, rather than having to select a more standardized,
one-size-fits-all approach that often ends up being the lowest common
denominator.

- Granular Scaling – Individual components can scale as per need, there is no need
to scale all components together
Cons of Microservices

- Increases delay due to remote calls

- Increases troubleshooting challenges

- Tough to track data across various boundaries

- Increased efforts for configuration and other operations

- Difficult to code between services

## References

<https://microservices.io/>

<https://www.edurekaco/blog/what-is-microservices/>

<https://articles.microservices.com/monolithic-vs-microservices-architecture-5c4848858f59>

<https://www.tiempodev.com/corporateblog/monolithic-vs-microservices>

<https://mediumcom/koderlabs/introduction-to-monolithic-architecture-and-microservices-architecture-b211a5955c3>

<https://dzone.com/articles/microservices-1-introduction-monolithic-vs-microse>

<https://docs.aws.amazon.com/whitepapers/latest/microservices-on-aws/characteristics-of-microservices.html>

<https://www.spkaa.com/blog/top-4-pros-cons-microservices-architecture/>