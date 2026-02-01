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
