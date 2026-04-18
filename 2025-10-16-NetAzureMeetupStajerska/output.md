.NET & AZURE
MEETUP
ŠTAJERSKA

THURSDAY, OCTOBER 16 · 18:30 – 21 CEST

TEHNOLOŠKI PARK PTUJ
Vičava 1, 2250 Ptuj

Monitor your IoT Asset
with Azure Free Services

NICOLA PARO

Special thanks to

A Real Life Story…

My IoT device works, but not really that well…

If only I would have a monitoring system, I could understand when things are not working
properly…

I’m low on budget, so I need to create a cheap infrastructure that «does the job», even better if I
don’t have to pull out any money…

IoT is not always «RealTime»

Hot Data

Warm Data

Cold Data

Data that must be
immediately notified
or aggregates of data

Sampled data,
accumulated locally
and sent via file
upload every minute

Contextual data, MES,
ERP, Registries in
general

Hot
Streaming

Real-time streaming
of the Warm Data,
enabled and disabled
«on demand»

First Level of
monitoring

Second level of
monitoring

It is not monitoring

Third level of
monitoring

Monitoring Platform Overview

?

Event Storage

?

Web Socket

?

API

?

UI

?

Receiver

Collector Module

On Edge

On Cloud

Azure Free Services

https://azure.microsoft.com/en-us/pricing/free-services

Monitoring Platform – Event Storage

It must persist the events in order to query them later.

It must allow analytics in a simple way.

Cosmos DB

Managed Database either relationation and NoSQL

Globally distributed, highly responsive and always online

You can use the API you prefer

NoSQL

MongoDB

Apache
Cassandra

Apache
Gremlin

Table

PostgreSQL

Free Tier: Max throughput 1000 RU/s + 25 GB storage, available to “provisioned throughput
accounts” (must opt-in when creating the account)

Azure SQL

Fully managed relational database

Built over the same engine of SQL Server

Free Tier available with 100,000 seconds * vCore and 32GB of storage limit per month forever
◦ You can choose to auto-pause it when the limits are reached
◦ Or else you can continue to use it and pay only for the extra usage

Azure SQL

Fully managed relational database

Built over the same engine of SQL Server

Free Tier available with 100,000 seconds * vCore and 32GB of storage limit per month forever
◦ You can choose to auto-pause it when the limits are reached
◦ Or else you can continue to use it and pay only for the extra usage

Monitoring Platform – Event Storage

Cosmos or SQL ?

Monitoring Platform – Event Storage

Cosmos or SQL ?

Monitoring Platform – Web Socket

Must notify the events to the frontend to ensure a quick human intervention

Azure SignalR & Web PubSub

Thought for applications that require real-time data

High
frequency
updates

Live
dashboards e
monitoring

Cross-
platform live
chat

Real-time
location on
map

Real-time
targeted ads

Collaborative
apps

Push
notifications

Real-time
broadcasting

IoT

Automation

Azure SignalR vs Web PubSub

When you are already using SignalR

WebSockets are good enough for your use case

There is an available SignalR client in your
language
◦ MS officially supported Clients:

You need to transport another custom protocol
over WebSocket
◦ MQTT over WebSocket
◦ AMQP over WebSocket

A «lite» infrastructure is enough for your
application

You really need multiple transport protocols
◦ WebSocket
◦ Server sent events
◦ Long polling

Inside Azure Web PubSub

Group

Group

Group

Group

Hub

Hub

Web Pub Sub

Sending Data with Azure Web PubSub

ServiceClient C#
Azure.Messaging.WebPubSub

AzFunction Bindings
Microsoft.Azure.WebJobs.Extensions.WebPubSub

Azure SignalR & Web PubSub Pricing

Monitoring Platform – Web Socket

Web Pub Sub o SignalR?

Monitoring Platform – Web Socket

Web Pub Sub o SignalR?

Monitoring Platform - Receiver

Must receive “occasional” events from the IoT device

Must store these events in the Event Storage

Must notify via WebSocket each event

Azure Functions Free grant

Only in Consumption Plan on Pay As You Go subscriptions

Up to 400.000 GBs and 1 million invocations

Or I can host them in a free AppServicePlan

Despite the free grant, Azure Functions always require a Storage Account in order to work
properly (it is cheap, but is not given for free)

Monitoring Platform - Receiver

Azure Functions o Azure Functions ?

Monitoring Platform - Receiver

Azure Functions o Azure Functions ?

Monitoring Platform - API

Must read the events from the Event Storage

Must perform small aggregates

Must expose the contents via REST to make them available for the UI

Azure App Service Web Apps

Managed services to host web apps and REST APIs

Wide choice of
supported
programming
languages

Supports Docker
containers

Managed updates
and security
patches

Authentication
support without
modifying
application code

Built-in CORS
management

Azure App Service Plan Free Tier

I can have only a single App Service Plan Free instance per subscription

Azure Container Apps

Serverless platform for the
execution of containerized
applications

Basically, Kubernetes pods
as PaaS: you pay for what
you use.

Azure Container Apps Free Grant

Each month you get for free:
◦ Up to 180,000 vCPU-seconds
◦ 360,000 GiB-seconds
◦ 2 million requests

Other tricks to not to pay them pay them less
◦ Scale the replicas down to 0
◦ When there are no incoming HTTP requests and the replica count is at its minimum, you are going to

pay a reduced price

Monitoring Platform - API

Container Apps o Web Apps?

Monitoring Platform - API

Container Apps o Web Apps?

Monitoring Platform - UI

App for exploring the historical data and for receiving the IoT notifications

It doesn’t really need a full backend, as it can consume the APIs we just implemented.

Azure Static WebApp

Service that allows the hosting of static web applications.

Static content
publishing with
HTML, CSS, and
JavaScript

Globally
distributed static
content

API support

CI/CD with GitHub
and Azure DevOps

Free SSL certificate

Staging
environment
management

Azure Blob Static Website
vs Azure Static WebApp

•

•

•

•

•

 SSL

 CI/CD do it yourself

 No Multiregion

 Custom Domain

 No HTTPS with Custom

Domains

 SSL

 CI/CD integrate

 Globally distributed

 Custom Domain

 HTTPS with Custom Domain

Azure Static WebApp… But the backend?

Managed

Azure Static WebApp… But the backend?

Managed

Data Api Builder Endpoint

Data API Builder?

To use DAB locally

dotnet tool install Microsoft.DataApiBuilder

Azure Static WebApp Pricing

Required Tools to work with this
technology

Static Web App Command line tool (swa)

npm install -g @azure/static-web-apps-cli

Wasm tools to output Blazor wasm

dotnet workload install -g wasm-tools-net6

https://azure.github.io/static-web-apps-cli/docs/use/install/

Monitoring Platform - UI

Static Web Apps or Static Web Apps

Monitoring Platform - UI

Static Web Apps or Static Web Apps

Monitoring Platform Overview

Event Storage

API

Collector Module

Receiver

Web Socket

UI

On Edge

On Cloud

Monitoring Platform Overview

Event Storage

API

RCON

Minecraft

Collector Module

Receiver

Web Socket

UI

On Edge

On Cloud

Demo

Let’s get in touch!

Nicola Paro
Solution Architect | Microsoft MVP

linkedin.com/in/nicolaparo

github.com/nicolaparo

WE LIKE CI/CD

Continuous Improvement – Continuous Discussions

Share your feedback, opinions, suggestions with us!

WE ARE ON DISCORD!

https://discord.gg/K6F7pdP4xq

GREMO NA PIVO?

Hvala!
