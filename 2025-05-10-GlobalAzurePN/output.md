Gestisci il deployment su Azure…

…con Minecraft?

Nicola Paro

SPONSORS

A real life story…

• Virtual Buildings è un’azienda specializzata nella realizzazione di

applicazioni cloud based su Azure.

• Sviluppa un software custom per Acme S.p.A.,
• Applicativo cloud based e, per tenere bassi i costi, Virtual

Buildings lo ha realizzato utilizzando i tier minimi di tutti i servizi
Azure.

•

L’applicazione inizialmente si comporta in modo regolare ma
dopo alcune settimane comincia ad essere meno performante.
• Con l’avanzare del tempo, anche l’applicazione diventa sempre
più lenta e le operazioni iniziano a fallire per via dei numerosi
timeout e throttlings

• Nessuno ha pensato allo scaling e a come gestirlo

automaticamente

Come possiamo fare?

Soluzioni
tramite UI

Soluzioni da
riga di
comando

Infrastructure
as code
dichiarativo

AZ PowerShell Module

Set of cmdlets for
managing Azure
resources.

Built on .NET and
works in
PowerShell
environments.

Enables scripting
and automation of
tasks.

AZ PowerShell Module

Install from PowerShell Gallery

Install-Module -Name Az -AllowClobber -Scope CurrentUser

Regular updates via

Update-Module -Name Az

AZ PowerShell Module – Getting Started

Connect-AzAccount

Connect-AzAccount `

-ServicePrincipal `
-Tenant <tenantId> `
-ApplicationId <appId> `
-Credential (Get-Credential)

AZ PowerShell Module - Esempi

Resource Management
Get-AzResource, New-AzResourceGroup

Virtual Machines
New-AzVM, Start-AzVM, Stop-AzVM

Storage
Get-AzStorageAccount, New-AzStorageContainer

Networking
Get-AzVirtualNetwork, New-AzPublicIpAddress

AZ CLI

• Azure CLI (Command-Line Interface) is a set of commands used to create and manage Azure resources.
• Cross-platform: works on Windows, macOS, and Linux.
• Available as open source here → https://github.com/Azure/azure-cli

Scriptable and
automatable

Faster
resource
management

Integrated
with Azure
Cloud Shell

Works with
CI/CD tools

AZ CLI – Getting Started

az login

az login -u <username> -p <password>

az login --service-principal -u <appId> -p <password> --tenant <tenant>

AZ CLI - Esempi

Resource Group
az group create --name MyGroup --location eastus

VM Creation
az vm create --resource-group MyGroup --name MyVM --image UbuntuLTS

Storage Account
az storage account create --name mystorage --resource-group MyGroup --
location eastus --sku Standard_LRS

Combine commands in bash, PowerShell, or batch scripts.
az vm list --query "[].{Name:name, ResourceGroup:resourceGroup}" --output
table

AZ CLI vs Azure PowerShell Module

Criteria

Azure CLI

Azure PowerShell Module

Platform & Shell

Designed for Bash, great for Linux/macOS

Native to PowerShell (Windows-first)

Syntax Simplicity

JSON-style, more concise and readable

Verb-Noun format (e.g., Get-AzVM)

Learning Curve

Easier for non-Windows admins or developers

Steeper if unfamiliar with PowerShell

Scripting Language

Shell scripts, Bash, etc.

PowerShell scripts (.ps1)

Cloud Shell Default

Default in Azure Cloud Shell

Also available, but not default

Output Formats

Built-in JSON, Table, TSV, YAML

JSON, but more verbose by default

Cross-Platform Usage

Uniform experience across Operative Systems

Slight variation in behavior

Community Examples

More online tutorials & templates in CLI

PowerShell examples often Windows-specific

AZ CLI

Gestione del deployment con un
Polyglot Notebook

Utile se nel bel mezzo del deploy sono
da configurare anche le risorse appena
create

ARM Templates

• È un file in formato JSON utilizzato per definire e distribuire risorse in Microsoft Azure.

• Fa parte del modello Infrastructure as Code (IaC), che consente la gestione dell’infrastruttura tramite codice.

• È dichiarativo: si descrive lo stato desiderato delle risorse, non i passaggi per arrivarci.

• Gestito tramite Azure Resource Manager (ARM), il motore di provisioning delle risorse in Azure.

ARM Templates

Consistenza

Ripetibilità

Automazione

 Le risorse vengono
distribuite nello stesso
modo ogni volta.

Facilmente riutilizzabili
in ambienti diversi (dev,
test, prod).

