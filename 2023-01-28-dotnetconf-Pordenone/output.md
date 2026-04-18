Frontend per servizi Backend con Blazor e .NET7

Sponsors

With the support of:

About me

Nicola Paro
Cloud Solutions Engineer @ beanTech

Linkedin: https://www.linkedin.com/in/nicolaparo/

Github: https://github.com/nicolaparo

Email: nicola.paro@gmail.com

A Real Life Story
(Maybe)

C’era una volta Itemfactory S.R.L. …

• Azienda specializzata nella produzione di oggetti

• Ha sviluppato un sistema di invio di notifiche (NotificationService) per informare il cliente

quando l’ordine è in lavorazione e per comunicare eventuali news.

• Il NotificationService è controllabile solo via Rest o tramite interrogazioni al database

• Non molto User Friendly

• Vuole una UI per l’assistenza clienti per poter accedere ai dati del NotificationService

• Vuole che costi poco

C’era una volta Itemfactory S.R.L. …

Notification Service

ItemFactory MES
Application

Api

Worker

Email

Sms

Telegram

DB

C’era una volta Itemfactory S.R.L. …

UI Blazor
Notification Service

ItemFactory MES
Application

Api

Worker

Email

Sms

Telegram

DB

Blazor

Cos’è Blazor?

Blazor è un framework per la creazione di interfacce web interattive client-side utilizzando .NET.

Cosa possiamo fare?

• Creare interfacce web utilizzando C# invece che JS*

• Condividere logica tra server e client

• Utilizzare librerie .NET anche lato client**

* Non è vero, JS rimane per molte cose l’unica strada percorribile

** Con alcune restrizioni.

Blazor Server vs WebAssembly

Blazor Server

Blazor WebAssembly

https://...

https://...

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

Struttura di un Razor Component / Blazor Page

Route

Possibilità di iniettare servizi

Possibilità di implementare
interfacce e derivare classi

Contenuto da renderizzare

Logica per la gestione della vita
del componente

Razor Component Lifecycle

SetParametersAsync()

OnInitializedAsync()

OnParametersSetAsync()

OnAfterRenderAsync(true)

ShouldRender()

OnAfterRenderAsync(false)

Special Guest

DisposeAsync()

Dispose() e DisposeAsync()
sono invocati all’unload del
componente se il
componente implementa
IDisposable o
IAsyncDisposable

Librerie di Componenti

DevExpress

Telerik

Blazorise

MudBlazor

€

€

€

FREE

FREE

And many more…

Fluent UI

Or Bring your Own!

Nuove Funzionalità per Blazor in .NET7

Controllo della navigazione

NavigationLock

History State

Location
Changing
Events

Parameter binding migliorato

@bind:get

@bind:set

@bind:after

Integrazione con altri framework frontend

Better Development Experience

Custom
Elements

Empty
Template

QuickGrid
[PREVIEW]

Nuove Funzionalità per Blazor Webassembly e .NET 7

FULLY CUSTOMIZABLE
Loading
Progress

Dynamic Auth

MORE
Crypto
Algorythms

SIMD
Vectorization

Improved
Debugger

Faster AOT
Code

REAL
Multithreading
[ALPHA]

Demo

Demo

Receive the Notifications
on Telegram!

https://t.me/netconf2022_bot

SPOILER: What will be in .NET 8 for Blazor?

MVC

Razor Pages

Blazor Server

Blazor
WebAssembly

HTML

SPA

SPOILER: What will be in .NET 8 for Blazor?

MVC

Razor Pages

Blazor United

Blazor Server

Blazor
WebAssembly

HTML

Single Project

Hybrid
Rendering

SPA

Auto
Rendering
Strategy

Q & A

Thank You!

Contacts

Nicola Paro
Cloud Solutions Engineer @ beanTech

Linkedin: https://www.linkedin.com/in/nicolaparo/

Github: https://github.com/nicolaparo

Email: nicola.paro@gmail.com
