XMAS DEV 2023

Monitora la fabbrica di biscotti per Babbo Natale con i servizi gratuiti Azure
Nicola Paro

Platinum Sponsor
Silver Sponsor
Gold Sponsor
| Technical | Sponsor | Community |
| --------- | ------- | --------- |

A Virtual Life Story
Il Natale è alle porte…

A Virtual Life Story
Il Natale è alle porte…

A Virtual Life Story
Il Natale è alle porte…
PROBLEMI
(o Opportunità?)
| • Se finisce    |     | il cioccolato, la produzione |      |                   |                  |         | si             | ferma    |     |
| --------------- | --- | ---------------------------- | ---- | ----------------- | ---------------- | ------- | -------------- | -------- | --- |
| • La produzione |     |                              | ogni | tanto si          |                  | inceppa | ed è richiesto |          | un  |
| intervento      |     | manuale                      |      | per ripristinarla |                  |         |                |          |     |
| • Nessuno       |     | si accorge                   |      | dei               | problemi, perché |         |                | non sono |     |
notificati
| • Necessaria |     | una    | soluzione |       |          | di monitoraggio, ma Azure  |     |     |     |
| ------------ | --- | ------ | --------- | ----- | -------- | -------------------------- | --- | --- | --- |
| non si       | può | pagare |           | con i | biscotti |                            |     |     |     |

Azure Free Services
https://azure.microsoft.com/en-us/pricing/free-services

Monitoring Platform Overview
|     |     | Event Storage | API |
| --- | --- | ------------- | --- |
RCON
Collector Module
| Minecraft | Receiver | Web Socket | UI  |
| --------- | -------- | ---------- | --- |
On Edge On Cloud

Monitoring Platform – Event Storage
|     |     |     |     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
|     |     |     | Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --- | --- | --- | --------- | ----------- | -------- | ---------- | --- |
• Deve persistere gli eventi dell’impianto produttivo per poterli
| successivamente | interrogare |     |     |     |     |     |     |
| --------------- | ----------- | --- | --- | --- | --- | --- | --- |
•
| Deve permettere | analitiche | in modo semplice |     |     |     |     |     |
| --------------- | ---------- | ---------------- | --- | --- | --- | --- | --- |

Cosmos DB
|     |     |     |     |     |     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | --- | --- | --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
|                    |     |     |               |             | Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| ------------------ | --- | --- | ------------- | ----------- | --------- | ----------- | -------- | ---------- | --- |
| • Database gestito |     |     | sia NoSQL che | relazionale |           |             |          |            |     |
•
Globalmente distribuito, altamente responsive e sempre online
| • Puoi | usare | l’API | che preferisci |     |     |     |     |     |     |
| ------ | ----- | ----- | -------------- | --- | --- | --- | --- | --- | --- |
Apache
|     |     | NoSQL |     | MongoDB |     |     |     |     |     |
| --- | --- | ----- | --- | ------- | --- | --- | --- | --- | --- |
Cassandra
Apache
Table PostgreSQL
Gremlin
• Free Tier: Max throughput 1000 RU/s + 25 GB storage

Azure SQL
|     |     |     |     |     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | --- | --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
|                        |     |            |         | Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| ---------------------- | --- | ---------- | ------- | --------- | ----------- | -------- | ---------- | --- |
| • Database relazionale |     | totalmente | gestito |           |             |          |            |     |
•
| Costriuito | sullo stesso | engine di SQL Server |     |     |     |     |     |     |
| ---------- | ------------ | -------------------- | --- | --- | --- | --- | --- | --- |
• Free Tier con 100,000 secondi * vCore e 32GB di storage limit al mese per
sempre
• Puoi scegliere di metterlo in auto-pause quando il limite è raggiunto
• Oppure continuare ad utilizzarlo e pagare solamente per la parte
extra

Azure Sql DB – Free Tier
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |

Monitoring Platform – Event Storage
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
Cosmos o SQL ? R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |

