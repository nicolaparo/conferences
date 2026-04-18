.NET Conf 2023

Da WinForm al Web:
La transizione è possibile
con Blazor Hybrid!

Nicola Paro

A Real Life Story

Maybe

A Real Life Story

• Applicativo per la

gestione degli ordini

• Hanno più client

connessi al database

• Applicativo WinForm
.NET Framework 3.5

A Real Life Story

Problematiche dell’implementazione attuale

Legacy
Codebase

Sincronizzazion
e

Problemi di
Sicurezza

Manutenzione e
Distribuzione

Scalabilità

Tecnologia
Obsoleta

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

A Real Life Story

Desiderata

https://northwind.boh

Blazor Hybrid on WinForm

Blazor Hybrid On WinForms

Differenze con le altre modalità di utilizzo di Blazor

• Eseguito nativamente nel dispositivo client.

• Può accedere a tutte le funzionalità del dispositivo utilizzando

.NET

• Renderizzato in una WebView2 “embeddata” all’interno
dell’applicazione tramite un canale in interoperabilità.
https://github.com/dotnet/maui/blob/main/src/BlazorWebView/src/SharedSource/WebView2WebViewManager.cs#L201

Blazor Hybrid On WinForms

Che cos’è WebView2 ?

• Microsoft Edge WebView2 è un runtime che fornisce funzionalità

web-based ad applicativi desktop.

• Utilizza Microsoft Edge come rendering engine.

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

Blazor Hybrid On WinForms

Workloads

Blazor Hybrid On WinForms

Nuget per utilizzare Blazor Hybrid

.NET Migration Tool

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

Where can you Deliver a Blazor Hybrid app?

https://developer.microsoft.com/en-us/microsoft-edge/webview2/

Alcune considerazioni…

• La strada verso il web è lunga e tortuosa

• Librerie vecchie o non più supportate
• Personalizzazioni a librerie di componenti implementate molti anni fa

• Ci sono molti modi per migrare verso il web: Blazor Hybrid è una

delle possibilità

Ci piace Blazor?

Blazor Developer Italiani è la prima
community italiana dedicata allo sviluppo di
applicazioni con Blazor

Thank You!

Q & A

Nicola Paro
Cloud Solutions Engineer | Technical Team Leader

@ beanTech

linkedin.com/in/nicolaparo

github.com/nicolaparo
