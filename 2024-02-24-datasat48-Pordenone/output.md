Monitora la tua farm di Minecraft
con Azure Data Explorer

Sponsors

A Real Life Story

A Real Life Story

A Real Life Story

A Real Life Story

A Real Life Story

• Quanto tempo spendono le api nel proprio alveare?

• Tra quanto tempo esaurirò lo spazio per il miele?

• Le api hanno una dimora fissa?

A Real Life Story

RCON

.jsonl

A Real Life Story

async Task<SampleDataItem> SampleDataAsync()
{

   var day = await client.TimeQueryDayAsync();
   var dayTime = await client.TimeQueryDayTimeAsync();

   var beehives = await GetBeehivesAsync();
   var outputChests = await GetChestsContentsAsync();

   return new SampleDataItem(day, dayTime, beehives, outputChests);

}

var timer = new Timer(async _ =>
{

   Console.WriteLine("Reading data...");
   var sampleData = await collector.SampleDataAsync();

   File.AppendAllLines($"day-{sampleData.Day}.jsonl", [
       JsonSerializer.Serialize(new { sampleData.Day, sampleData.DayTime, Type = "OutputChests", Data = sampleData.OutputChests }),
       JsonSerializer.Serialize(new { sampleData.Day, sampleData.DayTime, Type = "Beehives", Data = sampleData.Beehives }),
   ]);

}, null, TimeSpan.Zero, TimeSpan.FromSeconds(5));

A Real Life Story