Monitoring Platform – Event Storage
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
Cosmos o SQL ? R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |

Monitoring Platform – Web Socket
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |
• Deve notificare gli eventi dell’impianto al frontent per garantire un rapido
intervento

Azure SignalR & Web PubSub
|     |     |     |     |     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | --- | --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
|     |     |     |     | Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --- | --- | --- | --- | --------- | ----------- | -------- | ---------- | --- |
Pensati per applicazioni che richiedono dati in tempo reale
| High  | Live  | Cross- | Real-time  |     |     |     |     |     |
| ----- | ----- | ------ | ---------- | --- | --- | --- | --- | --- |
Real-time
| frequency  | dashboards e  | platform live  | location on  |     |     |     |     |     |
| ---------- | ------------- | -------------- | ------------ | --- | --- | --- | --- | --- |
targeted ads
| updates        | monitoring    | chat         | map |     |            |     |     |     |
| -------------- | ------------- | ------------ | --- | --- | ---------- | --- | --- | --- |
| Collaborative  | Push          | Real-time    |     |     |            |     |     |     |
|                |               |              | IoT |     | Automation |     |     |     |
| apps           | notifications | broadcasting |     |     |            |     |     |     |

SignalR vs Azure Web PubSub
S E to v r e a n g t e API
R
C
O
N
Minecraft C M ol o le d c u t l o e r Receiver Web Socket UI
• Stai già usando SignalR • Hai bisogno solo di WebSocket
• Esiste un client SignalR nel • Subprotocollo custom over
linguaggio scelto WebSocket
• Clients supportati da MS: • MQTT over WebSocket
• AMQP over WebSocket
• È sufficiente un’infrastruttura «lite»
per la tua applicazione
• Hai necessità di più protocolli di
trasporto
• WebSocket
• Server sent events
• Long polling

Inside Azure Web PubSub
S E to v r e a n g t e API
R
C
O
N
Minecraft C M ol o le d c u t l o e r Receiver Web Socket UI
Group Group Group Group
Hub Hub
Web Pub Sub

Sending Data with Azure Web PubSub
S E to v r e a n g t e API
R
C
O
N
Minecraft C M ol o le d c u t l o e r Receiver Web Socket UI
• ServiceClient C#
Azure.Messaging.WebPubSub
• AzFunction Bindings
Microsoft.Azure.WebJobs.Extensions.WebPubSub

Azure Web PubSub Pricing
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |

Monitoring Platform – Web Socket
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
Web Pub Sub o SignalR R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |

Monitoring Platform – Web Socket
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
Web Pub Sub o SignalR R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |

Monitoring Platform - Receiver
|     |     |     |     |     |     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | --- | --- | --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
|     |     |     |     |     | Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --- | --- | --- | --- | --- | --------- | ----------- | -------- | ---------- | --- |
• Deve ricevere degli eventi sporadici dall’impianto produttivo
| • Deve persistere | questi             | eventi | sull’Event | Storage |     |     |     |     |     |
| ----------------- | ------------------ | ------ | ---------- | ------- | --- | --- | --- | --- | --- |
| • Deve notificare | via WebSocket ogni |        |            | evento  |     |     |     |     |     |

Azure Functions Free granT
|     |     |     |     |     |     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | --- | --- | --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
|     |     |     |     |     | Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --- | --- | --- | --- | --- | --------- | ----------- | -------- | ---------- | --- |
• Solamente con Consumption Plan in sottoscrizioni Pay As You Go
• Fino a 400.000 GBs ed 1 milioni di invocazioni
| • Oppure | le posso | hostare | in un AppServicePlan | free |     |     |     |     |     |
| -------- | -------- | ------- | -------------------- | ---- | --- | --- | --- | --- | --- |
• Nonostante abbiano un free grant, le Azure Functions richiedono sempre
lo Storage Account per funzionare (che non è gratuito)

Monitoring Platform - Receiver
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
Azure Functions R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |

Monitoring Platform - Receiver
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
Azure Functions R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |

