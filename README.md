# Real-Time Chat Application

A modern, scalable chat application with typing indicators, online status, group chats, message persistence, and WebSocket-based realtime updates.

Perfect demonstration of **distributed systems + realtime communication + full-stack engineering.**

## Features

- 🔥 Instant messaging via WebSockets (Socket.io)
- 👥 One-to-one and group chats
- 🟢 Online/offline presence tracking
- ✍️ Typing indicators
- 📩 Message delivery + read receipts
- 🗂️ Chat history persistence (PostgreSQL)
- 🔐 JWT-based auth (access + refresh tokens)
- 📡 Horizontal scaling with Redis adapter
- 📱 Responsive UI (mobile-first layout)

## High-Level Architecture

```bash
         ┌───────────────┐
         │   Client UI    │ (Next.js / React)
         └───────┬───────┘
                 │ REST + WebSocket
         ┌───────▼────────┐
         │  API Gateway    │  (NestJS)
         └───────┬────────┘
                 │
         ┌───────▼────────┐
         │ Auth Service    │  JWT, Refresh Tokens
         └───────┬────────┘
                 │
         ┌───────▼────────┐
         │ Chat Service    │  WebSocket Server
         └───────┬────────┘
                 │ uses
         ┌───────▼────────┐
         │ Redis Adapter   │
         └───────┬────────┘
                 │
         ┌───────▼────────┐
         │ PostgreSQL DB   │
         └─────────────────┘
```

## Tech Stack
### Backend
- Node.js / NestJS
- Socket.io
- PostgreSQL
- Redis (pub/sub)
- Prisma ORM

### Frontend
- React / Next.js
- Tailwind CSS
- Zustand for state management

## DevOps
- Docker + Compose
- Nginx (optional)

## Folder Structure

```bash
realtime-chat-app/
│
├── chat-service/          # Websocket backend
├── api-service/           # REST auth/user service
├── client/                # Next.js app
│
├── docker-compose.yml
└── README.md
```

## Running the Project
### Clone the Repo
```bash
git clone https://github.com/misbahafzal/realtime-chat-app
cd realtime-chat-app
```
### Start Environment
```bash
docker-compose up --build
```
### Open App
```bash
http://localhost:3000
```

## Roadmap
- [ ] Group chat creation UI
- [ ] Add message reactions
- [ ] Add image/file uploads
- [ ] Add notifications
- [ ] Add email/password onboarding
- [ ] Integrate vector search for “semantic chat history”

### License
MIT