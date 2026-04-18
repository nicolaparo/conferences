Sabato 30 settembre 2023

Nicola Paro

Sabato 30 settembre 2023

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
Requirements

Applicativo
Desktop

Uso di DLL
nativa
Win32

Componenti
UI Custom

Blazor Hybrid on WinForm

Blazor Hybrid On WinForms
Differenze con le altre modalità di utilizzo di Blazor

• Eseguiti nativamente nel dispositivo client.

• Possono accedere a tutte le funzionalità del dispositivo

utilizzando .NET

• Renderizzati in una WebView2 “embeddata” all’interno

dell’applicazione tramite un canale in interoperabilità.

https://github.com/dotnet/maui/blob/main/src/BlazorWebView/src/SharedSource/WebView2WebViewManager.cs#L201

Blazor Hybrid On WinForms
Che cos’è WebView2 ?

• Microsoft Edge WebView2 è un runtime che fornisce
funzionalità web-based ad applicativi desktop.

• Utilizza Microsoft Edge come rendering engine.

Blazor Hybrid On WinForms
Dietro le quinte: comunicazione tra .NET e WebView2

SendMessage()

.NET

WebView
2

.addEventListener
( 'message', e =>
callback(e.data))

UI

WebMessageReceived()

sendMessage()

Blazor Hybrid On WinForms
Workloads

Blazor Hybrid On WinForms
Creazione Progetto

Blazor Hybrid On WinForms
Creazione Progetto – Aggiunta Nuget per utilizzare Blazor

DEMO

Where can you Deliver it?

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

Where can you Deliver it?

https://developer.microsoft.com/en-
us/microsoft-edge/webview2/

Blazor Hybrid on WinForms – Use Cases
Stessa esperienza su Web e Desktop

Web App

Native
Desktop App

Razor
Components
Class
Library

Blazor Hybrid on WinForms – Use Cases
Step intermedio per la Modernizzazione delle Applicazioni

.NET
Framework

Legacy
WinForm App

.NET 7

WinForm App

.NET 7

Blazor
Hybrid
WinForm App

.NET 7

Blazor Web
App

.NET Upgrade
Assistant

Blazor Hybrid on WinForms – Use Cases
Step intermedio per la Modernizzazione delle Applicazioni

Interessati a Blazor?

Blazor Developer Italiani è la prima
community italiana dedicata allo sviluppo
di applicazioni con Blazor

Sabato 30 settembre 2023

Nicola Paro

About Me

Nicola Paro
Cloud Solutions Engineer | Technical Team Leader

@ beanTech

linkedin.com/in/nicolaparo

github.com/nicolaparo
