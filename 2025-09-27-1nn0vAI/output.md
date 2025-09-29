Ollama: Local AI for my Raspberry PI

Nicola Paro

SPONSOR

Perché voglio utilizzare un LLM nel mio
software?

Ci serve per davvero

Non è hype e non è «perché lo fanno tutti»

Perché voglio utilizzare un LLM Locale?

E’ davvero per la privacy

I miei dati sono su un server interno.
I miei clienti usano server interni dedicati anche loro.

Lavoro in scenari disconnessi
dal cloud

Che modelli Open Source posso usare in
locale?

gpt-oss deepseek-r1 gemma3 embeddinggemma qwen3 deepseek-v3.1 llama3.1 nomic-embed-text llama3.2 mistral qwen2.5 llama3 phi3 llava gemma2 qwen2.5-coder gemma
mxbai-embed-large qwen phi4 qwen2 llama2 minicpm-v codellama tinyllama dolphin3 olmo2 mistral-nemo llama3.3 llama3.2-vision deepseek-v3 bge-m3 mistral-small
smollm2 llava-llama3 qwq all-minilm mixtral deepseek-coder llama2-uncensored starcoder2 deepseek-coder-v2 codegemma snowflake-arctic-embed phi orca-mini
llama4 qwen2.5vl dolphin-mixtral falcon3 openthinker granite3.1-moe granite3.3 gemma3n phi4-reasoning smollm mistral-small3.2 codestral dolphin-llama3
wizardlm2 cogito dolphin-mistral qwen3-coder magistral phi4-mini deepscaler devstral dolphin-phi command-r hermes3 phi3.5 granite3.2-vision yi deepcoder
zephyr mistral-small3.1 mistral-large moondream wizard-vicuna-uncensored granite-code starcoder deepseek-llm vicuna openchat deepseek-v2 mistral-openorca
codegeex4 openhermes nous-hermes exaone-deep codeqwen qwen2-math snowflake-arctic-embed2 llama2-chinese falcon aya tinydolphin glm4 granite3.2 stable-code
nous-hermes2 opencoder neural-chat wizardcoder command-r-plus bakllava bge-large stablelm2 sqlcoder llama3-chatqa llava-phi3 yi-coder granite3.1-dense
granite3-dense wizard-math reflection llama3-gradient exaone3.5 dbrx r1-1776 dolphincoder samantha-mistral nemotron-mini tulu3 paraphrase-multilingual
starling-lm internlm2 phind-codellama solar xwinlm granite-embedding athene-v2 nemotron llama3-groq-tool-use yarn-llama2 meditron granite3-moe wizardlm-
uncensored aya-expanse llama-guard3 smallthinker wizardlm orca2 medllama2 nous-hermes2-mixtral stable-beluga deepseek-v2.5 reader-lm llama-pro yarn-mistral
command-r7b shieldgemma phi4-mini-reasoning command-a mathstral nexusraven everythinglm codeup marco-o1 stablelm-zephyr solar-pro duckdb-nsql falcon2
magicoder mistrallite codebooga bespoke-minicheck nuextract wizard-vicuna granite3-guardian megadolphin notux open-orca-platypus2 notus sailor2 firefunction-
v2 goliath alfred command-r7b-arabic

Perché IO voglio utilizzare un LLM su una
Raspberry PI?

Ma perché no?

Scelta del
LLM Runner

LLM Runners

Ollama

LM Studio

Foundry Local

Aggiornamenti frequenti,
documentazione chiara.

Interfaccia desktop molto popolare
per chi vuole un’alternativa
“ChatGPT offline”.

Nuovo, ma in rapida crescita: non
ancora “di massa” come Ollama,
ma più solido in ottica enterprise.

API REST semplici
(localhost:11434).

API OpenAI-compatible, quindi
integrabile ovunque senza
cambiare librerie.

API REST e SDK OpenAI-
compatible.

Community enorme (soprattutto
su macOS, ora anche Linux e
Windows).

Ampio uso in community e progetti
personali/produttivi.

Forte spinta da Microsoft,
integrazione con VS Code e
strumenti Azure.

LLM Runners, support by OS

Windows

Linux

Mac

Ollama

Foundry Local

LM Studio

LLM Runners, support by Silicon

CPU (x86, x64)

CPU (ARM)

GPU

NPU

Ollama

Foundry Local

LM Studio

Solo su Windows

Ollama

• Sviluppato da un team

indipendente con
background in AI e
developer tools.