Integrabili in pipeline
CI/CD per il
provisioning continuo.

Controllo

Sicurezza

Specifiche chiare e
valide dei componenti
da distribuire.

Puoi collegarli ad Azure
Key Vault per gestire
segreti e chiavi.

ARM Templates

• $schema – URL allo schema JSON di

•

riferimento.
contentVersion – Versione del template
(formato: "1.0.0.0").

• parameters – Valori di input dinamici forniti al

•

•

template.
variables – Valori riutilizzabili interni al
template.
resources – Risorse da creare o aggiornare
(VM, storage, rete, ecc.).

• outputs – Informazioni restituite al termine del

deployment.

{

"$schema":

"https:--schema.management.azure.com/sche
mas/2019-04-01/deploymentTemplate.json#",

"contentVersion": "1.0.0.0",
"parameters": {},
"variables": {},
"resources": [],
"outputs": {}

}

{

"$schema": "https://schema.management.azure.com/schemas/2019-04-

ARM Templates

01/deploymentTemplate.json#",

"contentVersion": "1.0.0.0",
"parameters": {

"location": {

"type": "string",
"defaultValue": "westeurope"

Parametri

},
"storageAccountName": {
"type": "string"

},
"webAppName": {

"type": "string"

},
"sqlServerName": {

"type": "string"

},
"sqlAdminUser": {

"type": "string"

},
"sqlAdminPassword": {

"type": "securestring"

},
"sqlDbName": {

"type": "string",
"defaultValue": "mydb"

},
"appServicePlanName": {

"type": "string",
"defaultValue": "myAppServicePlan"

}

},
"variables": {

"sqlConnectionString": "[concat('Server=tcp:', parameters('sqlServerName'),

'.database.windows.net,1433;Initial Catalog=', parameters('sqlDbName'), ';Persist
Security Info=False;User ID=', parameters('sqlAdminUser'), ';Password=',
parameters('sqlAdminPassword'),
';MultipleActiveResultSets=False;Encrypt=True;TrustServerCertificate=False;Connection
Timeout=30;')]"

"resources": [

},

{

"type": "Microsoft.Storage/storageAccounts",

"apiVersion": "2022-09-01",

"name": "[parameters('storageAccountName')]",

"location": "[parameters('location')]",

"sku": {

},

"name": "Standard_LRS"

"kind": "StorageV2",

"properties": {}

"type": "Microsoft.Sql/servers",

"apiVersion": "2022-02-01-preview",

"name": "[parameters('sqlServerName')]",

"location": "[parameters('location')]",

"properties": {

}

},

{

},

{

},

{

},

{

"administratorLogin": "[parameters('sqlAdminUser')]",

"administratorLoginPassword": "[parameters('sqlAdminPassword')]",

"version": "12.0"

"type": "Microsoft.Sql/servers/databases",

"apiVersion": "2022-02-01-preview",

"name": "[format('{0}/{1}', parameters('sqlServerName'),

parameters('sqlDbName'))]",

"location": "[parameters('location')]",

"[resourceId('Microsoft.Sql/servers', parameters('sqlServerName'))]"

"dependsOn": [

],

"properties": {}

"sku": {

"name": "F1",

"tier": "Free"

},

"properties": {}

"type": "Microsoft.Web/serverfarms",

"apiVersion": "2022-03-01",

"name": "[parameters('appServicePlanName')]",

"location": "[parameters('location')]",

"type": "Microsoft.Web/sites",

"apiVersion": "2022-03-01",

"name": "[parameters('webAppName')]",

"location": "[parameters('location')]",

"dependsOn": [

"[resourceId('Microsoft.Web/serverfarms',

parameters('appServicePlanName'))]",

"[resourceId('Microsoft.Storage/storageAccounts',

parameters('storageAccountName'))]",

parameters('sqlServerName'), parameters('sqlDbName'))]"

"[resourceId('Microsoft.Sql/servers/databases',

],

"properties": {

parameters('appServicePlanName'))]",

"siteConfig": {

"appSettings": [

"serverFarmId": "[resourceId('Microsoft.Web/serverfarms',

"name": "STORAGE_CONNECTION_STRING",

"value":

"[concat('DefaultEndpointsProtocol=https;AccountName=',

parameters('storageAccountName'), ';AccountKey=',

listKeys(resourceId('Microsoft.Storage/storageAccounts',

parameters('storageAccountName')), '2022-09-01').keys[0].value,

';EndpointSuffix=core.windows.net')]"

