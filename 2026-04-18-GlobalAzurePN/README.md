# GlobalAzurePN

## Main Topics Covered
- Dal codice al container
- Docker e Azure Container Registry in pratica Nicola Paro
- SPONSOR
- «Non funziona niente»
- Più modi di deployare
- Tempi di avvio Spazio Occupato CPU e RAM

## Key Takeaways and Conclusions
- È la ricetta che dice a Docker come costruire un’immagine. una descrizione dichiarativa di come nasce un ambiente uno standard ripetibile e versionabile Durante la build, docker legge il Dockerfile dall’alto verso il basso, esegue ogni istruzione in sequenza e crea una immagine finale immutabile
- Un’immagine docker è costituita da Layers Un layer è una modifica immutabile del filesystem Ogni layer rappresenta: un’aggiuntauna rimozioneo una modifica ai file L’immagine finale è la somma ordinata dei layer Perché servono i layers? Caching (velocità) Riutilizzo tra immagini Immutabilità

## Notes
- Event folder: 2026-04-18-GlobalAzurePN
- Source deck: presentation.pptx
- Date: 2026-04-18