Monitoring Platform - API
|     |     |     |     |     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | --- | --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
|                |            |            |         | Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| -------------- | ---------- | ---------- | ------- | --------- | ----------- | -------- | ---------- | --- |
| • Deve leggere | gli eventi | dall’Event | Storage |           |             |          |            |     |
•
| Deve fare delle | piccole | aggregate |     |     |     |     |     |     |
| --------------- | ------- | --------- | --- | --- | --- | --- | --- | --- |
• Deve esporre i contenuti via REST per renderli disponibili alla UI

Azure Container Apps
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |
Piattaforma serverless per l’esecuzione di applicazioni containerizzate

Azure Container Apps Free Grant
|     |     |     |     |     |     |     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
|         |                               |                 |             |        |          | Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| ------- | ----------------------------- | --------------- | ----------- | ------ | -------- | --------- | ----------- | -------- | ---------- | --- |
| • Ogni  | mese, gratis:                 |                 |             |        |          |           |             |          |            |     |
|         | • Fino a 180,000 vCPU-seconds |                 |             |        |          |           |             |          |            |     |
|         | • 360,000 GiB-seconds         |                 |             |        |          |           |             |          |            |     |
|         | • 2 million di richieste      |                 |             |        |          |           |             |          |            |     |
| • Altre | opzioni                       | per non pagarle |             | pagare | di meno: |           |             |          |            |     |
|         | • Scalare                     | a 0 il numero   | di repliche |        |          |           |             |          |            |     |
• Quando non ci sono richieste HTTP in ingresso ed il numero di
|     | repliche | è al minimo, viene |     | applicato | un prezzario | ridotto |     |     |     |     |
| --- | -------- | ------------------ | --- | --------- | ------------ | ------- | --- | --- | --- | --- |

Azure App Service Web Apps
|     |     |     |     |     |     |     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
|          |         |             |              |                |                  | Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| -------- | ------- | ----------- | ------------ | -------------- | ---------------- | --------- | ----------- | -------- | ---------- | --- |
| Servizio | gestito | per hostare | applicazioni | web e REST API |                  |           |             |          |            |     |
| Vasta    | scelta  | di          |              |                | Aggiornamenti e  |           |             |          |            |     |
Supporta container
| linguaggi |     |     |     |     | patch di sicurezza |     |     |     |     |     |
| --------- | --- | --- | --- | --- | ------------------ | --- | --- | --- | --- | --- |
docker
| utilizzabili |     |     |     |     |     | gestite |     |     |     |     |
| ------------ | --- | --- | --- | --- | --- | ------- | --- | --- | --- | --- |
Supporto
|     | all’autenticazione |     |     | Gestione       | del CORS  |     |     |     |     |     |
| --- | ------------------ | --- | --- | -------------- | --------- | --- | --- | --- | --- | --- |
|     | senza modificare   |     | il  | out of the box |           |     |     |     |     |     |
codice applicativo

Azure App Service Plan FREE TIER
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |
Posso avere solo un’istanza di App Service Plan Free per sottoscrizione

Monitoring Platform - API
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
Container Apps o Web Apps R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |

Monitoring Platform - API
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
Container Apps o Web Apps R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |

Monitoring Platform - UI
|     |     |     |     |     |     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | --- | --- | --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
|     |     |     |     |     | Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --- | --- | --- | --- | --- | --------- | ----------- | -------- | ---------- | --- |
• Applicativo per la consultazione degli eventi storici e la ricezione delle
| notifiche | a partire |     | dall’impianto | produttivo |     |     |     |     |     |
| --------- | --------- | --- | ------------- | ---------- | --- | --- | --- | --- | --- |
• Non ha necessità di un backend applicativo. Si può appoggiare alle API
| già   | implementate |        |         |     |     |     |     |     |     |
| ----- | ------------ | ------ | ------- | --- | --- | --- | --- | --- | --- |
| • Può | essere       | un’app | statica |     |     |     |     |     |     |

