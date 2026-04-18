# NetSaturday

## Main Topics Covered
- Quanto sappiamo (davvero) della Dependency Injection?
- Nicola Paro
- Sponsor
- A real life story…
- Il problema di fondo…
- Una classe che crea direttamente le proprie dipendenze gestisce quello che usa invece che quello di cui ha bisogno

## Key Takeaways and Conclusions
- Normalmente, il container DI crea automaticamente le istanze risolvendo tutte le dipendenze dal servizio registrato. Tuttavia, a volte potremmo voler creare un'istanza di una classe dove solo alcuni parametri del costruttore sono gestiti dal container, mentre altri li passiamo esplicitamente. i valori in parameters vengono abbinati in ordine ai parametri del costruttore che non possono essere risolti dal container. viene scelto il costruttore pubblico con il maggior numero di parametri che può essere soddisfatto (combinando servizi risolti + parametri forniti). Se nessun costruttore è compatibile  InvalidOperationException. Utile quando non vuoi registrare un tipo nel container, ma comunque sfruttare il DI per alcune sue dipendenze.

## Notes
- Event folder: 2026-01-31-NetSaturday
- Source deck: nicolaparo-netsaturday2026.pptx
- Date: 2026-01-31
