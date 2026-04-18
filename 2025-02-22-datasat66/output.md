Real Time Intelligence Experience
in Microsoft Fabric
Nicola Paro

Sponsors

A real life story…

TMPPRO-V1
€ 100

TMPPRO-V2
€ 1000

L’IoT non è sempre «RealTime»

Hot - primo livello di monitoraggio
• Variabili «onchange» di cui tracciare il cambiamento

•

Stati, Allarmi, Settings, Counters

• Cardinalità di valori limitata
•
•
•

Immediatamente notificati, oppure aggregati
Inviati nell’ordine dei minuti
Json+MQTT

L’IoT non è sempre «RealTime»

Warm: il secondo livello di monitoraggio
• Variabili di performance, con valori continui (decimali)

• Se sono in allarme, o voglio fare una ottimizzazioni, allora
guardo lo storico, che arriva su con calma e regolarità

• Possono essere anche campionati nell’ordine del secondo,

ma sono bufferizzati ed inviati a pacchetti

• CSV, Parquet

L’IoT non è sempre «RealTime»

Cold: non è monitoraggio
• Dati relativi al contesto produttivo

• Asset, produzione, mes, erp, per decodificare i dati che

arrivano dagli asset

• Non è OT
• SQL, Data Integration, ETL

L’IoT non è sempre «RealTime»

Hot Streaming: il terzo livello di
monitoraggio
•

Se serve il qui e ora, si fa lo streaming dei dati che
normalmente arrivano come warm
Lo si fa solamente «on demand» on/off, per colmare il gap
dell’attesa dei dati warm.
Json+MQTT

•

•

Cosa è Real Time Intelligence

È uno dei workload/experience di
Fabric

Si focalizza sul pattern e sui servizi
che hanno a che fare con il
concetto di «Evento»:
• Eventstream
• EventHouse
• Data Activator

All’IoT piace LakeHouse e le shortcuts

• Il device IoT genera file parquet o json, li carica

su un datalake

• Posso caricare i dati in LakeHouse tramite

shortcut o tramite una pipeline di Data Factory

Event Hub & IoT Hub

• Azure Event Hub è un servizio di messaggistica in tempo reale
completamente gestito di Microsoft Azure. È progettato per
l'ingestion di grandi quantità di dati di eventi da varie fonti e la loro
elaborazione in tempo reale.

•

•

IoT Hub ha un endpoint compatibile EventHub
• Gestisce anche le identità dei devices

è una soluzione gestita che offre un'integrazione facile con altri
servizi di Azure e una gestione semplificata

Gli eventi non sono solo IoT

• Anche le applicazioni possono generare eventi

• Un log altro non è che la traccia della sequenza di eventi

• Fino a prova contraria anche un server può essere visto

come un dispositivo IoT

• Uno storage può generare eventi ed in generale tutti i db

con dei feed Change Data Capture sono buone sorgenti per
Real Time Analytics

Common Real-time Analytics Patterns

Data Source

Ingestion

Store

Expose

Lakehouse &
Data Warehouse

CI & Shortcuts

Kusto DB

PBI

Structured /
Unstructured

Pipeline &
Dataflows

Event Streaming

ML Model

Kusto Query

Notebook

Mirror
Lakehouse & Data
Warehouse

Eventstreams

Eventstreams

• Punto centralizzato dove raccogliere, trasformare e instradare gli eventi.
• Connettori per recuperare dati degli eventi da diverse fonti, come app
personalizzate per inviare a Eventstreams, Azure Event Hub o Samples

• Esperienza Low Code nella definizione del flusso

Event House
L’esperienza KQL in Fabric

KQL Database – Organizzazione dei dati

Fabric Workspace

KQL Database

Table

Schema

KQL Database – Differenze rispetto ai RDMS

No Primary
Key

No Unique
Keys

No Foreign
Keys

Columnstore
Indexes

Data Sharding
(Extents)

Rowstore

Nome

Cognome

Data di Nascita

Sesso

Giovanni

Sofia

Marco

Laura

Luca

Chiara

Matteo

Alessia

Federico

Martina

Rossi

Bianchi

Esposito

Romano

Russo

Colombo

Moretti

Ferrari

Conti

Marini

15/03/1987

22/07/1995

10/11/1980

05/09/1990

20/04/1975

18/06/1988

30/12/1978

08/02/1992

25/10/1983

12/07/1998

M

F

M

F

M

F

M

F

M

F

Giovanni....Rossi.......15/03/1987..MSofia..
.....Bianchi.....22/07/1995..FMarco.......Es
posito....10/11/1980..MLaura.......Romano...
...05/09/1990..FLuca........Russo.......20/0
4/1975..MChiara......Colombo.....18/06/1988.
.FMatteo......Moretti.....30/12/1978..MAless
ia.....Ferrari.....08/02/1992..FFederico....
Conti.......25/10/1983..MMartina.....Marini.
.....12/07/1998..F

