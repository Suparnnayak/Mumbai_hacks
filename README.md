🏥 Arogya AI: Autonomous Surge-Readiness Engine for 1000+ Hospitals
🚀 Mumbai Hacks 2025 — Official Project Documentation
🏆 Proposed Guinness World Record Submission
🏆 Guinness Claim (Proposed)

“First AI system to autonomously coordinate and plan surge-readiness for 1000+ hospitals in real time using multi-agent reasoning, completing the entire simulation in under 2 minutes.”

Arogya AI demonstrates the world’s first near-real-time, fully autonomous healthcare surge-readiness engine built using SLMs, multi-agent reasoning, and a massively scalable backend.

🌐 Overview

Arogya AI is a MERN-based autonomous operations engine that simulates, predicts, and plans healthcare surge-readiness for a large network of hospitals. It combines:

Machine Learning predictions

SLM-powered multi-agent planning

High-throughput simulation engine

Interactive React dashboard

It can simulate 1000+ hospitals concurrently — generating surge predictions, staffing & supply plans, advisories, and a merged operational strategy.

✨ Core Features
🧠 1. Patient Surge Prediction

Predicts surge probability from environmental + hospital sensitivity factors.

Inputs include: AQI, temperature, humidity, rainfall, festival index, seasonal index.

🧩 2. Autonomous Multi-Agent System (SLM-powered)

Arogya AI uses four specialized Small Language Model agents:

Agent	Role
Monitor Agent	Analyzes external risk factors → outputs alertLevel, riskFactors.
Staffing Planner	Computes doctorsNeeded, nursesNeeded, supportStaffNeeded.
Supplies Planner	Computes beds, oxygenCylinders, commonMedicines, specialMedicines.
Advisory Agent	Public advisory, triage rules, teleconsultation tips, safety notices.
Coordinator Agent	Combines everything into a unified operational plan.

Agents run via:

Phi-3 Mini

Llama 3.1 8B

Groq SLM endpoint

Ollama local

⚡ 3. 1000-Hospital Simulation Engine

Built using Node.js, Redis, BullMQ for concurrency.

Executes 1000 full agent pipelines in parallel.

Collects performance metrics:

Total latency

Per-hospital execution time

Concurrency throughput

📊 4. Interactive React Dashboard

Live visualization of:

Predictions

Agent-generated operational plans

Public advisories

Simulation performance

🛡️ 5. High-Availability ML Microservice

ML service is external

BUT backend has auto-fallback → ensures prediction always works

Built using Node.js + plug-in architecture

🏗️ Architecture
               ┌────────────────────────────────────────┐
               │                Frontend                 │
               │       React + Vite Dashboard            │
               └───────────────▲─────────┬──────────────┘
                               │         │
                               │         │
                     REST API  │         │ WebSockets (optional)
                               │         │
                               ▼         │
     ┌──────────────────────────────────────────────────────────────┐
     │                       Backend (Node.js)                      │
     │  Express • BullMQ • Redis • Pino Logging • Prometheus        │
     ├─────────────┬────────────────────────┬───────────────────────┤
     │ Prediction   │ Multi-Agent Engine     │ Simulation Engine     │
     │ Microservice │ (Phi3, Llama, Groq)    │ (1000 Hospitals)      │
     └─────────────┴────────────────────────┴───────────────────────┘
                               │
                               │
                               ▼
                   ┌────────────────────────┐
                   │   MongoDB Atlas         │
                   │ hospitals, simulations, │
                   │ predictions, agentLogs  │
                   └────────────────────────┘

🗄️ Database Schema (MongoDB)
hospitals
{
  _id,
  name,
  district,
  capacity,
  diseaseSensitivity: { resp: 0.7, cardio: 0.2, general: 0.1 }
}

predictions
{
  hospitalId,
  date,
  predictedAdmissions,
  aqi,
  temp,
  humidity,
  rainfall,
  festivalIndex,
  riskScore
}

agents_logs
{
  hospitalId,
  monitor,
  staffing,
  supplies,
  advisory,
  finalPlan,
  timestamp
}

simulations
{
  simulationId,
  count: 1000,
  concurrency: 20,
  durationMs: 81257,
  perHospitalLatency: {...},
  agentsUsed: ["Phi3 Mini", "Groq", "Llama 3.1 8B"],
  timestamp
}

📡 Backend API Endpoints
🔮 1. /predict-surge (POST)

Predicts patient inflow using ML model.

👩‍⚕️ 2. /plan-staffing (POST)

Staffing Planner Agent (SLM)

🏥 3. /plan-supplies (POST)

Supply Planner Agent (SLM)

📢 4. /generate-advisory (POST)

Advisory Agent (SLM)

🤖 5. /run-agents (POST)

Full pipeline for a single hospital:

Prediction → Monitor Agent → Staffing → Supplies → Advisory → Coordinator

🌐 6. /simulate-network (POST)

Runs Guinness-scale simulation.

{
  "count": 1000,
  "concurrency": 20
}

🏛️ 7. /hospitals/:id

Get hospital details.

📊 8. /simulation/:id

Fetch metrics of simulation run.

🚀 Setup & Development Guide
1. Clone Repo
git clone https://github.com/your-repo/arogya-ai.git
cd arogya-ai

⚙️ Backend Setup
cd backend
npm install
npm run dev


Environment variables:

MONGO_URI=
REDIS_URL=
GROQ_API_KEY=
OLLAMA_HOST=
ML_SERVICE_URL=

🎨 Frontend Setup
cd frontend
npm install
npm run dev

🤖 AI/ML Services

Arogya AI uses hybrid SLM orchestration:

Primary → Groq SLM API (fastest)

Fallback → Local Ollama (Phi-3 Mini)

Special Cases → Llama 3.1 8B

Agents implemented using:

LangChain

Custom Orchestrator

Tools-based Agent actions

Streaming outputs

🚀 Deployment Guide
🟩 Frontend (React)

Hosted on Vercel
🔗 https://frontend-three-beta-54.vercel.app/

🟦 Backend (Node / Express)

Hosted on Railway
🔗 https://new-f-production.up.railway.app/

🟥 ML / Agents Engine

Hosted on Render
🔗 https://agents-ai-xkvx.onrender.com/agents/run

🟨 Database

MongoDB Atlas Cluster (M10 or higher)

📸 Screenshots

(Add images in your GitHub or Devpost)

Dashboard Home

Hospital Surge Prediction View

Agent Plan Viewer

1000-Hospital Simulation Screen

Latency Graph

Advisory Cards

📈 Performance Metrics (Sample)
Metric	Value
Simulation size	1000 hospitals
Concurrency	20
Total time	~1–2 minutes
Avg per hospital	40–90 ms
Agents combined	4 agents per hospital
Total agent runs	4000+ in 120 sec
🏅 Why This Project Matters

Healthcare systems often fail due to slow surge readiness.
Arogya AI solves this by:
✔ Scaling to 1000+ hospitals
✔ Real-time agent-based micro-planning
✔ Predictive + prescriptive pipeline
✔ High-speed simulation for disaster scenarios
✔ Complete automation end-to-end
This can assist:
Indian health departments
Hospital networks
Pandemic management teams
Disaster response units
<img width="532" height="161" alt="Screenshot 2025-11-29 120759" src="https://github.com/user-attachments/assets/4e0fb18a-996a-4653-8d18-0df582684313" />
<img width="419" height="242" alt="Screenshot 2025-11-29 120753" src="https://github.com/user-attachments/assets/e7328b1f-63f2-4252-bd42-cdce5ec4b236" />
