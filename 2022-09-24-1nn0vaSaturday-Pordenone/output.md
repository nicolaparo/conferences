Sabato 24 settembre 2022
Sabato 24 settembre 2022

Nicola Paro

Nicola Paro

Cloud Solutions Engineer in beanTech

Linkedin: https://www.linkedin.com/in/nicolaparo/

Github: https://github.com/nicolaparo

Email: nicola.paro@gmail.com

2020 - 2022

Grazie ai nostri sponsor

C’era una volta Itemfactory S.R.L. …

• Azienda specializzata nella

produzione di oggetti
• Linee di produzione già

connesse ad un HMI

• I dati arrivano già in Cloud

• Vuole un applicativo MES per
la gestione degli ordini di
produzione

• Lo vuole Desktop, Mobile e Web
• Vuole che si aggiorni in tempo

reale

• Vuole che costi poco

HMI

(facciamo finta che lo sia)

The Recipe

Cross
Platform

Hosting

UI
Framework

Data
Storage

Data
Movement
+
Data
Access

Realtime
Messaging
System

Code Repo
+
CI/CD

Progressive
Web App

Azure
Static
WebApp

Blazor

Azure
Storage
Account

Free

Free Tier

Free

Pay per Use

Azure
Functions

Azure Web
PubSub

GitHub

Consumption
Plan

Free Tier

Free

The Architecture Schema

Edge Software

Service Bus

SBS

Az Function

Save

Storage

Az Function

Events

SBS

Read

WS

Web PubSub

REST

SWA

CI/CD

GitHub

Cos’è Blazor

Blazor è un framework per la creazione di interfacce web
interattive client-side utilizzando .NET.

Cosa possiamo fare?
• Creare interface web utilizzando C# invece che JS*
• Condividere logica tra server e client
• Utilizzare librerie .NET anche lato client**

* Non è vero, JS rimane per molte cose l’unica strada percorribile

** Con alcune restrizioni.

Blazor Server vs WebAssembly

Blazor Server

Blazor WebAssembly (WASM)

https:**.**

https:**.**

ASP.NET Core

Razor Components

SignalR

DOM

.NET

Blazor

Razor Components

.NET

WebAssembly

DOM

Cos’è una PWA?

È un applicativo web installabile.

Deve soddisfare tutti i seguenti requisiti:

• Contenere un manifest.json.
• Servito in HTTPS
• Contenere un’icona per la Shortcut
• Deve registrare un service worker

richiesto da tutti i browser Chromium-based

Come posso creare una PWA con Blazor?

Opzioni:
1. Creo un’app AspNetCore e aggiungo gli assets per renderlo

una PWA

2. dotnet new blazorwasm -o AppName –-pwa

3. Così:

Razor Components Lifecycle

SetParametersAsync()

OnInitializedAsync()

OnParametersSetAsync()

OnAfterRenderAsync(true)

ShouldRender()

OnAfterRenderAsync(false)

Special Guest

DisposeAsync()

Dispose() e DisposeAsync()
sono invocati all’unload
del componente se il
componente implementa
IDisposable o
IAsyncDisposable

Blazor Page Structure

Azure Web PubSub

Servizio gestito che supporta WebSockets serverless.
Pensato per applicazioni che richiedono aggiornamenti
in tempo reale

Aggiornamenti
ad alta
frequenza

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

Notifiche
Push

Real-time
broadcasting

IoT e
dispositivi
connessi

Automazione

SignalR vs Azure Web PubSub

• Stai già usando SignalR
• Esiste un client SignalR nel

• Hai bisogno solo di WebSocket
• Subprotocollo custom over

linguaggio scelto

• Clients supportati da MS:

• Hai necessità di più

protocolli di trasporto

• WebSocket
• Server sent events
• Long polling

WebSocket

• MQTT over WebSocket
• AMQP over WebSocket

• È sufficiente

un’infrastruttura «lite» per
la tua applicazione

* Azure Web PubSub è solo PaaS

Azure Web PubSub Pricing

DEMO – Azure Web PubSub

Sending Data with Azure Web PubSub

• ServiceClient C#

Azure.Messaging.WebPubSub

• AzFunction Bindings

Microsoft.Azure.WebJobs.Extensions.WebPubSub

Get AccessUri for Azure Web PubSub

• Tramite il portale Azure

• ServiceClient C#

• AzFunction Bindings

DEMO – Notifiche in pagina

Cos’è Azure Static WebApp

È un servizio che consente di creare applicazioni Web
statiche.

La pubblicazione dei nuovi contenuti avviene tramite un
sistema di CI/CD.

Si integra nativamente con GitHub e con Azure DevOps.

Az Blob Static Website vs Az Static WebApp

•
•
•
•
•

 SSL
 CI/CD non gestito
 No Multiregion
 Custom Domain
 No HTTPS con Custom

Domains

•
•
•
•
•
•

 SSL
 CI/CD integrate
 Globalmente distribuito
 Custom Domain
 HTTPS con Custom Domain
 API proxy integrato

Azure Static WebApp - Api

Free Tier
• Azure Functions

Standard Tier
• Azure Functions
• Azure Api Management
• Azure AppService
• Azure Container Apps

Azure Static WebApp Pricing

DEMO – Azure Static WebApp

Creare
una
Azure
Static
WebApp

Creare
una
Azure
Static
WebApp

Creare una Azure Static WebApp

https:**victorious-tree-017109303.1.azurestaticapps.net

Q & A

Nicola Paro

Cloud Solutions Engineer in beanTech

Linkedin: https://www.linkedin.com/in/nicolaparo/

Github: https://github.com/nicolaparo

Email: nicola.paro@gmail.com

2020 - 2022

Sabato 24 settembre 2022

Marco Parenzan
