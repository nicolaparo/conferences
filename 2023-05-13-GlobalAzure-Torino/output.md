#GlobalAzureTorino

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

#GlobalAzureTorino

Al supermercato con Azure Data
Explorer
Nicola Paro

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

About Me
Nicola Paro
Cloud Solutions Engineer | Technical Team Leader
@ beanTech

linkedin.com/in/nicolaparo

github.com/nicolaparo

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

A Real Life Story

#GlobalAzureTorino

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

#GlobalAzure

A Real Life Story

Creerò degli scraper per leggere i prezzi dei prodotti
giorno per giorno.

Scraper 1

Scraper 2

Scraper 3

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

A Real Life Story

Salverò i dati estratti in alcuni RawFiles in formato TXT

Scraper 1

Scraper 2

Scraper 3

RF1

RF2

RF3

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

A Real Life Story

I miei adapters estrarranno i dati rilevanti e li
persisteranno in un formato comune

Scraper 1

Scraper 2

Scraper 3

RF1

RF2

RF3

Adapter 1

Adapter 2

Adapter 3

F1

F2

F3

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

A Real Life Story

Sono troppi dati e non riesco a leggerli.

Scraper 1

Scraper 2

Scraper 3

RF1

RF2

RF3

Adapter 1

Adapter 2

Adapter 3

F1

F2

F3

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

A Real Life Story

Sono troppi dati e non riesco a leggerli.

Scraper 1

Scraper 2

Scraper 3

RF1

RF2

RF3

Adapter 1

Adapter 2

Adapter 3

F1

F2

F3

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

A Real Life Story

Caricherò i files in uno Storage Account e li
analizzerò con Azure Data Explorer

Scraper 1

Scraper 2

Scraper 3

RF1

RF2

RF3

Adapter 1

Adapter 2

Adapter 3

F1

F2

F3

Storage
Account

ADX

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

A Real Life Story
Prima di fare Web Scraping

• Controlla prima i termini di licenza del sito web
• Non fare scraping di dati protetti da copyright
• Non fare scraping di contenuti protetti da login

• Non fare scraping dopo aver fatto una login

• Analizza solamente informazioni disponibili pubblicamente
• Controlla il /robots.txt per essere avere la certezza di poter analizzare

un determinato path

• Controlla la /sitemap.xml per un elenco agevolato delle pagine da

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

analizzare

Azure Data Explorer

#GlobalAzureTorino

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

#GlobalAzure

Azure Data Explorer

Azure Data Explorer è un servizio di analisi dati veloce e totalmente
gestito  per  l’analisi  in  tempo  reale  di  grandi  volumi  di  dati,
provenienti da applicazioni, siti web, dispositivi IoT ecc…

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Main Features

Fast Data
Ingestion

Interactive
Data
Exploration

Real Time
Analytics on
Streaming data

Scalability

Integration
with other
Azure Services

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
When does it makes sense to use ADX?

Sliding
Window of
data

Read A Lot!

Insert /
Append A Lot!

Few Delete

NEVER
Update

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Pricing for Business Purposes

ADX Cost   +   VMs Cluster Cost   +   Storage Cost

Dev/Test
Free (No SLA)

Standard
$0.11/core per
hour

Varies on VM
Size

$0.126/hour
for the
smallest VM

Pay per use

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

More info on https://azure.microsoft.com/en-us/pricing/details/data-explorer/

Azure Data Explorer
Pricing for Education Purposes with Limited Functionalities

ADX Cost   +   VMs Cluster Cost   +   Storage Cost

Dev/Test
Free (No SLA)

Varies on VM
Size

Free Cluster Available with Microsoft Account / AAD User Identity
No need for an Azure Subscription or Credit Card
Standard
$0.11/core per
hour

$0.126/hour
for the
smallest VM

Pay per use

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

More info on https://azure.microsoft.com/en-us/pricing/details/data-explorer/

Azure Data Explorer
Data Ingestion

SDK

Managed
Pipelines

ADX

Connectors
& Plugins

Other Tools

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Data Organization

Simile ai database
relazionali (ex: SqlServer)

