# Project: Agentic IG Manager
## Scope

A web-based agentic AI system that acts as a social media manager for Instagram. The platform visualizes your profile as a network of agents, each handling a specific task (analytics, content planning, content creation, engagement) and communicates with other agents to automate insights and suggestions.

Frontend: Next.js + React Flow (visualize agents and their interactions)

Backend: Python + FastAPI (runs agents and handles logic)

Agents communicate asynchronously and optionally store memory

MVP focuses on demo-ready AI workflow, not live Instagram posting

## Goals

Provide a visual overview of agent interactions managing an IG profile

Implement autonomous agents for analytics, planning, content creation, and engagement suggestions

Enable modular agent development for easy experimentation and extensions

Use free deployable stack for backend, frontend, and AI inference

Build a showcase-ready MVP suitable for hackathons or portfolio

## Deliverables (MVP)

React Flow dashboard showing agents as nodes

Backend API for running agents and orchestrating communication

Dummy content/analytics to simulate Instagram data

Live agent updates via WebSockets or API polling

Modular agent classes for future AI integration

## Project Structure

```
frontend/
├── app/
│   ├── page.tsx                 # Dashboard
│   ├── api/                     # Proxy routes to Python
│   │   └── agents/
│   │       └── run/route.ts
│   ├── layout.tsx
│
├── components/
│   ├── flow/
│   │   ├── AgentFlow.tsx        # React Flow canvas
│   │   ├── AgentNode.tsx
│   │   └── Edge.tsx
│   ├── panels/
│   │   ├── LogsPanel.tsx
│   │   ├── AgentDetails.tsx
│   │   └── ApprovalPanel.tsx
│
├── store/
│   └── agentStore.ts            # Zustand (agent state)
│
├── lib/
│   ├── api.ts                   # Calls to backend
│   └── socket.ts                # WebSocket client
│
├── types/
│   └── agent.ts                 # Agent message types
│
└── tailwind.config.ts

backend/
├── app/
│   ├── main.py                  # FastAPI entry
│
│   ├── orchestrator/
│   │   └── orchestrator.py      # Decides agent order
│
│   ├── agents/
│   │   ├── base.py              # BaseAgent class
│   │   ├── analytics.py
│   │   ├── planner.py
│   │   ├── creator.py
│   │   └── engagement.py
│
│   ├── tools/
│   │   ├── instagram.py         # IG API / mocks
│   │   ├── llm.py               # OpenAI / HF / Groq
│   │   └── media.py             # Image/video gen
│
│   ├── memory/
│   │   └── store.py             # SQLite / Redis
│
│   ├── schemas/
│   │   └── messages.py          # Pydantic models
│
│   ├── ws/
│   │   └── events.py            # WebSocket events
│
│   └── config.py
│
├── requirements.txt
└── .env