Columnstore

Nome

Cognome

Data di Nascita

Sesso

Giovanni

Sofia

Marco

Laura

Luca

Chiara

Matteo

Alessia

Federico

Martina

Rossi

Bianchi

Esposito

Romano

Russo

Colombo

Moretti

Ferrari

Conti

Marini

15/03/1987

22/07/1995

10/11/1980

05/09/1990

20/04/1975

18/06/1988

30/12/1978

08/02/1992

25/10/1983

12/07/1998

M

F

M

F

M

F

M

F

M

F

Giovanni....Sofia.......Marco.......Laura...
....Luca........Chiara......Matteo......Ales
sia.....Federico....Martina.....Rossi.......
Bianchi.....Esposito....Romano......Russo...
....Colombo.....Moretti.....Ferrari.....Cont
i.......Marini......15/03/1987..22/07/1995..
10/11/1980..05/09/1990..20/04/1975..18/06/19
88..30/12/1978..08/02/1992..25/10/1983..12/0
7/1998..MFMFMFMFMF

Quando ha senso usare un KQL Database?

Sliding
Window of
data

Tante letture

Tanti Insert /
Append

Poche Delete

NESSUN
Update

KQL: Kusto Query Language

Kusto Query Language

Una query Kusto è una richiesta in sola lettura per il processamento dei dati e la
produzione di risulati.

La richiesta è effettuata tramite testo, utilizzando un modello di data-flow che è
semplice da leggere, scrivere ed automatizzabile.

Le query Kusto sono composte di una o più istruzioni.

Initial Data

Intermediate
Data Set 1

Intermediate
Data Set 2

Intermediate
Data Set n

Result Set

Azure Data Explorer

Kusto Query Language

SQL

SELECT

WHERE

JOIN

UNION

GROUP BY

ORDER BY

TOP, LIMIT

KQL

project, extend, project-away, project-keep …

where, search, …

join kind=inner

union

summarize

sort by, order by, top by

take

More on https://learn.microsoft.com/en-us/azure/data-explorer/kusto/query/

Update Policies

Update Policies

Una update policy è una comando che aggiunge
dati ad una tabella di destinazione Target a
partire da una Source Table

Ingestion

Source Table

bla

bla

bla

bla1

bla1

bla1

bla2

bla2

bla2

Target Table A

bla

bla

bla

bla1

bla1

bla1

Target Table B

bla

bla

bla

bla2

bla2

bla2

Materialized View

Materialized View

Una Materialized View è una vista aggregate sui dati di una tabella KQL. I dati sono
materializzati anche su disco.

Vantaggi nell’adozione delle Materialized View

Performance
Improvement

Data
Freshness

Cost
Reduction

Medallion Architecture

Update Policy o Materialized View?

Update Policy
• Data Transformation

• Data Enrichment

Materialized View
• Data Aggregation

Bronze Table

bla

bla

bla

bla

bla

bla

bla

bla

bla

Update Policy

Silver Table

bla

bla

bla

bla

bla

bla

bla

bla

bla

Materialized View

Gold Table

bla

bla

bla

bla

bla

bla

bla

bla

bla

Limitazioni per le Update Policies

La query di una update policy può invocare stored functions, ma:
• Non può eseguire query incrociate tra diversi eventhouse.
• Non può accedere a dati esterni o tabelle esterne.
• Non può effettuare richieste esterne (utilizzando un plugin).
La query non ha accesso in lettura alle tabelle che hanno abilitata la policy
RestrictedViewAccess.

Limitazioni per le Materialized Views

• La tabella sorgente di una materialized view deve essere una tabella in cui i dati

vengono inseriti direttamente
• Ok update policy o ingest query.

• La tabella sorgente di una materialized view deve avere la IngestionTime policy abilitata.

(Abilitata di default).

• NO operatori come mv-expand o il plugin pivot che non preservano il valore di

ingestion_time() e quindi non possono essere utilizzati in una materialized view con un
lookback.

• Una materialized view non può essere creata sopra un'altra materialized view, a

meno che la prima materialized view non sia del tipo take_any(*) aggregation.

• Le materialized views non possono essere definite su external tables.

Demo

Devo pagare Fabric per far pratica con Kusto?

Realtime Analytics is Azure Data Explorer!

Azure Data Explorer supporta dei database
“sample” gratuiti su cui è possibile effettuare
delle interrogazioni per provare

https://dataexplorer.azure.com/home

Devo pagare Fabric per far pratica con Kusto?

Kusto Detective Agency: una gamification
per imparare ad usare kusto.

https://detective.kusto.io/

About me

Nicola Paro
Solution Architect – beanTech

linktr.ee/nicolaparo