Cluster

Database

Table

Table Schema

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Data Organization – Differenze rispetto ai RDMS

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

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Behind the scenes

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Behind the scenes

I dati delle tabelle sono divisi in extents
(aka shards, partizioni, …)

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Behind the scenes

I dati delle tabelle sono divisi in extents
(aka shards, partizioni, …)

Un extent è una mini-tabella che
contiene dati e metadati.

Un extent non può mai essere
modificato, ma può essere cancellato

I dati sono organizzati in colonne

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Behind the scenes

I dati delle tabelle sono divisi in extents
(aka shards, partizioni, …)

Un extent è una mini-tabella che
contiene dati e metadati.

Un extent non può mai essere
modificato, ma può essere cancellato

I dati sono organizzati in colonne

Extent più piccoli possono essere uniti
in extent più grandi

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Behind the scenes

Gli extent sono creati durante le
operazioni di inserimento

Un extent è unito ad altri

• Shard rebuild

• Shard merge

Un extent può essere cancellato con
una retention-policy

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Behind the scenes

Gli shards sono distribuiti tra i
nodi del cluster

Node 1

Node 2

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Behind the scenes - A query to the cluster

Logs

| where Timestamp > ago(1h)

Node 1

Node 2

Bla

Bla
Bla

Bla

Bla
Bla

Bla

Bla
Bla

Bla

Bla

Bla

Bla
Bla

Bla

Bla
Bla

Bla

Bla
Bla

Bla

Bla

Bla

Bla
Bla

Bla

Bla
Bla

Bla

Bla
Bla

Bla

Bla

Bla
Bla

Bla

Bla

Bla
Bla

Bla

Bla

Bla
Bla

Bla

Bla
Bla

Bla

Bla

Bla
Bla

Bla

Bla

Bla
Bla

Bla

Bla
Bla

Bla

Bla

Bla
Bla

Bla

Bla

Bla
Bla

Bla

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Behind the scenes - A query to the cluster

Logs

| where Timestamp > ago(1h)

Node 1

Node 2

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Behind the scenes - A query to the cluster

Logs

| where Timestamp > ago(1h)

Node 1

Node 2

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Kusto Query Language

Una query Kusto è una richiesta in sola lettura per il processamento dei dati e
la produzione di risulati.

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

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Kusto Query Language

SQL

SELECT

WHERE

KQL

project, extend, project-away, project-keep, …

where, search, …

JOIN, LEFT JOIN, …

join kind=inner, kind=leftouter, …

UNION

GROUP BY

ORDER BY

TOP, LIMIT

union

summarize

sort by, order by, top by

take

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

More on https://learn.microsoft.com/en-us/azure/data-explorer/kusto/query/

Demo

#GlobalAzureTorino

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

#GlobalAzure

Azure Data Explorer
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

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Materialized View

Una Materialized View è una vista aggregata sui dati di una tabella ADX. I dati sono
materializzati anche su disco.

Vantaggi nell’adozione delle Materialized View

Performance
Improvement

Data
Freshness

Cost
Reduction

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Update Policy vs Materialized View

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

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Where to start?

Azure Data Explorer supporta dei
database sample gratuiti su cui è
possibile effettuare delle interrogazioni
per prendere confidenza con lo
strumento

https://dataexplorer.azure.com/home

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Where to start?

Kusto Detective Agency: una
gamification per imparare ad usare
kusto! (e non solo)

https://detective.kusto.io/

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Azure Data Explorer
Where to start?

Find my partner: trova il tuo
partner per consulenza,
formazione e supporto in
Azure Data Explorer

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

https://learn.microsoft.com/it-it/azure/data-explorer/find-my-partner

Q & A

#GlobalAzureTorino

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

#GlobalAzure

Thank You!

#GlobalAzureTorino

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

#GlobalAzure

Contacts
Nicola Paro
Cloud Solutions Engineer | Technical Team Leader
@ beanTech

linkedin.com/in/nicolaparo

github.com/nicolaparo

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0

Y

e

l

l

o

w

R

:

2

5

5

G

:

1

8

5

B

:

0