"name": "SQL_CONNECTION_STRING",

"value": "[variables('sqlConnectionString')]"

{

},

{

}

]

}

}

}

]

}

{

"$schema": "https://schema.management.azure.com/schemas/2019-04-

01/deploymentTemplate.json#",

"contentVersion": "1.0.0.0",

"parameters": {

"location": {

"type": "string",

"defaultValue": "westeurope"

},

},

},

},

},

},

},

"storageAccountName": {

"type": "string"

"webAppName": {

"type": "string"

"sqlServerName": {

"type": "string"

"sqlAdminUser": {

"type": "string"

"sqlAdminPassword": {

"type": "securestring"

"sqlDbName": {

"type": "string",

"defaultValue": "mydb"

"appServicePlanName": {

"type": "string",

"defaultValue": "myAppServicePlan"

}

},

"variables": {

"sqlConnectionString": "[concat('Server=tcp:', parameters('sqlServerName'),

'.database.windows.net,1433;Initial Catalog=', parameters('sqlDbName'), ';Persist

Security Info=False;User ID=', parameters('sqlAdminUser'), ';Password=',

parameters('sqlAdminPassword'),

';MultipleActiveResultSets=False;Encrypt=True;TrustServerCertificate=False;Connection

Timeout=30;')]"

},
"resources": [

{

ARM Templates

Risorse

"type": "Microsoft.Storage/storageAccounts",
"apiVersion": "2022-09-01",
"name": "[parameters('storageAccountName')]",
"location": "[parameters('location')]",
"sku": {

"name": "Standard_LRS"

},
"kind": "StorageV2",
"properties": {}

},
{

"type": "Microsoft.Sql/servers",
"apiVersion": "2022-02-01-preview",
"name": "[parameters('sqlServerName')]",
"location": "[parameters('location')]",
"properties": {

"administratorLogin": "[parameters('sqlAdminUser')]",
"administratorLoginPassword": "[parameters('sqlAdminPassword')]",
"version": "12.0"

}

},
{

"type": "Microsoft.Sql/servers/databases",
"apiVersion": "2022-02-01-preview",
"name": "[format('{0}/{1}', parameters('sqlServerName'),

parameters('sqlDbName'))]",

"location": "[parameters('location')]",
"dependsOn": [

"[resourceId('Microsoft.Sql/servers', parameters('sqlServerName'))]"

],
"properties": {}

},
{

},

{

"type": "Microsoft.Web/serverfarms",
"apiVersion": "2022-03-01",
"name": "[parameters('appServicePlanName')]",
"location": "[parameters('location')]",

"sku": {

"name": "F1",

"tier": "Free"

},

"properties": {}

"type": "Microsoft.Web/sites",

"apiVersion": "2022-03-01",

"name": "[parameters('webAppName')]",

"location": "[parameters('location')]",

"dependsOn": [

"[resourceId('Microsoft.Web/serverfarms',

parameters('appServicePlanName'))]",

"[resourceId('Microsoft.Storage/storageAccounts',

parameters('storageAccountName'))]",

parameters('sqlServerName'), parameters('sqlDbName'))]"

"[resourceId('Microsoft.Sql/servers/databases',

],

"properties": {

parameters('appServicePlanName'))]",

"siteConfig": {

"appSettings": [

"serverFarmId": "[resourceId('Microsoft.Web/serverfarms',

"name": "STORAGE_CONNECTION_STRING",

"value":

"[concat('DefaultEndpointsProtocol=https;AccountName=',

parameters('storageAccountName'), ';AccountKey=',

listKeys(resourceId('Microsoft.Storage/storageAccounts',

parameters('storageAccountName')), '2022-09-01').keys[0].value,

';EndpointSuffix=core.windows.net')]"

"name": "SQL_CONNECTION_STRING",

"value": "[variables('sqlConnectionString')]"

{

},

{

}

]

}

}

}

]

}

ARM Templates – Funzioni

Funzione

Descrizione

Esempio

base64(string)
uri(base, path)
coalesce(a, b, ...)
empty(value)
if(cond, trueVal, falseVal)
equals(a, b)
not(bool)
and(bool1, bool2)
or(bool1, bool2)
concat(a, b, ...)
format(formatStr, ...)
toLower(str)
toUpper(str)
replace(str, old, new)
substring(str, start, len)
guid(val1, val2, ...)
contains(array, value)
length(array|string)
first(array)
last(array)
union(array1, array2)
intersection(array1, array2)
resourceId(type, name, ...)
subscription()
tenant()
deployment()
reference(resourceId, apiVersion)
listKeys(resourceId, apiVersion)