• Obiettivo di rendere

semplice e accessibile
l'esecuzione di LLM in
locale, per una maggiore
privacy, controllo e
autonomia.

Ollama

• 2023 (inizio): Prime versioni interne

• Estate 2023: Lancio pubblico su GitHub con supporto a modelli

GGUF e binari ottimizzati.

• 2024: Integrazione API REST, supporto a GPU e ottimizzazioni

multi-piattaforma. Aggiunta di modelli più recenti come Mistral e
Gemma.

Ollama

Ollama utilizza
container di
modelli LLM (.bin o
.gguf)

Compatibile con
diversi modelli (es:
LLaMA, Mistral,
Gemma...)

Supporta GPU /
CPU a seconda del
sistema

Inferenza locale:
nessun invio dati a
server esterni

Integrazione
semplice: CLI, API
REST

Supporto a modelli
di visione e
modelli tool

Costi dell’AI

Quanto costa Ollama su Raspberry PI?

0.13€ / Million Tokens

(in Italia)

Quanto costa Ollama su Raspberry PI?

Costo input (€/1k
tok)

Costo output (€/1k
tok)

Tokens/sec (tipico)

Costo per 1M tok

GPT-4 (Azure, 8k)

~0,028 €

~0,055 €

~15–30 t/s

GPT-3.5 Turbo
(Azure)

~0,0014 €

~0,0018 €

~50–100 t/s

GPT-4o-mini (Azure)

~0,00014 €

~0,00055 €

~50–100 t/s

~82 €

~1,8 €

~0,7 €

llama3.2:3b (RPi5,
Ollama)

~0,00013–0,00016 €
(energia)

~0,00013–0,00016 €
(energia)

~4–5 t/s

~0,13–0,16 €

Let’s get started!

Hardware

Hardware

• Raspberry PI 5

Praticamente è un mini pc, ma con le GPIO

• 64bit ARM CPU
• 16GB RAM

• MicroSD 64GB (o più)

• Prendete il dissipatore attivo

Software

Download Raspberry Pi Imager on your computer
https://www.raspberrypi.com/software/

Software

Software

Software

Software

Connect via ssh
ssh <user>@<hostname>

Update
sudo apt update && sudo apt upgrade -Y

Update
sudo apt update && sudo apt upgrade -Y

Raspberry Pi Connect gives you free, simple, out-of-the-box access to
your Raspberry Pi from anywhere in the world.

Secure remote access solution for Raspberry Pi OS, allowing you to
connect to your Raspberry Pi desktop and command line directly from
any browser.

VPN?

VPN?

VPN?

Ricapitolando…

• SSH (abilitato di default)

• Impostazione configurabile tramite Raspberry PI Imager

• RPI Connect

• Preinstallato con le ultime versioni, installabile tramite apt
• Connessione «RDP» ed «SSH» alla Raspberry via browser

• Tailscale

• Zero configuration VPN per creare una rete locale con tutti i device all’interno

dei quali è installato

Installiamo .NET

Installiamo .NET
curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin --channel STS

echo 'export DOTNET_ROOT=$HOME/.dotnet' >> ~/.bashrc
echo 'export PATH=$PATH:$HOME/.dotnet' >> ~/.bashrc
source ~/.bashrc

dotnet --version

Installiamo .NET

Installiamo Ollama

Installiamo Ollama

Installiamo Ollama

Orchestratori

Orchestratori

Permettono di combinare modelli linguistici con codice, strumenti
esterni, memoria e flussi logici.

Facilitano la creazione di agenti che possono pianificare, ragionare e
agire in modo autonomo.

Offrono librerie e componenti per integrare modelli come GPT, Mistral,
Claude, ecc. in app reali.

Orchestratori

Semantic Kernel

LangChain

Orchestratori

Linguaggi supportati

C#, Python, Java

Python, JavaScript

Filosofia

Plugin modulari + pianificatori

Catene di chiamate + agenti

Memoria

Embedding + contesto persistente

Memoria conversazionale

Integrazione

Forte con Azure e Microsoft

Ampia con strumenti esterni

Target

Aziende, sviluppatori enterprise

Ricercatori, startup, maker

Use case ideali

Copilot aziendali, workflow complessi

Chatbot, tool AI interattivi

Però …

• Semantic Kernel non è ottimizzato per ambienti con risorse limitate

come Raspberry Pi 5.

• Il suo motore di pianificazione e gestione dei plugin può generare

prompt complessi e lunghi

