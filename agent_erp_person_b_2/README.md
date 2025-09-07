
# Mohamad Orabi — Domain Agents (Sales & Finance) — Minimal MVP

This package contains a simple, dependency‑light implementation of Sales and Finance domain agents and their tools.

## How to run
```bash
# 1) Create the SQLite DB from seed
python db/init_db.py
# 2) Run a tiny end‑to‑end demo
python workflows/run_workflows.py
```

## What happens
1) Add a lead -> 2) Score it (heuristic) -> 3) Convert to order -> 4) Generate invoice -> 5) Detect anomaly -> 6) Policy lookup

## Design choices
- Tools have a single `run(payload)` method returning a dict -> easy to test & plug into a Router/Registry.
- SQL tools use parameterized queries via `sqlite3`.
- RAG = simple keyword search over `documents` (no extra deps). Replace later with vector search if needed.
- ML = heuristic baseline by default; when you add a real model file under `ml/models/`, the tools can switch to ML mode.

Enjoy building!