Codifica in base64
Combina base URL con path
Primo valore non null
Controlla se stringa/array è vuoto
Valutazione condizionale
Confronta due valori
Negazione logica
AND logico
OR logico
Concatena stringhe
Formatta stringhe con placeholder {0}
Minuscolo
Maiuscolo
Sostituisce porzioni di stringa
Estrae parte della stringa
Genera GUID deterministico da input
Controlla se array/oggetto contiene elemento
Lunghezza array o stringa
Primo elemento dell’array
Ultimo elemento
Unione di due array
Elementi comuni
ID risorsa Azure
Info sulla sottoscrizione
Info sul tenant
Info sul deployment corrente
Ottiene proprietà di una risorsa già deployata
Recupera chiavi di accesso

"[base64('abc')]"
"[uri('https:--site.com', 'api/values')]"
"[coalesce(null, '', 'val')]" → ""
"[empty('')]" → true
"[if(equals(parameters('env'), 'prod'), 'Standard', 'Basic')]"
"[equals('a', 'b')]"
"[not(true)]"
"[and(true, false)]"
"[or(false, true)]"
"[concat('https:--', parameters('name'))]"
"[format('{0}/{1}', 'abc', 'def')]"
"[toLower('Hello')]" → hello
"[toUpper('abc')]" → ABC
"[replace('abc123', '123', 'XYZ')]"
"[substring('abcdef', 1, 3)]" → bcd
"[guid('site1', 'slot1')]"
"[contains(parameters('features'), 'logging')]"

"[first(parameters('items'))]"
"[last(parameters('items'))]"
"[union(array1, array2)]"
"[intersection(array1, array2)]"
"[resourceId('Microsoft.Web/sites', 'mySite')]"
"[subscription().subscriptionId]"
"[tenant().tenantId]"
"[deployment().name]"
"[reference(resourceId(.--), '2021-01-01')]"
"[listKeys(resourceId(.--), '2022-09-01').keys[0].value]"

https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/template-functions

ARM Templates – How to Deploy?

• Azure Portal

• Azure CLI

az deployment group create --resource-group mioGruppo --template-file
template.json --parameters @parametri.json

• PowerShell

New-AzResourceGroupDeployment -ResourceGroupName "mioGruppo" -TemplateFile
"template.json" -TemplateParameterFile "parametri.json"

• Azure DevOps / GitHub Actions

Integrazione in pipeline CI/CD per deployment automatici.

ARM Templates – Best Practices

• Utilizzare parametri per valori dinamici (es. nomi, posizioni, SKU).

• Definire variabili per evitare ripetizioni.

• Validare i template con az deployment validate

• Separare le logiche in template modulari (linked templates).

• Usare Azure Key Vault per gestire segreti e credenziali.

Bicep

Bicep è un linguaggio dichiarativo di Infrastructure as Code (IaC) per Azure, pensato come alternativa più

leggibile e moderna agli ARM template JSON

Bicep

{

…
"parameters": {

"location": {

"type": "string",
"defaultValue": "westeurope"

},
"storageAccountName": { "type": "string" },
"webAppName": { "type": "string" },
"sqlServerName": { "type": "string" },
"sqlAdminUser": { "type": "string" },
"sqlAdminPassword": { "type": "securestring" },
"sqlDbName": { "type": "string", "defaultValue": "mydb" },
"appServicePlanName": {
"type": "string",
"defaultValue": "myAppServicePlan"

}

},
…

}

param location string = 'westeurope'
param storageAccountName string
param webAppName string
param sqlServerName string
param sqlAdminUser string
@secure()
param sqlAdminPassword string
param sqlDbName string = 'mydb'
param appServicePlanName string = 'myAppServicePlan'

Bicep

{

…
"variables": {

"storageConnectionString":

"[concat('DefaultEndpointsProtocol=https;AccountName=',
parameters('storageAccountName'), ';AccountKey=',
listKeys(resourceId('Microsoft.Storage/storageAccounts',
parameters('storageAccountName')), '2022-09-01').keys[0].value,
';EndpointSuffix=core.windows.net')]",

"sqlConnectionString": "[concat('Server=tcp:',

parameters('sqlServerName'),
'.database.windows.net,1433;Initial Catalog=',
parameters('sqlDbName'), ';Persist Security Info=False;User
ID=', parameters('sqlAdminUser'), ';Password=',
parameters('sqlAdminPassword'),
';MultipleActiveResultSets=False;Encrypt=True;TrustServerCertif
icate=False;Connection Timeout=30;')]"

},
…

}

