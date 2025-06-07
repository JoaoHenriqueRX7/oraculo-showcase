<h1 align="center">🔮 Oráculo – Multi-Agent LLM Platform 🚀</h1>

<p align="center">
  <strong>An Enterprise MVP platform for orchestrating and managing multiple LLM agents</strong>
</p>

> **This is an early MVP.** Functionality comes first, so several screens are visually rough.  
> Please excuse the spartan UI — **far better design work** is showcased in my [portfolio](https://yourportfolio.com/designs).

---

> 🛑 **Important:** This repository contains documentation only.  
> The source code behind Oráculo is proprietary.  
> For details or collaboration, [contact me](mailto:joaohenrique@jhbdev.com.br).

---

## 📸 High-Level Architecture

Click to view full-size architecture diagram:

[![Architecture Diagram](https://link-to-your-hosted-image.com/architecture.png)](https://link-to-your-hosted-image.com/architecture.png)

---

## ✨ Features at a glance

- **Real-time chat:** Multi-agent interface using SSE
- **Admin Dashboard:** Basic CRUD for tenants, users, and agents
- **RAG Integration:** Enriched responses using vector databases
- **Media Processing:** PDFs, spreadsheets, images via **Docling**
- **Provider Flexibility:** Dynamic integration of multiple LLM providers (OpenAI, Anthropic…)

---

## 🌥️ Infrastructure Overview

| Component                | Technology                        | Description                           |
|--------------------------|-----------------------------------|---------------------------------------|
| **Compute**              | 🐳 Docker on AWS EC2              | 2 EC2 instances behind an AWS ALB     |
| **Auth & Data**          | 🛢️ Supabase PostgreSQL + Auth     | Multi-tenant user/tenant storage & JWT auth |
| **Vector DB**            | 🌐 External RAG API (e.g., Pinecone) | Vector stores for knowledge retrieval |

---

## 📌 Key Components

- 📱 **User Frontend**: Real-time chat (React + Vite)
- ⚙️ **Admin Frontend**: Management UI (React + MUI)
- 🔐 **Orchestrator API**: Authentication, multi-tenancy (FastAPI + Supabase)
- 🤖 **Multi-Agent LLM API**: Core LLM handling, RAG, Docling integration (FastAPI + Pydantic)
- 🗃️ **Docling**: Media extraction (PDF/Image/Audio) using Python tooling

---

## 🎯 Data Flow Quick Reference

1. **Login** → JWT from Supabase
2. **Agent Listing** → Tenant-specific agents from Orchestrator API
3. **Chat request** → `/chat/{agent_id}` endpoint (SSE-enabled)
4. **LLM Processing** → RAG enhancement & LLM provider calls
5. **Streaming Responses** → Incremental token streaming to frontend

---

## 🔑 Important Endpoints

| Endpoint                | Description                   |
|-------------------------|-------------------------------|
| `POST /auth/token`      | User Authentication (JWT)     |
| `GET /client/agents`    | Fetch available agents        |
| `POST /chat/{agent_id}` | Chat with selected agent (SSE) |
| `POST /admin/instances` | Create new tenant             |
| **[Full API Specification](docs/api-spec.md)** | Comprehensive API details |

---

## 📊 Primary Data Models (Supabase)

| Entity            | Highlights                                         |
|-------------------|----------------------------------------------------|
| `instances`       | Tenant/client instances                            |
| `users`           | Users and roles (`super_admin`, `instance_admin`, `instance_user`) |
| `instance_agents` | Configurable agent profiles per tenant             |

[Full data model ERD](docs/data-model.md)

---

## 🎥 Screenshots & Demo

| 🗣️ Chat Frontend (MVP UI)                | 🛠️ Admin Dashboard (MVP UI)                 |
|------------------------------------------|--------------------------------------------|
| ![Chat GIF](assets/chat-demo.gif)        | ![Admin Screenshot](assets/admin.png)       |

👉 **[Watch Full MVP Demo on YouTube](https://youtu.be/YOUR_VIDEO_URL)**

*(For polished UI examples, visit my [portfolio designs](https://yourportfolio.com/designs).)*

---

## 🚀 Next Steps (Roadmap)

- ✨ Complete UI/UX overhaul  
- 🌐 Automatic prompt translations  
- 🔧 Tenant-specific fine-tuning capabilities  
- 💳 Usage-based billing & throttling  
- 📂 Bulk RAG document upload

---

## 🙌 Contributing

This repository accepts pull requests for documentation improvements. For direct collaboration on the proprietary codebase, please [get in touch](mailto:your.email@example.com).

---

## 📜 License

All documentation in this repository is shared under **Creative Commons CC-BY-NC-SA 4.0**.  
All production source code remains proprietary and confidential.

---

**Thanks for stopping by!** 🎉