Azure Static WebApp
|     |     |     |     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
|     |     |     | Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --- | --- | --- | --------- | ----------- | -------- | ---------- | --- |
È un servizio che consente di creare applicazioni Web statiche.
Pubblicazione di
| contenuti | statici | CI/CD con GitHub  |     |     |     |     |     |
| --------- | ------- | ----------------- | --- | --- | --- | --- | --- |
Supporto alle API
| con HTML, CSS e  |     | and Azure DevOps |     |     |     |     |     |
| ---------------- | --- | ---------------- | --- | --- | --- | --- | --- |
JavaScript
| Contenuto | statico | Gestione |     | di  |     |     |     |
| --------- | ------- | -------- | --- | --- | --- | --- | --- |
Certificato SSL
| distribuito |     | ambiente |     | di  |     |     |     |
| ----------- | --- | -------- | --- | --- | --- | --- | --- |
gratuito
| globalmente |     |     | Staging |     |     |     |     |
| ----------- | --- | --- | ------- | --- | --- | --- | --- |

Azure Blob Static Website
|                        |     |     |     |     |     |     | S E to v r e a n g t e   | API |
| ---------------------- | --- | --- | --- | --- | --- | --- | ------------------------ | --- |
| vs Azure Static WebApp |     |     |     | R   |     |     |                          |     |
C
O
N
C ol le c t o r
|         |                      |        |                   | Minecraft   | M o d u l e | Receiver | Web Socket | UI  |
| ------- | -------------------- | ------ | ----------------- | ----------- | ----------- | -------- | ---------- | --- |
| •       | SSL                  | •      | SSL               |             |             |          |            |     |
| •       | CI/CD non gestito    | •      | CI/CD integrate   |             |             |          |            |     |
| •       | No Multiregion       | •      | Globalmente       | distribuito |             |          |            |     |
| •       | Custom Domain        | •      | Custom Domain     |             |             |          |            |     |
| •       | No HTTPS con Custom  | •      | HTTPS con Custom  |             |             |          |            |     |
| Domains |                      | Domain |                   |             |             |          |            |     |

Azure Static WebApp – Backend?
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |
Managed

Azure Static WebApp – Backend?
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |
Managed
Data Api Builder Endpoint

Data API Builder?
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |
Per utilizzare DAB in locale
dotnet tool install -g Microsoft.DataApiBuilder

Azure Static WebApp Pricing
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |

Required Tools to work with this technology
|     |     |     |     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | --- | --- | --- | ------------------------ | --- |
R
C
O
N
C ol le c t o r
|     |     |     | Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --- | --- | --- | --------- | ----------- | -------- | ---------- | --- |
Static Web App Command line tool (swa)
| npm  | install -g @azure/static-web-apps-cli |      |     |     |     |     |     |
| ---- | ------------------------------------- | ---- | --- | --- | --- | --- | --- |
| Wasm | tools to output Blazor                | wasm |     |     |     |     |     |
dotnet workload install -g wasm-tools-net6
https://azure.github.io/static-web-apps-cli/docs/use/install/

Monitoring Platform - UI
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
Azure Static Web App o Azure Static Web App? R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |

Monitoring Platform - UI
|     |     |     | S E to v r e a n g t e   | API |
| --- | --- | --- | ------------------------ | --- |
Azure Static Web App o Azure Static Web App? R
C
O
N
C ol le c t o r
| Minecraft | M o d u l e | Receiver | Web Socket | UI  |
| --------- | ----------- | -------- | ---------- | --- |

Monitoring Platform Overview
|     |     | Event Storage | API |
| --- | --- | ------------- | --- |
RCON
Collector
| Minecraft | Receiver | Web Socket | UI  |
| --------- | -------- | ---------- | --- |
Module
On Edge On Cloud

Demo

About Me
Nicola Paro
Cloud Solutions Engineer | Technical Team Leader
beanTech
Let’s Connect!
linkedin.com/in/nicolaparo github.com/nicolaparo

GRAZIE!
Valuta questa sessione