var storageKeys = listKeys(storage.id, storage.apiVersion)

var storageConnectionString =
'DefaultEndpointsProtocol=https;AccountName=${storageAccountNam
e};AccountKey=${storageKeys.keys[0].value};EndpointSuffix=core.
windows.net'

var sqlConnectionString =
'Server=tcp:${sqlServerName}.database.windows.net,1433;Initial
Catalog=${sqlDbName};Persist Security Info=False;User
ID=${sqlAdminUser};Password=${sqlAdminPassword};MultipleActiveR
esultSets=False;Encrypt=True;TrustServerCertificate=False;Conne
ction Timeout=30;'

Bicep

{

…
"resources": [

"type": "Microsoft.Storage/storageAccounts",
"apiVersion": "2022-09-01",
"name": "[parameters('storageAccountName')]",
"location": "[parameters('location')]",
"sku": { "name": "Standard_LRS" },
"kind": "StorageV2",
"properties": {}

{

}

]
…

}

resource storage 'Microsoft.Storage/storageAccounts@2022-09-01' = {

name: storageAccountName
location: location
sku: {

name: 'Standard_LRS'

}
kind: 'StorageV2'
properties: {}

}

Bicep – How to Deploy?

Esattamente come se fosse un ARM template, solo che invece che essere un file «.json» è un file «.bicep»:

• Azure Portal

• Azure CLI

az deployment group create --resource-group mioGruppo --template-file
template.bicep --parameters @parametri.json

• PowerShell

New-AzResourceGroupDeployment -ResourceGroupName "mioGruppo" -TemplateFile
"template.bicep" -TemplateParameterFile "parametri.json"

• Azure DevOps / GitHub Actions

Integrazione in pipeline CI/CD per deployment automatici.

A confronto

Interfaccia

Grafica

Riga di comando
(PowerShell)

Riga di comando
(bash/cmd)

{ } JSON dichiarativo

DSL dichiarativa (semplificata
per ARM)

Facilità d'uso

Alta per principianti

Automazione

Limitata

Controllo versione

Modularità e riuso

Validazione prima del deploy

Complessità gestibile

Dipendenze tra risorse

Bassa

Manuali

Media

Elevata

Limitata

Parziale

Media

Manuali

Media

Elevata

Bassa (complesso e verboso)

Media/Alta (più leggibile di
ARM)

Elevata

Elevata

Limitata

Supportata ma complicata

Parziale

Media

Manuali

Alta

Media

Supportate

Supportate (semplificate)

Deploy ripetibili/idempotenti

Parzialmente

Parzialmente

Supporto CI/CD

Limitato

Conversione in ARM

Nativo

 (compila in ARM JSON)

API

Azure Resource Manager
API

ARM API

•

•

Le API di ARM sono basate su REST e permettono di interagire programmaticamente con tutte le risorse di

Azure.

L'endpoint di base è: https://management.azure.com/.

• Principali operazioni supportate:

• GET: Recupero di informazioni sulle risorse

• POST: Creazione di nuove risorse

• PUT: Aggiornamento di risorse esistenti

• DELETE: Rimozione di risorse

•

Le API sono versionate per mantenere la retrocompatibilità.

ARM API

curl -X PUT \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  --data @template.json \
  "https:--management.azure.com/subscriptions/<subscription-
id>/resourceGroups/<resource-
group>/providers/Microsoft.Compute/virtualMachines/<vm-name>?api-
version=2022-03-01"

API

Azure Resource Manager
API

API

& SDK

Azure Resource Manager
API

SDK C#

Libreria client ufficiale di
Microsoft per gestire le risorse
di Azure in modo
programmatico tramite codice
C#.

Azure.Identity utilizzata per la
parte di autenticazione.

Azure.ResourceManager
contiene le funzionalità di base
e la gestione dei resource
groups.

Per ogni risorsa Azure è
necessario il pacchetto nuget
corrispondente

SDK C# - Setup

var credential = new ___AzureCredential();

var client = new ArmClient(credential);

SDK C# - Setup

Descrizione

Pro

Contro

DefaultAzureCredential

Tenta diverse credenziali in ordine predefinito
(locale, ambienti, gestite)

Facile da usare, ideale per ambienti dev →
prod

Possibile ambiguità se più metodi sono
configurati

EnvironmentCredential

Usa variabili di ambiente per client ID, secret e
tenant

