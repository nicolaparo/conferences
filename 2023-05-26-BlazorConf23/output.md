Accendi la festa con
Blazor Hybrid

Nicola Paro

Un grazie agli sponsor

E alle community che ci hanno supportato

A Real Life Story

A Real Life Story

Consolle Luci

Par Led RGB

Par Led RGB

DMX Cable

DMX Cable

A Real Life Story

PC

Par Led RGB

Par Led RGB

uDMX Adapter Cable

DMX Cable

A Real Life Story

PC

Par Led RGB

Par Led RGB

uDMX Adapter Cable

DMX Cable

A Real Life Story

Requisiti

Applicativo
Desktop

Uso di DLL
nativa Win32

Componenti
UI Custom

Blazor Hybrid on WinForm

Blazor Hybrid

On WinForms

Razor Components in Blazor Hybrid

Differenze con le altre modalità di utilizzo di Blazor

• Eseguiti nativamente nel dispositivo client.

• Possono accedere a tutte le funzionalità del dispositivo utilizzando

.NET

• Renderizzati in una WebView2 “embeddata” all’interno
dell’applicazione tramite un canale in interoperabilità.
https://github.com/dotnet/maui/blob/main/src/BlazorWebView/src/SharedSource/WebView2WebViewManager.cs#L201

Razor Components in Blazor Hybrid

Che cos’è WebView2 ?

• Microsoft Edge WebView2 è un runtime che fornisce funzionalità

web-based ad applicativi desktop.

• Utilizza Microsoft Edge come rendering engine.

Razor Components in Blazor Hybrid

Dietro le quinte: comunicazione tra .NET e WebView2

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

Build a WinForm Blazor App

Workloads

Build a WinForm Blazor App

Creazione Progetto

Build a WinForm Blazor App

Creazione Progetto – Aggiunta Nuget per utilizzare Blazor

Demo

Where can you Deliver it?

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

109

Manual Install

Latest

Latest

Blazor Hybrid on Winform Support

Where can you Deliver it?

https://developer.microsoft.com/en-us/microsoft-edge/webview2/

Blazor Hybrid on WinForms – Use Cases

Stessa esperienza su Web e Desktop

Web App

Native
Desktop App

Razor
Components
Class Library

Blazor Hybrid on WinForms – Use Cases

Step intermedio per la Modernizzazione delle Applicazioni

.NET Framework
Legacy WinForm
App

.NET 7
WinForm App

.NET 7
Blazor Hybrid
WinForm App

.NET 7
Blazor Web App

.NET Upgrade
Assistant

About Me

Nicola Paro
Cloud Solutions Engineer | Technical Team Leader

@ beanTech

linkedin.com/in/nicolaparo

github.com/nicolaparo

Grazie!
