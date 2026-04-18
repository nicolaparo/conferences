Sabato 30 settembre 2023

Nicola Paro

Sabato 30 settembre 2023

A Real Life Personal Challenge
Dove la mia passione ebbe inizio…

A Real Life Personal Challenge
Ora però…

A Real Life Personal Challenge
Quindi…

• C’è modo di unire la mia passione per la creazione di

videogiochi con le competenze che ho acquisito in questi
anni?

• No, JavaScript purtroppo non è una delle mie competenze

• Blazor Interactive Server ce la può fare?

Game Entity Lifecycle

Creation

Draw

Step

Destroy

Game Entity Lifecycle, in Blazor Server

Creation

Draw

Step

Destroy

RequestFrame

Canvas.Draw…()

…done…

Canvas.Draw…()

…done…

Await

Await

33ms MAX

Game Entity Lifecycle, in Blazor Server

Creation

Draw

Step

Destroy

RequestFrame

Canvas.Draw…()

…done…

Canvas.Draw…()

…done…

Await

Await

33ms MAX

Game Development tradizionale… Con Blazor?
Qualcuno c’è riuscito!

GitHub - mizrael/BlazorCanvas: Simple 2D gamedev examples using Blazor and .NET 5

GitHub - mizrael/Blazorex: Blazorex is an HTML Canvas wrapper library for Blazor.

Game Development tradizionale… Con Blazor?
Ma…

• Le funzionalità sono limitate e pare funzionare solamente

con Blazor Interactive Client

• La libreria utilizza IJSInProcessRuntime per effettuare le chiamate

sincrone alle funzionalità JavaScript

• Fare la stessa cosa in Blazor Interactive Server è

proibitivo dal punto di vista delle performance

• Non abbiamo abbastanza tempo per tutte le chiamate asincrone al

javascript

• Blazor è pensato per fare altro…

Cosa riesce a fare (bene) Blazor?

Reagisce alle azioni
dell’utente

Produce e modifica in
modo dinamico
documenti Markup

Click, Keyboard Press,
Touch, …

HTML  XML  SVG

Game Development… Con Blazor?
Forse forse…

Se un gioco segue questo flusso, forse lo possiamo
realizzare con Blazor

Attesa
Azione

Modifica
Stato

Rendering

Parliamo di grafica

Che cos’è SVG - Scalable Vector Graphics

Formato di immagine basato su XML utilizzato per definire
grafica vettoriale bidimensionale.

A differenza delle immagini raster (come JPEG o PNG), che
sono costituite da una griglia di pixel, le immagini SVG
sono composte da forme geometriche come linee, cerchi,
rettangoli e testo, definite attraverso descrizioni
matematiche.

Che cos’è SVG - Scalable Vector Graphics

• Elemento <img>

• <img src="immagine.svg"> per inserire un file SVG come un'immagine

normale.

• Elemento <object>

• <object data="immagine.svg" type="image/svg+xml"> per un controllo

avanzato e fallback.

• Elemento <iframe>

• <iframe src="immagine.svg"></iframe> per tenere l'SVG separato dal

DOM principale.

• Sfondo CSS

• Imposta un SVG come background di un elemento con background-image:

url('immagine.svg');.
• Incorporare direttamente

• Il codice SVG direttamente nel file HTML per un pieno controllo su

stile e interattività, tramite un elemento <svg>

Blazor Hybrid On WinForms
Differenze con le altre modalità di utilizzo di Blazor

• Eseguiti nativamente nel dispositivo client.

• Possono accedere a tutte le funzionalità del dispositivo

utilizzando .NET

• Renderizzati in una WebView2 “embeddata” all’interno

dell’applicazione tramite un canale in interoperabilità.

https://github.com/dotnet/maui/blob/main/src/BlazorWebView/src/SharedSource/WebView2WebViewManager.cs#L201
