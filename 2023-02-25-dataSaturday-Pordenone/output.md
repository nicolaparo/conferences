Al supermercato con Azure Data
Explorer

Sponsors

With the support of:

About me

Nicola Paro
Cloud Solutions Engineer

Linkedin: linkedin.com/in/nicolaparo

Github: github.com/nicolaparo

Twitter: @nicola_paro

A Real Life Story

With the support of:

A Real Life Story

Creerò degli scraper per leggere i prezzi dei prodotti
giorno per giorno.

Scraper 1

Scraper 2

Scraper 3

With the support of:

A Real Life Story

Salvo i dati estratti in alcuni RawFiles in formato TXT

Scraper 1

Scraper 2

Scraper 3

RF1

RF2

RF3

With the support of:

A Real Life Story

I miei importer estrarranno i dati rilevanti e li
persisteranno in un formato condiviso

Scraper 1

Scraper 2

Scraper 3

RF1

RF2

RF3

Importer 1

Importer 2

Importer 3

F1

F2

F3

With the support of:

A Real Life Story

Sono troppi dati e non riesco a leggerli.

Scraper 1

Scraper 2

Scraper 3

RF1

RF2

RF3

Importer 1

Importer 2

Importer 3

F1

F2

F3

With the support of:

A Real Life Story

Sono troppi dati e non riesco a leggerli.

Scraper 1

Scraper 2

Scraper 3

RF1

RF2

RF3

Importer 1

Importer 2

Importer 3

F1

F2

F3

With the support of:

A Real Life Story

Caricherò i files su uno Storage Account e li analizzerò
con Azure Data Explorer

Scraper 1

Scraper 2

Scraper 3

RF1

RF2

RF3

Importer 1

Importer 2

Importer 3

F1

F2

F3

Storage
Account

ADX

With the support of:

Prima di fare Web Scraping

• Controlla prima i termini di licenza del sito web
• Non fare scraping di dati protetti da copyright
• Non fare scraping di contenuti protetti da login
• Non fare scraping dopo aver fatto una login

• Analizza solamente informazioni disponibili pubblicamente
• Controlla il /robots.txt per essere sicuro di poter analizzare un

determinato path

• Controlla la /sitemap.xml per un elenco agevolato delle pagine da

analizzare

With the support of:

Azure Data Explorer

With the support of:

Azure Data Explorer

Azure  Data  Explorer  è  un  servizio  di  analisi  dati  veloce  e
totalmente gestito per l’analisi in tempo reale di grandi volumi di
dati, provenienti da applicazioni, siti web, dispositivi IoT ecc…

With the support of:

Azure Data Explorer

Features Principali

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

With the support of:

Azure Data Explorer

Quando ha senso utilizzare ADX?

Sliding
Window of
data

Tante letture

Tanti Insert /
Append

Poche Delete

NESSUN
Update

With the support of:

Azure Data Explorer

Pricing

ADX Cost   +   VMs Cluster Cost   +   Storage Cost

Dev/Test
Free (No SLA)

Standard
$0.11/core per
hour

Varies on VM
Size

$0.126/hour for
the smallest VM

Varies by usage

More info on https://azure.microsoft.com/en-us/pricing/details/data-explorer/

With the support of:

Azure Data Explorer

Organizzazione dei dati

Simile ai database
relazionali (ex: SqlServer)

Cluster

Database

Table

Schema

With the support of:

Azure Data Explorer

Organizzazione dei dati – Differenze rispetto ai RDMS

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

With the support of:

Azure Data Explorer

Data Ingestion

SDK

Managed
Pipelines

ADX

Connectors
& Plugins

Other Tools

With the support of:

Azure Data Explorer

Dietro le quinte

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

Bla

With the support of:

Azure Data Explorer

Dietro le quinte

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

With the support of:

Azure Data Explorer

Dietro le quinte

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

With the support of:

Azure Data Explorer

Dietro le quinte

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

With the support of:

Azure Data Explorer

Dietro le quinte

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

With the support of:

Azure Data Explorer

Dietro le quinte

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

With the support of:

Azure Data Explorer

Una “semplice query” nel cluster

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

With the support of:

Azure Data Explorer

Una “semplice query” nel cluster

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

With the support of:

Azure Data Explorer

Una “semplice query” nel cluster

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

With the support of:

Azure Data Explorer

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

With the support of:

Azure Data Explorer

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

With the support of:

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

With the support of:

Demo

With the support of:

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

With the support of:

Azure Data Explorer

Materialized View

Una Materialized View è una vista aggregate sui dati di una tabella ADX. I dati sono
materializzati anche su disco.

Vantaggi nell’adozione delle Materialized View

Performance
Improvement

Data
Freshness

Cost
Reduction

With the support of:

Azure Data Explorer

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

With the support of:

Azure Data Explorer

Devo pagare un cluster per fare pratica con Kusto?

Azure Data Explorer supporta dei
database “sample” gratuiti su cui è
possibile effettuare delle interrogazioni
per provare

https://dataexplorer.azure.com/home

With the support of:

Azure Data Explorer

Devo pagare un cluster per fare pratica con Kusto?

Kusto Detective Agency: una gamification
per imparare ad usare kusto.

https://detective.kusto.io/

With the support of:

Q & A

With the support of:

Thank You!

With the support of:

Link e Contatti

Nicola Paro
Cloud Solutions Engineer

With the support of:
