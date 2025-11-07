# 💰 SPV Simulator Advanced

## Overview
Next-generation **financial simulation engine** for restaurant acquisitions and expansions.  
Converts business inputs into precise cost forecasts, dynamically adjusted using risk data from MAPAQ.

---

## Features
- Modular cost engine (Python backend)
- REST interface (FastAPI/Flask)
- Web UI (React or Blazor)
- Scenario comparison: Good vs Bad location, Full Expansion vs Cloud Kitchen
- Integration with MAPAQ risk API
- Export: CSV, PDF, and live API responses
- Multi-user sessions stored in SQLite/PostgreSQL

---

## Architecture

spv-simulator-advanced/

├── backend/

│ ├── engine.py # Core cost calculation logic

│ ├── formulas.py # Weighted multipliers

│ ├── api.py # REST endpoints

│ └── db.py # Persistence

├── frontend/

│ ├── src/

│ │ ├── components/

│ │ ├── pages/

│ │ └── services/

│ └── package.json

├── tests/

│ ├── test_engine.py

│ └── test_api.py

└── README.md


---

## Inputs & Outputs

| Input Variable | Description | Source |
|----------------|-------------|--------|
| `theme` | Restaurant type (5 themes) | UI dropdown |
| `revenue_size` | Annual gross income | User input |
| `kitchen_size` | Physical area (m²) | DB |
| `equipment_condition` | Good / Fair / Bad | DB |
| `retraining_needed` | Boolean | HR module |
| → **Output** | JSON with cost breakdown by category + total | API |

---

## Example Flow
1. User fills UI form.  
2. Frontend sends JSON payload to `/simulate`.  
3. Engine runs calculations (formulas.py).  
4. Result returned and displayed as colored cost table.  
5. Optional: “Compare Scenarios” button runs two simulations side-by-side.  

---

## Phase 2 Development Tasks
1. Refactor backend into FastAPI service.  
2. Add advanced cost formulas (equipment depreciation, retraining multipliers).  
3. Build multi-scenario comparison module.  
4. Integrate external risk factor adjustment (via MAPAQ API).  
5. Develop modern web UI (React).  
6. Enable CSV/PDF export with charts.  
7. Add unit tests and API docs.

---

## Technologies
Python 3.10, FastAPI, React, Tailwind CSS, iText, SQLite/PostgreSQL.