{"Day":40,"DayTime":428,"Type":"OutputChests","Data":[[],[],[],[],[],[],[],[],[],[],[],[{"Slot":0,"id":"minecraft:honey_block","Count":64},{"Slot":1,"id":"mine
craft:honey_block","Count":64},{"Slot":2,"id":"minecraft:honey_block","Count":17}],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[
],[],[],[],[],[],[],[],[],[],[]]}
{"Day":40,"DayTime":428,"Type":"Beehives","Data":[{"Bees":[{"TicksInHive":481,"EntityData":{"Attributes":[{"Base":48,"Modifiers":[{"Operation":1,"UUID":[-
677666685,-1972092740,-1499300242,59951531],"Amount":0.021267192,"Name":"Random spawn
bonus"}],"Name":"minecraft:generic.follow_range"},{"Base":0.3,"Modifiers":null,"Name":"minecraft:generic.movement_speed"}]}},{"TicksInHive":382,"EntityData":{"
Attributes":[{"Base":48,"Modifiers":[{"Operation":1,"UUID":[-1289509923,-525185133,-1405974367,-370337279],"Amount":0.051070083,"Name":"Random spawn
bonus"}],"Name":"minecraft:generic.follow_range"},{"Base":0.3,"Modifiers":null,"Name":"minecraft:generic.movement_speed"}]}}]},{"Bees":[{"TicksInHive":499,"Ent
ityData":{"Attributes":[{"Base":48,"Modifiers":[{"Operation":1,"UUID":[549663717,1511737572,-1728276919,-1347919532],"Amount":-0.08425045,"Name":"Random spawn
bonus"}],"Name":"minecraft:generic.follow_range"},{"Base":0.3,"Modifiers":null,"Name":"minecraft:generic.movement_speed"}]}},{"TicksInHive":494,"EntityData":{"
Attributes":[{"Base":48,"Modifiers":[{"Operation":1,"UUID":[-1254433216,1652508928,-1391806683,-1742753251],"Amount":-0.0009832926,"Name":"Random spawn
bonus"}],"Name":"minecraft:generic.follow_range"},{"Base":0.3,"Modifiers":null,"Name":"minecraft:generic.movement_speed"}]}},{"TicksInHive":435,"EntityData":{"
Attributes":[{"Base":48,"Modifiers":[{"Operation":1,"UUID":[-766511703,360467320,-1686136457,710167439],"Amount":0.077570975,"Name":"Random spawn
bonus"}],"Name":"minecraft:generic.follow_range"},{"Base":0.3,"Modifiers":null,"Name":"minecraft:generic.movement_speed"}]}}]},{"Bees":[{"TicksInHive":442,"Ent
ityData":{"Attributes":[{"Base":48,"Modifiers":[{"Operation":1,"UUID":[1414183203,-600161118,-1853165412,-1011782503],"Amount":0.019186005,"Name":"Random spawn
bonus"}],"Name":"minecraft:generic.follow_range"},{"Base":0.3,"Modifiers":null,"Name":"minecraft:generic.movement_speed"}]}}]},{"Bees":[{"TicksInHive":475,"Ent
ityData":{"Attributes":[{"Base":48,"Modifiers":[{"Operation":1,"UUID":[-932296066,1913995519,-1783415465,1928982629],"Amount":-0.014792211,"Name":"Random spawn
bonus"}],"Name":"minecraft:generic.follow_range"},{"Base":0.3,"Modifiers":null,"Name":"minecraft:generic.movement_speed"}]}},{"TicksInHive":471,"EntityData":{"
Attributes":[{"Base":48,"Modifiers":[{"Operation":1,"UUID":[-1534697145,-419213640,-1671080197,1774861776],"Amount":-0.0074034343,"Name":"Random spawn
bonus"}],"Name":"minecraft:generic.follow_range"},{"Base":0.3,"Modifiers":null,"Name":"minecraft:generic.movement_speed"}]}},{"TicksInHive":390,"EntityData":{"
Attributes":[{"Base":48,"Modifiers":[{"Operation":1,"UUID":[1962122137,-289979547,-1389281492,-367137004],"Amount":-0.06051512,"Name":"Random spawn
bonus"}],"Name":"minecraft:generic.follow_range"},{"Base":0.3,"Modifiers":null,"Name":"minecraft:generic.movement_speed"}]}}]},{"Bees":[{"TicksInHive":503,"Ent
ityData":{"Attributes":[{"Base":48,"Modifiers":[{"Operation":1,"UUID":[-940783886,1447709448,-1767725088,385664109],"Amount":-0.013383434,"Name":"Random spawn
bonus"}],"Name":"minecraft:generic.follow_range"},{"Base":0.3,"Modifiers":null,"Name":"minecraft:generic.movement_speed"}]}},{"TicksInHive":364,"EntityData":{"
Attributes":[{"Base":48,"Modifiers":[{"Operation":1,"UUID":[379455662,-1215346290,-1696347354,-855400929],"Amount":-0.01707336,"Name":"Random spawn
bonus"}],"Name":"minecraft:generic.follow_range"},{"Base":0.3,"Modifiers":null,"Name":"minecraft:generic.movement_speed"}]}}]},{"Bees":[{"TicksInHive":519,"Ent
ityData":{"Attributes":[{"Base":48,"Modifiers":[{"Operation":1,"UUID":[-699739745,-798012115,-1277718758,61184767],"Amount":0.0645359,"Name":"Random spawn
bonus"}],"Name":"minecraft:generic.follow_range"},{"Base":0.3,"Modifiers":null,"Name":"minecraft:generic.movement_speed"}]}},{"TicksInHive":500,"EntityData":{"
Attributes":[{"Base":48,"Modifiers":[{"Operation":1,"UUID":[230179695,1530480144,-1744421406,1349736889],"Amount":-0.01854032,"Name":"Random spawn
bonus"}],"Name":"minecraft:generic.follow_range"},{"Base":0.3,"Modifiers":null,"Name":"minecraft:generic.movement_speed"}]}}]},{"Bees":[{"TicksInHive":512,"Ent
ityData":{"Attributes":[{"Base":48,"Modifiers":[{"Operation":1,"UUID":[-889986075,-561559534,-1540669335,1297470529],"Amount":-0.047952812,"Name":"Random spawn
bonus"}],"Name":"minecraft:generic.follow_range"},{"Base":0.3,"Modifiers":null,"Name":"minecraft:generic.movement_speed"}]}}]}]}

A Real Life Story

RCON

.jsonl

Azure Data Explorer

Azure Data Explorer

• Servizio di analisi dati veloce

• Serivizio totalmente gestito

• Analisi  in  tempo  reale  di  grandi  volumi  di  dati,  provenienti  da

applicazioni, siti web, dispositivi IoT ecc…

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

Azure Data Explorer

Organizzazione dei dati

Simile ai database
relazionali (ex: SqlServer)

Cluster

Database

Table

Schema

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

Azure Data Explorer

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

Azure Data Explorer

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

Azure Data Explorer

Data Ingestion

SDK

Managed
Pipelines

ADX

Connectors
& Plugins

Other Tools

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

Demo

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

Medallion Architecture

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

Azure Data Explorer

Devo pagare un cluster per fare pratica con Kusto?

Azure Data Explorer supporta dei
database “sample” gratuiti su cui è
possibile effettuare delle interrogazioni
per provare

https://dataexplorer.azure.com/home

Azure Data Explorer

Devo pagare un cluster per fare pratica con Kusto?

Kusto Detective Agency: una gamification
per imparare ad usare kusto.

https://detective.kusto.io/

Azure Data Explorer

Serve una mano?

MSFT-ADX@beantech.it

Grazie!

About me

Nicola Paro

Cloud Solutions Architect

beantech

linkedin.com/in/nicolaparo

github.com/nicolaparo
