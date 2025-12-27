# 🚀 DevCollab - Real-Time Collaborative Coding Platform

<div align="center">

![DevCollab Banner](https://img.shields.io/badge/DevCollab-Real--Time%20Collaboration-blue?style=for-the-badge)

[![Live Demo](https://img.shields.io/badge/🌐_Live_Demo-Vercel-black?style=for-the-badge)](https://devcollab-frontend.vercel.app/)
[![API Docs](https://img.shields.io/badge/📚_API_Docs-Swagger-green?style=for-the-badge)](https://devcollab-backend-6h0m.onrender.com/api/docs/)
[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)](https://typescriptlang.org/)
[![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)](https://nextjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)

**A production-grade real-time collaborative coding workspace that enables developers to code together seamlessly.**

[Live Demo](https://devcollab-frontend.vercel.app/) • [API Documentation](https://devcollab-backend-6h0m.onrender.com/api/docs/) • [Developer](https://prinsmathukiya.vercel.app/)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Live Demo](#-live-demo)
- [Screenshots](#-screenshots)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [Database Schema](#-database-schema)
- [API Endpoints](#-api-endpoints)
- [Real-Time Events](#-real-time-events)
- [Getting Started](#-getting-started)
- [Environment Variables](#-environment-variables)
- [Project Structure](#-project-structure)
- [Security Features](#-security-features)
- [Developer](#-developer)

---

## 🎯 Overview

**DevCollab** is a real-time collaborative JavaScript coding platform designed for teams to work together seamlessly. Built with modern technologies and following clean architecture principles, it provides a secure, scalable, and performant environment for collaborative coding.

### Key Highlights

- ⚡ **Real-time Collaboration** - See teammates' cursors and code changes instantly
- 🔐 **Secure Authentication** - JWT with refresh token rotation
- 🚀 **Async Code Execution** - BullMQ-powered job queue for safe code execution
- 📊 **Role-Based Access** - Owner, Collaborator, and Viewer roles
- 🗄️ **Redis Caching** - High-performance caching layer
- 📝 **File Versioning** - Track code changes with version control

---

## 🌐 Live Demo

| Service | URL |
|---------|-----|
| **Frontend** | [https://devcollab-frontend.vercel.app/](https://devcollab-frontend.vercel.app/) |
| **Backend API** | [https://devcollab-backend-6h0m.onrender.com/api/v1](https://devcollab-backend-6h0m.onrender.com/api/v1) |
| **Swagger Docs** | [https://devcollab-backend-6h0m.onrender.com/api/docs/](https://devcollab-backend-6h0m.onrender.com/api/docs/) |

---

## 📸 Screenshots

### Landing Page
![Home Page](public/01-home-page.png)

### Authentication
<div align="center">
<table>
<tr>
<td align="center"><b>Register</b></td>
<td align="center"><b>Login</b></td>
</tr>
<tr>
<td><img src="public/02-register.png" alt="Register" width="400"/></td>
<td><img src="public/03-login.png" alt="Login" width="400"/></td>
</tr>
</table>
</div>

### Workspace & Code Editor
![Workspace Editor](public/04-workspace-editor.png)

### Real-Time Collaboration
<div align="center">
<table>
<tr>
<td align="center"><b>Live Cursor Sync</b></td>
<td align="center"><b>Real-Time Code Updates</b></td>
</tr>
<tr>
<td><img src="public/05-realtime-cursor-sync.png" alt="Cursor Sync" width="400"/></td>
<td><img src="public/06-realtime-collaboration.png" alt="Real-time Collaboration" width="400"/></td>
</tr>
</table>
</div>

### Team Management
<div align="center">
<table>
<tr>
<td align="center"><b>Invite Collaborators</b></td>
<td align="center"><b>Team Presence (Online/Offline)</b></td>
</tr>
<tr>
<td><img src="public/07-invite-collaborators.png" alt="Invite Collaborators" width="400"/></td>
<td><img src="public/08-team-presence.png" alt="Team Presence" width="400"/></td>
</tr>
</table>
</div>

### Role-Based Access
![Viewer Mode - Read Only](public/09-viewer-readonly.png)
*Viewers can see the code but cannot edit or execute it*

---

## ✨ Features

### 🔐 Authentication & Authorization

![Authentication Flow](public/diagrams/01-auth-flow.png)

- **JWT Authentication** with access and refresh tokens
- **Refresh Token Rotation** - Each refresh creates a new token pair
- **Secure Token Storage** - Refresh tokens stored in PostgreSQL
- **Rate Limiting** - Protects against brute force attacks

### 👥 Role-Based Access Control

![Role-Based Access Control](public/diagrams/02-rbac.png)

| Role | Create Project | Edit Code | Execute Code | View Code | Invite Users |
|------|:--------------:|:---------:|:------------:|:---------:|:------------:|
| **Owner** | ✅ | ✅ | ✅ | ✅ | ✅ |
| **Collaborator** | ❌ | ✅ | ✅ | ✅ | ❌ |
| **Viewer** | ❌ | ❌ | ❌ | ✅ | ❌ |

### ⚡ Real-Time Collaboration

![Real-Time Collaboration](public/diagrams/03-realtime-collab.png)

- **Live Cursor Tracking** - See where teammates are editing with colored cursors
- **Real-Time Code Sync** - Changes appear instantly across all connected users
- **User Presence** - Know who's online in your workspace
- **Selection Highlighting** - View teammates' text selections

### 🖥️ Code Execution Engine

![Code Execution Engine](public/diagrams/04-code-execution.png)

- **Async Job Queue** - BullMQ handles code execution jobs
- **Sandboxed Execution** - Code runs in isolated VM environment
- **Execution Timeout** - 5-second limit prevents infinite loops
- **Real-Time Results** - Output broadcasted to all workspace members

---

## 🛠️ Tech Stack

### Backend

| Technology | Purpose |
|------------|---------|
| **Node.js + Express** | REST API Server |
| **TypeScript** | Type-safe development |
| **PostgreSQL** | Primary database |
| **Prisma ORM** | Database access & migrations |
| **Redis** | Caching & Socket.io adapter |
| **Socket.io** | Real-time communication |
| **BullMQ** | Job queue for code execution |
| **JWT** | Authentication tokens |
| **Zod** | Request validation |
| **Winston** | Logging |
| **Swagger** | API documentation |

### Frontend

| Technology | Purpose |
|------------|---------|
| **Next.js 14** | React framework |
| **React 18** | UI library |
| **TypeScript** | Type-safe development |
| **Zustand** | State management |
| **Socket.io Client** | Real-time communication |
| **Monaco Editor** | Code editor (VS Code engine) |
| **Tailwind CSS** | Styling |
| **Radix UI** | Accessible components |
| **React Hook Form + Zod** | Form handling & validation |

---

## 🏗️ Architecture

### System Architecture

![System Architecture](public/diagrams/05-system-architecture.png)

### Clean Architecture Layers

![Clean Architecture](public/diagrams/06-clean-architecture.png)

---

## 🗄️ Database Schema

![Database Schema](public/diagrams/07-database-schema.png)

---

## 📡 API Endpoints

### Authentication

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/v1/auth/register` | Register new user |
| `POST` | `/api/v1/auth/login` | Login user |
| `POST` | `/api/v1/auth/refresh` | Refresh access token |
| `POST` | `/api/v1/auth/logout` | Logout (invalidate refresh token) |
| `POST` | `/api/v1/auth/logout-all` | Logout from all devices |
| `GET` | `/api/v1/auth/me` | Get current user profile |
| `GET` | `/api/v1/auth/users/search` | Search users |

### Projects

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/v1/projects` | Create project |
| `GET` | `/api/v1/projects` | Get user's projects |
| `GET` | `/api/v1/projects/:id` | Get project by ID |
| `PATCH` | `/api/v1/projects/:id` | Update project |
| `DELETE` | `/api/v1/projects/:id` | Delete project |
| `POST` | `/api/v1/projects/:id/collaborators` | Invite collaborator |
| `GET` | `/api/v1/projects/:id/collaborators` | Get collaborators |
| `PATCH` | `/api/v1/projects/:id/collaborators/:id` | Update role |
| `DELETE` | `/api/v1/projects/:id/collaborators/:id` | Remove collaborator |

### Workspaces

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/v1/workspaces` | Create workspace |
| `GET` | `/api/v1/workspaces/project/:projectId` | Get project workspaces |
| `GET` | `/api/v1/workspaces/:id` | Get workspace |
| `PATCH` | `/api/v1/workspaces/:id` | Update workspace |
| `DELETE` | `/api/v1/workspaces/:id` | Delete workspace |
| `GET` | `/api/v1/workspaces/:id/files/:fileId` | Get code file |
| `PATCH` | `/api/v1/workspaces/:id/files/:fileId` | Update code file |

### Code Execution

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/v1/execute` | Execute JavaScript code |
| `GET` | `/api/v1/execute/job/:jobId` | Get job status |
| `GET` | `/api/v1/execute/history/:workspaceId` | Get execution history |

### Health Check

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/v1/health` | Check API & services health |

---

## 🔌 Real-Time Events

### Client → Server Events

| Event | Payload | Description |
|-------|---------|-------------|
| `join-workspace` | `{ workspaceId }` | Join a workspace room |
| `leave-workspace` | - | Leave current workspace |
| `code-change` | `{ content, fileId }` | Broadcast code changes |
| `save-code` | `{ content, fileId }` | Persist code to database |
| `cursor-position` | `{ line, column }` | Update cursor position |
| `selection-change` | `{ startLine, startColumn, endLine, endColumn }` | Update selection |

### Server → Client Events

| Event | Payload | Description |
|-------|---------|-------------|
| `workspace-joined` | `{ workspaceId, users, role, codeFile }` | Confirm workspace join |
| `user-joined` | `{ userId, username, users }` | New user joined |
| `user-left` | `{ userId, username, users }` | User left workspace |
| `code-update` | `{ content, userId, username }` | Code changed by another user |
| `code-saved` | `{ fileId, savedBy, timestamp }` | Code saved confirmation |
| `cursor-update` | `{ userId, username, position }` | Cursor position update |
| `selection-update` | `{ userId, username, selection }` | Selection update |
| `execution-result` | `{ jobId, output, error, status }` | Code execution result |

---

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- PostgreSQL 14+
- Redis 6+
- npm or yarn

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/prinsium/devcollab.git
   cd devcollab
   ```

2. **Setup Backend**
   ```bash
   cd back-end
   npm install
   cp .env.example .env
   # Configure your .env file
   npx prisma generate
   npx prisma db push
   ```

3. **Setup Frontend**
   ```bash
   cd front-end
   npm install
   cp .env.example .env.local
   # Configure your .env.local file
   ```

4. **Start Development Servers**
   ```bash
   # Terminal 1 - Backend
   cd back-end
   npm run dev

   # Terminal 2 - Job Worker
   cd back-end
   npm run worker

   # Terminal 3 - Frontend
   cd front-end
   npm run dev
   ```

---

## ⚙️ Environment Variables

### Backend (.env)

```env
# Server
NODE_ENV=development
PORT=5000

# Database
DATABASE_URL=postgresql://user:password@localhost:5432/devcollab
DIRECT_URL=postgresql://user:password@localhost:5432/devcollab

# Redis
REDIS_URL=redis://localhost:6379

# JWT
JWT_SECRET=your-super-secret-key
JWT_EXPIRES_IN=15m

# Client
CLIENT_URL=http://localhost:3000
```

### Frontend (.env.local)

```env
NEXT_PUBLIC_API_URL=http://localhost:5000/api/v1
NEXT_PUBLIC_SOCKET_URL=http://localhost:5000
```

---

## 📁 Project Structure

```
devcollab/
├── back-end/
│   ├── prisma/
│   │   └── schema.prisma          # Database schema
│   ├── src/
│   │   ├── application/
│   │   │   └── services/          # Business logic
│   │   ├── config/                # Configuration
│   │   ├── infrastructure/
│   │   │   └── socket/            # Socket.io handlers
│   │   ├── interfaces/
│   │   │   ├── controllers/       # Request handlers
│   │   │   └── routes/            # API routes
│   │   ├── middleware/            # Express middleware
│   │   ├── utils/                 # Utilities
│   │   ├── workers/               # Background jobs
│   │   ├── app.ts                 # Express app
│   │   └── server.ts              # Server entry
│   └── package.json
│
├── front-end/
│   ├── src/
│   │   ├── app/                   # Next.js pages
│   │   ├── components/            # React components
│   │   ├── lib/                   # Utilities & API
│   │   └── store/                 # Zustand stores
│   └── package.json
│
└── README.md
```

---

## 🔒 Security Features

| Feature | Implementation |
|---------|----------------|
| **Password Hashing** | bcrypt with 12 salt rounds |
| **JWT Authentication** | Access tokens (15min) + Refresh tokens (7 days) |
| **Token Rotation** | Refresh token replaced on each use |
| **Rate Limiting** | express-rate-limit on all API routes |
| **Input Validation** | Zod schemas for all requests |
| **SQL Injection Protection** | Prisma ORM with parameterized queries |
| **XSS Protection** | Helmet middleware |
| **CORS** | Configured for specific origins |
| **Sandboxed Execution** | VM2 for code execution isolation |

---

## 📊 Performance Optimizations

- **Redis Caching** - Project and workspace data cached with TTL
- **Database Indexing** - Optimized queries with proper indexes
- **Socket.io Redis Adapter** - Horizontal scaling support
- **Connection Pooling** - Prisma connection management
- **Rate Limiting** - Prevents API abuse
- **Lazy Loading** - Frontend code splitting

---

## 👨‍💻 Developer

<div align="center">

**Prins Mathukiya**

[![Portfolio](https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=About.me&logoColor=white)](https://prinsmathukiya.vercel.app/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/prinsium)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/prins-mathukiya)

</div>

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

<div align="center">

**Built with ❤️ by [Prins Mathukiya](https://prinsmathukiya.vercel.app/)**

⭐ Star this repo if you find it helpful!

</div>
