# SQLingo

Ask your data a question in plain English — get back a real SQL query and live results. No SQL knowledge required.

**Live demo:** https://parth033.github.io/SQLingo/

## What it does

SQLingo turns a natural-language question into a safe, read-only SQL query and runs it instantly in your browser — no backend server required.

1. Type a question like *"which department has the highest average salary?"*
2. An AI model converts it into SQL, using the schema of your current dataset
3. The query is checked to make sure it's a plain `SELECT` — anything else is blocked before it runs
4. It executes against an in-browser SQL engine and the results show up as a table

## Features

- **Demo Data mode** — a ready-made `employees` and `sales` dataset to try immediately
- **Upload CSV mode** — load your own CSV and query it the same way
- **External DB tab** — a UI mockup showing how connecting a real MySQL/Postgres database would work in production (requires a backend, explained in the app)
- **Multiple AI providers** — switch between Google Gemini, Groq, or (inside a Claude preview) Claude, depending on what you have a free key for
- **Read-only safety layer** — `INSERT`, `UPDATE`, `DELETE`, `DROP`, `ALTER`, and similar statements are blocked before execution
- **Runs entirely client-side** — the whole app is a single HTML file with no build step and no server

## Getting started

Since this is a single static HTML file, there's nothing to install.

### Try it online
Open the [live demo](https://parth033.github.io/SQLingo/) and start asking questions using the Demo Data tab.

### Run it locally
Clone this repo and open `index.html` directly in your browser:
```bash
git clone https://github.com/Parth033/SQLingo.git
cd SQLingo
open index.html   # or just double-click the file
```

### Setting up an AI provider
The app needs an AI model to translate your question into SQL. Tap **⚙ AI provider** in the app to choose one:

| Provider | Cost | Get a key |
|---|---|---|
| Google Gemini | Free tier | [aistudio.google.com/apikey](https://aistudio.google.com/apikey) |
| Groq | Free tier, no card | [console.groq.com/keys](https://console.groq.com/keys) |

Your key is only kept in your browser tab's memory for that session — it's never saved to disk or sent anywhere except directly to the provider you chose.

## Tech stack

- Vanilla HTML/CSS/JavaScript — no framework, no build step
- [alasql](https://github.com/agershun/alasql) — in-browser SQL engine
- Google Gemini API / Groq API — natural language → SQL translation

## Roadmap

- [ ] Full backend (Flask + SQLAlchemy) to support real external database connections
- [ ] Query history
- [ ] Support for more file types (Excel, JSON)

## Author

**Parth Agarwal**
- GitHub: [@Parth033](https://github.com/Parth033)
- LinkedIn: [parth-agarwal](https://linkedin.com/in/parth-agarwal-587b942a3)
