Una UI per domarli tutti

Alessio Iafrate – Nicola Paro

Un grazie agli sponsor

A Real Life Story

Questa è vera davvero eh!

A Real Life Story

Case History: Sauron Industries

A Real Life Story

Case History: Sauron Industries

A Real Life Story

Case History: Sauron Industries - Requisiti

• Applicazione Desktop con possibilità di accedere a funzionalità

mediante componenti COM (per le fornaci)

• Applicazione mobile per la gestione delle checklists (manutenzione)

• Applicazione web per l’inserimento degli ordini (disponibile anche dal campo

di battaglia*)

• UI consistente tra tutte le piattaforme

Sono uno sviluppatore
ASP.NET e posso far
girare la mia applicazione
ovunque senza cambiare
linguaggio

Blazor Hybrid

Razor Components in Blazor Hybrid

Differenze con le altre modalità di utilizzo di Blazor

• Eseguiti nativamente nel dispositivo client.

• Possono accedere a tutte le funzionalità del dispositivo utilizzando

.NET

• Renderizzati in una WebView “embeddata” all’interno
dell’applicazione tramite un canale in interoperabilità.

• I componenti non sono eseguiti nel browser e WebAssembly non è

coinvolto

MAUI

• Framework multipiattaforma per la creazione

di app desktop e mobili native con C# e
XAML.​

• App eseguibili su Android, iOS, macOS e

Windows da un'unica codebase condivisa.

• Consente di implementare il maggior

numero possibile di logica dell'app e layout
dell'interfaccia utente in un'unica base di
codice.​

• Unifica le API Android, iOS, macOS e

Windows in un'unica API che consente
un'esperienza di sviluppo che può essere
scritta una sola volta ed eseguita ovunque.​

MAUI  Blazor hybrid

• Il supporto Blazor Hybrid è integrato nel framework .NET MAUI. ​

• .NET MAUI include il controllo BlazorWebView, che consente di

eseguire il rendering dei componenti Razor in una visualizzazione
Web incorporata.​

• Usando .NET MAUI e Blazor insieme, è possibile riutilizzare un set

di componenti dell'interfaccia utente Web su dispositivi mobili,
desktop e Web.​

Come? Con BlazorWebView

• BlazorWebView è un controllo che consente di ospitare un'app

Blazor nelle varie app native.​

• Disponibile come pacchetto nuget per le varie piattaforme​
• Il controllo BlazorWebView può essere aggiunto a qualsiasi

pagina di un'app .NET MAUI e fatto puntare alla radice dell'app
Blazor oppure ad un’altra pagina disponibile.​

BlazorWebView - Proprietà​

HostPage
Definisce la pagina di
partenza della Blazor
web app.​

RootComponents
Specifica una collezione
di component di root che
possono essere aggiunti​

StartPath
Definisce il path per la
navigazione quando il
componente Blazor è
stato caricato​

BlazorWebView - RootComponent

Selector
Definisce tramite
selettore CSS dove, nel
documento, il
componente deve essere
inserito​

ComponentType
definisce il tipo del
componente​

Parameters
Definisce i parametri
opzionali che possono
essere passata al
componente principale​

BlazorWebView - Eventi​

BlazorWebViewInitializing
Prima che il componente sia inizializzato. In questo evento è possible fare modifiche alla configurazione della BlazorWebView.​

BlazorWebViewInitialized
Dopo che il componente è stato inizializzato ma prima che ogni componente sia renderizzato. In questo evento è possible
avere accesso all’istanza della WebView specifica della piattaforma​

UrlLoading
Quanto un hyperlink è stato cliccato nella BlazorWebView. Permette di intercettare e gestire l’apertura del link (apri in
BlazorWebView, oppure app esterna) o di annullare il caricamento dell’URL.​

Build a Blazor Hybrid App

Workloads

Blazor

Blazor Hybrid
on MAUI

Blazor Hybrid
on WinForm
& WPF

Build a Blazor Hybrid App

Nugets

Build a Blazor Hybrid App

Oppure creiamo un progetto .NET MAUI Blazor Hybrid App

Demo

One UI to rule them all

Try on your Android phone!

(a Mordor fortunatamente non usano iOS)

Alcune considerazioni

• @rendermode non è supportato

con Blazor Hybrid

• Non è possibile utilizzare la

BlazorWebView (o WebView2)
all’interno di un form che è aperto
mediante .ShowDialog()

Comportamento di routing per le richieste URI​

Un link è internal se il nome host e lo schema corrispondono tra l'URI di
origine dell'app e l'URI della richiesta.
• Internal Link → l'app aprirà il link nella BlazorWebView
• External Link → il collegamento viene aperto da un’app esterna

determinata dal sistema operativo.

Per i collegamenti interni che puntano ad un file, ma non fanno riferimento
a contenuto statico: /file.x/Maryia.Melnyk/image.gif​
• WPF e Windows Form: viene restituito il contenuto della pagina host.​
• NET MAUI: restituisce un codice di risposta 404.​

Where can we deliver it?

Blazor Hybrid on WinForm or WPF

April 2018 (1803)

Windows Version

Win 7

Win 8

Win 8.1

Win 10

Win 11

.NET Version

.NET6

.NET 6

.NET6, .NET 7, .NET 8

WebView2

Blazor Hybrid

109 Manual Install

Latest
Manual Install

Latest

Blazor Hybrid on WinForm & WPF Support

Where can we deliver it?

Blazor Hybrid on WinForm or WPF

April 2018 (1803)

Windows Version

Win 7

Win 8

Win 8.1

Win 10

Win 11

.NET Version

.NET6

.NET 6

.NET6, .NET 7, .NET 8

WebView2

Blazor Hybrid

109 Manual Install

Latest
Manual Install

Latest

Blazor Hybrid on WinForm & WPF Support

Out of support soon!

Where can we deliver it?

Blazor Web

PWA Blazor

Blazor Hybrid
WinForm & WPF

Blazor Hybrid
MAUI

Blazor Server with
Electron

Windows Desktop

Linux Desktop

macOs

Android

iOs

Tizen

Where can we deliver it?

Blazor Web

PWA Blazor

Blazor Hybrid
WinForm & WPF

Blazor Hybrid
MAUI

Blazor Server with
Electron

Windows Desktop

Linux Desktop

macOs

Android

One UI to rule them all

Tizen

iOs

Use case per Blazor Hybrid

Sono uno sviluppatore
ASP.NET e posso far
girare la mia applicazione
ovunque senza cambiare
linguaggio

​Ho un’applicazione legacy
WinForm / WPF e voglio
migrare verso il Web

Ho un’applicazione Web,
ma in alcuni scenari, ho
bisogno di accedere a
funzionalità di basso
livello del OS

Ho bisogno della stessa
UI su più piattaforme

Voglio la mia app sugli
Store

Sono da solo e devo fare
tutto io

(Freelancers / Startups)

Q & A

https://github.com/nicolaparo/one-ui-to-rule-them-all

About us

Alessio Iafrate
Freelance Software Developer |
Microsoft MVP | Community manager
and speaker.

linkedin.com/in/alessio-iafrate

Nicola Paro
Solution Architect presso beanTech

linkedin.com/in/nicolaparo

Grazie!
