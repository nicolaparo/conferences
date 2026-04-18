TOPIC

Da WinForm al
Web:
La transizione è
possibile con
Blazor Hybrid!
Nicola Paro

1

Thanks to our partners

2

A Real Life Story

Maybe

3

A Real Life Story

Applicativo per la
gestione degli ordini

Hanno più client
connessi al database

Applicativo WinForm
.NET Framework 3.5

4

A Real Life Story

Problematiche dell’implementazione attuale

Legacy
Codebase

Sincronizzazione

Problemi di
Sicurezza

Manutenzione e
Distribuzione

Scalabilità

Tecnologia
Obsoleta

5

A Real Life Story

Desiderata

Scalabilità

Maggior
Sicurezza

Accesso anche
da Remoto

UI Moderna

Aggiornabilità

Compatibilità
con Dispositivi
Diversi

6

A Real Life Story

Desiderata

https://northwind.boh

Blazor Hybrid on WinForm

7

Cos’è Blazor?

Blazor è un framework per la creazione di interfacce web
client-side utilizzando .NET.

Cosa possiamo fare?
Creare interfacce web utilizzando C# invece che JS*
Condividere logica tra server e client
Utilizzare librerie .NET anche lato client**

* Non è vero, JS rimane per molte cose l’unica strada percorribile

** Con alcune restrizioni.

8

Blazor Interactive: Server vs WebAssembly

Interactive Server

Interactive WebAssembly

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

9

Blazor Static Server vs Interactive

Static Server

Interactive

Form POST

Plain HTML

https://...

DOM

Interactive Server

Interactive WebAssembly

https://...

https://...

ASP.NET Core
Razor Components

.NET

SignalR

DOM

Blazor

Razor Components

.NET

WebAssembly

DOM

ASP.NET Core

Razor Components

.NET

10

Struttura di un Razor Component / Blazor Page

Route

Possibilità di iniettare servizi

Possibilità di implementare
interfacce e derivare classi

Contenuto da renderizzare

Logica per la gestione della vita
del componente

11

Razor Component Lifecycle

SetParametersAsync()

OnInitializedAsync()

OnParametersSetAsync()

OnAfterRenderAsync(true)

ShouldRender()

OnAfterRenderAsync(false)

Special Guest

DisposeAsync()

Dispose() e
DisposeAsync() sono
invocati all’unload del
componente se il
componente
implementa
IDisposable o
IAsyncDisposable

12

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

13

Blazor Hybrid On WinForms

Differenze con le altre modalità di utilizzo di Blazor

Eseguito nativamente nel dispositivo client.

Può accedere a tutte le funzionalità del dispositivo
utilizzando .NET

Renderizzato in una WebView2 “embeddata” all’interno
dell’applicazione tramite un canale in interoperabilità.

https://github.com/dotnet/maui/blob/main/src/BlazorWebView/src/SharedSource/WebView2WebViewManager.cs#L201

14

Blazor Hybrid On WinForms

Che cos’è WebView2 ?

Microsoft Edge WebView2 è un runtime che fornisce
funzionalità web-based ad applicativi desktop.

Utilizza Microsoft Edge come rendering engine.

15

Blazor Hybrid On WinForms

Comunicazione tra .NET e WebView2

SendMessage()

.NET

WebView
2

WebMessageReceived()

sendMessage()

.addEventListener(
'message', e =>
callback(e.data))

UI

16

Blazor Hybrid On WinForms

Workloads

17

Blazor Hybrid On WinForms

Nuget per utilizzare Blazor Hybrid

18

.NET Migration Tool

19

Demo

Where can you Deliver a Blazor Hybrid app?

Windows Version

Win 7

Win 8

Win 8.1

Win 10

Win 11

April 2018 (1803)

.NET Version

WebView2

Blazor Hybrid

.NET6

.NET 6

.NET6, .NET7, .NET8

109

Manual Install

Latest

Latest

Blazor Hybrid on Winform Support

21

Where can you Deliver a Blazor Hybrid app?

22

Alcune considerazioni…

La strada verso il web è lunga e tortuosa

Librerie vecchie o non più supportate
Personalizzazioni a librerie di componenti implementate molti
anni fa

Ci sono molti modi per migrare verso il web: Blazor Hybrid
è una delle possibilità

23

Ci piace Blazor?

Blazor Developer Italiani è la prima
community italiana dedicata allo
sviluppo di applicazioni con Blazor

24

About Me

Nicola Paro

@nicola_paro

nicolaparo

nicolaparo

#CodeGen2024

@cloudgen_verona

Thank you

Any questions?

nicolaparo

@nicola_paro

nicolaparo
