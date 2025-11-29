🏥 Arogya AI: Autonomous Surge-Readiness Engine for 1000+ Hospitals🏆 Mumbai Hacks Submission & Proposed Guinness World Record

This project, Arogya AI, is a highly scalable, MERN-based autonomous AI operations engine designed to demonstrate real-time surge-readiness planning for a massive network of hospitals.

The Claim (Guinness-Style Framing):"First AI system to autonomously coordinate and plan surge-readiness for 1000+ hospitals in real time using multi-agent reasoning, completing the entire simulation in under 2 minutes."
✨ Features & Architecture

Arogya AI is a full-stack MERN application that uses Small Language Models (SLMs) and a multi-agent system to simulate and manage healthcare surge events at a national scale.Core Capabilities
Patient Surge Prediction: Predicts potential patient surges based on environmental factors (AQI, weather, festival scores) and historical data.
Autonomous Multi-Agent Planning: Utilizes four specialized SLM-powered agents to generate comprehensive operational plans.
1000-Hospital Simulation Engine: A high-throughput backend engine capable of simulating the full prediction-to-planning cycle for 1000 hospitals concurrently.
Real-time Metrics: Produces record-ready performance metrics for latency, throughput, and coordination scale.
Interactive Dashboard: A React frontend to visualize predictions, agent outputs, and a What-if Simulator for testing different scenarios.
Agents System (SLM-Powered)
Monitor Agent: Reads external risk factors (AQI, weather, festival score) and hospital disease sensitivity to output an alertLevel and riskFactors.
Planning Agent:
Staffing Planner: Calculates doctorsNeeded, nursesNeeded, and supportStaffNeeded based on predicted inflow.
Supplies Planner: Calculates requirements for oxygenCylinders, beds, commonMedicines, and specialMedicines.
Advisory Agent: Generates public health advisories, triage rules, teleconsultation suggestions, and pollution-care guidelines.
Coordinator Agent: Combines all agent outputs into a final, unified operational plan for the hospital.
Technology Stack
Category	Components	Notes
Backend	Node.js, Express, BullMQ, Redis	Scalable, high-concurrency architecture.
Database	MongoDB Atlas	Stores hospital data, predictions, agent logs, and simulation results.
Frontend	React, Vite	Dashboard and What-if Simulator interface.
AI/Agents	LangChain (or custom orchestrator), Phi-3 Mini, Llama 3.1 8B, Groq SLM API, Ollama	Uses Small Language Models (SLMs) for low-latency, autonomous reasoning.
ML	Node.js prediction service with an ML microservice plug-in (with internal fallback logic).	Ensures prediction availability even if the external ML service fails.
Observability	Pino (logging), Prometheus (metrics)	Production-ready monitoring.
💻 API Endpoints (Backend)

The Node.js/Express backend exposes the following key API endpoints:
Endpoint	Method	Purpose
/predict-surge	POST	Triggers a single hospital prediction.
/plan-staffing	POST	Generates a staffing plan (by Planning Agent A).
/plan-supplies	POST	Generates a supplies plan (by Planning Agent B).
/generate-advisory	POST	Generates public and internal advisories (by Advisory Agent).
/run-agents	POST	Runs the full prediction and agent pipeline for a single hospital.
/simulate-network	POST	Triggers the Guinness Record simulation. Input: { count: 1000, concurrency: 20 }
/hospitals/:id	GET	Fetches details for a specific hospital.
/simulation/:id	GET	Fetches the results and metrics of a simulation run.
🚀 Development & DeploymentQuick Start (Phase 1 & 2)
Setup Backend: Initialize Node + Express project, add routing, middleware (logging with Pino, request-ID).
Setup MongoDB: Create an Atlas cluster with collections: hospitals, predictions, agents_logs, simulations.
Setup Frontend: Initialize React + Vite project with Dashboard, Simulator, and Hospital details pages.
Data Prep: Run the synthetic data generator to create 100 test hospitals and 1000 final simulation hospitals. Push 100 to MongoDB.
Deployment Stack (Phase 9)
Containerization: Docker
Backend Hosting: Railway / Render / AWS EC2
Frontend Hosting: Vercel
Database: MongoDB Atlas
Gemini can't reference Calendar or Chat yet. Check dates and times for accuracy. Learn more
