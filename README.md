<h1 align="center">🔮 Oráculo – Multi-Agent LLM Platform</h1>

<p align="center">
  <strong>An MVP built in partnership with Aya (Vila Velha, Brazil) to empower businesses with custom AI agents</strong>
</p>

> ⚠️ **Quick heads-up:** You're looking at the MVP version—meaning functionality beats aesthetics this round. So please forgive the plain looks! I've got a bit more refined works in [portfolio](https://yourportfolio.com/designs). 😉

---

🛑 **Important note:** This repo is just a showcase. The Oráculo code is proprietary and developed in collaboration with [Aya](https://aya.tec.br/) to provide companies with a powerful, customizable tool. For inquiries or collaboration, feel free to [reach out](mailto:joaohenrique@jhbdev.com.br).

---

## 📸 High-Level Architecture

Click below for a detailed view of our architecture:

[![Architecture Diagram](https://drive.google.com/uc?export=view&id=1pkytIwxN_MQBnnzKYjoi8ou9vrZbNWq-)](https://drive.google.com/uc?export=view&id=1pkytIwxN_MQBnnzKYjoi8ou9vrZbNWq-)

---

## 🚀 Why Oráculo?

Developed alongside Aya, Oráculo is designed specifically to give companies the power to effortlessly create and manage their own customized AI agents. Its core strengths include:

- **Unlimited agent instances**: Create as many specialized AI agents as your business needs.
- **Voice & text interactions**: Seamlessly chat with AI agents via voice or text.
- **Real-time conversation flow**: Powered by server-sent events (SSE) for dynamic interactions.
- **Intelligent context**: Integrated Retrieval-Augmented Generation (RAG) ensures precise, knowledge-rich responses.
- **Flexible backend**: Supports integration with leading LLM providers (OpenAI, Anthropic, etc.).
- **Media-friendly**: Directly process PDFs, images, audio, and more.

---

## 🛠️ How We Built It (Tech Stack)

| Component           | Technology                            | Role                              |
|---------------------|---------------------------------------|-----------------------------------|
| 🐳 **Compute**      | Docker on AWS EC2 + AWS ALB           | Scalable infrastructure           |
| 🗃️ **Database/Auth** | Supabase (PostgreSQL + JWT Auth)      | Multi-tenant user/tenant management |
| 🌐 **Vector DB**    | External RAG (e.g., Pinecone)         | Contextual knowledge retrieval    |

---

## 🔗 Core Modules

- 📱 **User Frontend:** Real-time chat interface (React + Vite)
- ⚙️ **Admin Dashboard:** Basic tenant & agent management (React + MUI)
- 🔐 **Orchestrator API:** Authentication and orchestration (FastAPI + Supabase)
- 🤖 **Multi-Agent LLM API:** LLM processing, RAG integration, media handling (FastAPI + Python)
- 📄 **Docling:** Robust media parsing (PDF, images, audio)

---

## 🗂️ A Quick Look at the Flow

1. **Login:** Auth via Supabase JWT
2. **Pick an Agent:** Get tenant-specific agents
3. **Start Chatting:** Real-time voice/text via `/chat/{agent_id}` (SSE)
4. **Enhanced Replies:** Prompt enriched with RAG context, processed by selected LLM
5. **Real-Time Interaction:** Responses delivered seamlessly, streamed live to frontend

---

## 🔑 Essential API Endpoints

| Endpoint                | Function                              |
|-------------------------|---------------------------------------|
| `POST /auth/token`      | Authenticate and issue JWT            |
| `GET /client/agents`    | Fetch tenant-specific agents          |
| `POST /chat/{agent_id}` | Converse with AI agent (text & voice) |
| `POST /admin/instances` | Create/manage tenants                 |

📖 [Full API details here](docs/api-spec.md).

---

## 📊 Data Model Overview

| Entity            | Key Details                                           |
|-------------------|-------------------------------------------------------|
| `instances`       | Tenants (individual companies or departments)         |
| `users`           | Role-based user access (admins, users)                |
| `instance_agents` | Fully customizable agents per tenant                  |

🗃️ [Complete data model ERD](docs/data-model.md)

---

## 🎥 Quick Demo & Screenshots

| 💬 **Chat UI** (basic MVP look)           | 🛠️ **Admin Panel** (simple MVP style)         |
|-------------------------------------------|-----------------------------------------------|
| ![Chat GIF](assets/chat-demo.gif)         | ![Admin Panel](assets/admin.png)              |

▶️ [**See Oráculo in action (YouTube Demo)**](https://youtu.be/YOUR_VIDEO_URL)

*(Again, UI-wise, better things await you in my [portfolio](https://yourportfolio.com/designs)!)*

---

## 📌 Roadmap (Where We're Headed Next)

- ✨ A full UI/UX makeover  
- 🌐 Multilingual automatic translations  
- 🔧 Tenant-specific model fine-tuning  
- 💳 Usage-based billing and rate limiting  
- 📂 Bulk document uploads for RAG databases

---

## 🙌 Interested in Collaborating?

I'm open to documentation improvements and further development opportunities. Reach out directly:

📧 [joaohenrique@jhbdev.com.br](mailto:joaohenrique@jhbdev.com.br)

---

## 📜 Licensing

All documentation and visuals provided here are under **Creative Commons CC-BY-NC-SA 4.0**.  
Source code remains private under Aya partnership agreements.

---

Thanks for checking out Oráculo — built in Brazil, empowering your business one agent at a time. 🇧🇷✨