Sicura e automatizzabile in ambienti CI/CD

Richiede setup accurato delle variabili

ManagedIdentityCredential

Usa l'identità gestita assegnata alla risorsa Azure
(VM, App Service, ecc.)

Nessuna gestione segreti, molto sicura

Funziona solo in ambienti Azure con
identità gestita abilitata

InteractiveBrowserCredential Apre un browser per login interattivo dell’utente

Utile per strumenti locali o CLI personalizzati

VisualStudioCredential

Usa il login configurato in Visual Studio

AzureCliCredential

Usa il token della sessione az login

Ottimo per sviluppatori che usano Visual
Studio
Perfetto per sviluppo locale, integrato con
CLI

AzurePowerShellCredential Usa il contesto di login da Connect-AzAccount

Utile in ambienti PowerShell e script

Non adatto ad ambienti automatizzati o
headless

Limitato a chi ha l’IDE installato e
configurato
Richiede che l’utente abbia effettuato az
login
Dipende dal contesto PowerShell
configurato

ClientSecretCredential

Usa ID applicazione, secret e tenant per
l’autenticazione

Adatto a produzione, automatizzabile

Richiede gestione sicura dei segreti

ClientCertificateCredential

Come sopra, ma usa un certificato al posto del
secret

Più sicura del secret, usata spesso in scenari
enterprise

Richiede gestione certificato
(caricamento, validità, ecc.)

ChainedTokenCredential

Permette di combinare più credenziali in ordine di
fallback

Flessibile, personalizzabile

Richiede configurazione esplicita della
catena

SDK C# - Setup

Descrizione

Pro

Contro

DefaultAzureCredential

Tenta diverse credenziali in ordine predefinito
(locale, ambienti, gestite)

Facile da usare, ideale per ambienti dev →
prod

Possibile ambiguità se più metodi sono
configurati

DefaultAzureCredential

EnvironmentCredential

Usa variabili di ambiente per client ID, secret e
tenant

Sicura e automatizzabile in ambienti CI/CD

Richiede setup accurato delle variabili

ManagedIdentityCredential

Usa l'identità gestita assegnata alla risorsa Azure
(VM, App Service, ecc.)

Nessuna gestione segreti, molto sicura

1. EnvironmentCredential

InteractiveBrowserCredential Apre un browser per login interattivo dell’utente

Utile per strumenti locali o CLI personalizzati

VisualStudioCredential

AzureCliCredential

Usa il login configurato in Visual Studio

2. ManagedIdentityCredential

Usa il token della sessione az login

3. VisualStudioCredential

Ottimo per sviluppatori che usano Visual
Studio
Perfetto per sviluppo locale, integrato con
CLI

AzurePowerShellCredential Usa il contesto di login da Connect-AzAccount

Utile in ambienti PowerShell e script

Funziona solo in ambienti Azure con
identità gestita abilitata

Non adatto ad ambienti automatizzati o
headless

Limitato a chi ha l’IDE installato e
configurato
Richiede che l’utente abbia effettuato az
login
Dipende dal contesto PowerShell
configurato

4. AzureCliCredential

Usa ID applicazione, secret e tenant per
l’autenticazione

ClientSecretCredential

ClientCertificateCredential

Come sopra, ma usa un certificato al posto del
secret

Più sicura del secret, usata spesso in scenari
enterprise

Richiede gestione certificato
(caricamento, validità, ecc.)

5.

InteractiveBrowserCredential

Adatto a produzione, automatizzabile

Richiede gestione sicura dei segreti

ChainedTokenCredential

Permette di combinare più credenziali in ordine di
fallback

Flessibile, personalizzabile

Richiede configurazione esplicita della
catena

SDK C#

var subscription = await armClient.GetDefaultSubscriptionAsync();

var rgData = new ResourceGroupData(AzureLocation.WestEurope);
var rg = await subscription.GetResourceGroups().CreateOrUpdateAsync("myRg", rgData);

var existingRg = await subscription.GetResourceGroups().GetAsync("myRg");

Posso usare quello che voglio per gestire il
Deployment su Azure…

… Anche Minecraft?

Nelle puntate precedenti

Minecraft per gestire Azure

RCON

SDK

Minecraft per gestire Azure

RCON

STD IN/OUT

SDK

AZ CLI

DEMO

Grazie!

About me

Nicola Paro
Cloud Solution Architect
beanTech

linktr.ee/nicolaparo

Codice della demo → https://github.com/nicolaparo/AzureCraft
