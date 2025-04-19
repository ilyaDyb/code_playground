
# CodePlayground MVP Checklist

A minimal viable product for a collaborative code editor with real-time sync and execution features.

---

## Project Goals
- Allow multiple users to edit code in real time
- Execute the code securely and return output
- Simple UI with WebSocket-based collaboration

---

## Tech Stack
- **Backend**: FastAPI + WebSocket
- **Frontend**: React + Monaco Editor
- **Execution**: Subprocess / Docker sandbox
- **Optional**: Redis for session handling

---

## Checklist

### 1. Project Setup
- [ ] Initialize backend project (FastAPI)
- [ ] Initialize frontend project (React + Vite)
- [ ] Configure Docker Compose (backend + frontend)

### 2. Backend (FastAPI)
#### API
- [ ] `POST /session/create` — Create session
- [ ] `GET /session/{id}` — Join session
#### WebSocket
- [ ] Enable WebSocket connection per session
- [ ] Broadcast code updates to connected users
- [ ] Handle client disconnects
#### Code Execution
- [ ] `POST /run` — Receive and execute code
- [ ] Secure execution (timeout, no dangerous modules)
- [ ] Return stdout/stderr to frontend

### 3. Frontend (React)
- [ ] Integrate Monaco Editor
- [ ] Connect WebSocket for real-time code updates
- [ ] Display execution output
- [ ] UI: Code input, Run button, Console

### 4. Session Storage (Optional)
- [ ] Use in-memory storage for sessions
- [ ] Redis for persistence/pub-sub (optional)

### 5. Security & Limits
- [ ] Timeout on execution
- [ ] Limit memory/CPU (ulimit/Docker)
- [ ] Sanitize code input (no `import os`, `open`, etc.)

### 6. Testing
- [ ] Test run endpoint
- [ ] Test WebSocket collaboration
- [ ] Simulate multiple users

### 7. Basic Design
- [ ] Minimal UI (VS Code style)
- [ ] Share session via link

---

_Last updated: 2025-04-17_
