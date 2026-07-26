# Travel Agent API

## Descrizione del progetto

Travel Agent API è un'applicazione sviluppata in Python utilizzando **FastAPI** e **LangChain**.

Il progetto implementa un assistente AI in grado di gestire diverse richieste relative ai viaggi attraverso l'utilizzo di modelli linguistici e strumenti dedicati.

L'applicazione espone delle API REST che permettono di:

- generare itinerari di viaggio personalizzati;
- fornire informazioni storiche su luoghi ed eventi;
- ricercare voli;
- ricercare hotel.

Il progetto rappresenta il backend dell'applicazione, mentre il frontend è stato fornito separatamente tramite un'applicazione Laravel.

---

# Tecnologie utilizzate

- Python 3
- FastAPI
- LangChain
- OpenAI API
- SerpAPI
- Pydantic
- Poetry
- Uvicorn

---

# Struttura del progetto

```
travel_agent_api/
│
├── routes/
│   └── gestione delle API
│
├── services/
│   └── logica dell'agente AI
│
├── tools/
│   ├── chain_historical_expert.py
│   ├── chain_travel_plan.py
│   ├── flights_finder.py
│   └── hotels_finder.py
│
├── main.py
│
└── ...
```

---

# Installazione

Installare le dipendenze del progetto:

```bash
poetry install
```

Creare un file `.env` contenente le chiavi API necessarie:

```env
OPENAI_API_KEY=YOUR_OPENAI_KEY
SERPAPI_API_KEY=YOUR_SERPAPI_KEY
```

Avviare il server:

```bash
poetry run uvicorn travel_agent_api.main:app --reload --port 8080
```

Una volta avviato il server è possibile accedere alla documentazione Swagger:

```
http://127.0.0.1:8080/docs
```

---

# Funzionalità

Il progetto mette a disposizione diversi strumenti AI:

### Historical Expert

Genera contenuti e spiegazioni approfondite su eventi storici.

---

### Travel Planner

Crea itinerari personalizzati in base a:

- destinazione
- date
- numero di persone
- budget
- stile di viaggio
- attività preferite
- eventuali restrizioni alimentari

---

### Flights Finder

Ricerca voli utilizzando SerpAPI e Google Flights.

---

### Hotels Finder

Ricerca hotel in base ai parametri richiesti dall'utente.

---

# Modifiche apportate

Durante lo svolgimento del progetto sono state apportate alcune modifiche per comprenderne meglio il funzionamento e migliorarne la leggibilità.

Le principali modifiche sono:

- aggiornamento del codice per garantire la compatibilità con le versioni più recenti di LangChain;
- aggiornamento degli import relativi ai Prompt Template;
- aggiunta di messaggi di tracing (`print`) per seguire l'esecuzione del programma durante il debug;
- piccoli interventi di refactoring per rendere il codice più leggibile e organizzato.

---

# Tracing

Per comprendere meglio il flusso di esecuzione dell'applicazione sono stati inseriti diversi messaggi di debug (`print`) all'interno dei tool principali.

Il tracing permette di monitorare:

- avvio dei tool;
- richiesta ricevuta;
- esecuzione delle chiamate al modello AI;
- risposta restituita.

---

# Esempi di utilizzo

## Richiesta di un itinerario

> Vorrei organizzare un viaggio a Roma dal 10 al 15 agosto per due persone con un budget di 1500€.

---

## Ricerca di voli

> Cerco un volo da Milano a Parigi dal 10 al 15 agosto.

---

## Informazioni storiche

> Raccontami la storia dell'antica Roma.

---

# Obiettivo del progetto

L'obiettivo del progetto è comprendere il funzionamento di un agente AI sviluppato con LangChain, integrato con FastAPI e servizi esterni, imparando a costruire strumenti modulari utilizzabili tramite API.

---

# Autore

Progetto realizzato come esercitazione del corso **Coding AI**.

Autore: **Luca Bozzali**