• Questo comporta errori di esecuzione, rallentamenti o incompatibilità

con modelli ottimizzati per dispositivi ARM.

• Per applicazioni su Raspberry:

• framework più snelli
• interfacce dirette con modelli

Orchestratori

Linguaggi supportati

C#, Python, Java

Python, JavaScript

Filosofia

Plugin modulari + pianificatori

Catene di chiamate + agenti

Memoria

Embedding + contesto persistente

Memoria conversazionale

Integrazione

Forte con Azure e Microsoft

Ampia con strumenti esterni

Target

Aziende, sviluppatori enterprise

Ricercatori, startup, maker

Use case ideali

Copilot aziendali, workflow complessi

Chatbot, tool AI interattivi

La soluzione?

Metodo Coleman

Co’ le man me lo faccio da solo [cit. Massimo Bonanni]

Scelta dei modelli

Scelta dei modelli
https://ollama.com/search

Capabilities

Numero di Parametri

Scelta dei modelli – Numero di Parametri

Pochi Parametri

Tanti Parametri

• Velocità di risposta
• Allucinazioni

• Accuratezza della risposta
• Consumo di energia
• Consumo di memoria

Scelta dei modelli – Numero di Parametri

Ollama, Ollama

Yes, papa

Eating RAM?

No, papa

Telling lies?

No, papa

Open your mouth

Scelta dei modelli – Numero di Parametri

Tutto il modello viene
caricato in RAM

Scelta dei modelli – Capabilities

• Embedding

• Modelli che generano vettori numerici per rappresentare testi, utili in ricerca

semantica, raccomandazioni e clustering.

• Vision

• Modelli capaci di analizzare immagini, riconoscere contenuti visivi e

combinarli con testo.

• Thinking

• Modelli progettati per un ragionamento più accurato e passo-per-passo,

ottimizzati per compiti complessi.

• Tools

• Modelli che possono usare strumenti esterni (API, funzioni, calcoli) oltre al

testo.

Cosa sono i Tools?

• Un tool è una funzionalità esterna che il modello può attivare per

svolgere compiti specifici che vanno oltre la semplice generazione di
testo.

• I tools permettono al modello di interagire con il mondo esterno o di
eseguire operazioni complesse che richiedono capacità specifiche.

Come funziona un tool?
(Flusso normale senza tools)

Ah ah! Non lo sa!

«Che tempo fa a PN?»

«Che tempo fa a PN?»

User

«Ma io che ne so, scusi?»

Application

«Ma io che ne so, scusi?»

LLM

Come funziona un tool?
(Flusso normale con i tool)

Ah però! Questo
assistente è
davvero
intelligente!

Internet

«Che tempo fa a PN?»

User

«A pordenone …»

Application

«Che tempo fa a
«A pordenone è
PN?»
soleggiato, con una
Tools:
SUNNY, 26°C
getWeather(«PN»)
temperatura di 26 °C
getWeather(location)
»
searchWiki(what)

LLM

Quindi che modello scelgo?

• Llama3.1 o 3.2

• Dalla mia personale esperienza, i modelli llama3.1 e llama3.2

hanno un forte bias nei confronti dei tool, preferendone
l’invocazione anche se non sono realmente richiesti.

• Gemma 3

• Qualità nella risposta, ma non supporta i tools

• Qwen2.5:3b

• Modello leggero e abbastanza preciso per le sue dimensioni
• Le invocazioni dei tool avvengono tendenzialmente quando

sono realmente necessarie

DEMO

La soluzione implementata

Orchestrator

Get Weather Tool

Nominatim

Open Meteo
APIWiki Search Tool
API

Wikipedia
API

Light Tool

Ollama w/
Gemma3
270m

Ollama w/
Qwen2.5:3b

Conclusioni

Conclusioni

• Il «fai da te» da sempre le sue soddisfazioni

• Ho imparato ad avere a che fare con un ambiente più «ostile» rispetto al mio

use case solito: risorse limitate, surriscaldamento della scheda

• Anche se sono un informatico, le lezioni di elettronica del liceo mi

sono servite

• Mettere un LLM in un ambiente così limitato, come la Raspberry PI,

non ha molto senso

Piuttosto…

Piuttosto… MCP

«Accendi la luce»

User

MCP

GRAZIE!

About me

Nicola Paro

Solutions Architect @ beanTech

.NET & Azure Meetup Štajerska Community Lead

codice

https://www.linkedin.com/in/nicolaparo/


