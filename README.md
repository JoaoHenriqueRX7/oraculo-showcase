<h1 align="center">🔮 Oráculo – Multi-Agent LLM Platform</h1>

<p align="center">
  <strong>An MVP built for Aya (Vila Velha, Brazil), enabling businesses to create and manage custom AI agents</strong>
</p>

> ⚠️ **Quick heads-up:** You're looking at the MVP version... functionality beats aesthetics this round. So please forgive the plain looks! I’ve got more polished design work in my [portfolio](https://yourportfolio.com/designs).

---

🛑 **Important note:** This repo is a showcase only. The Oráculo code is proprietary and was developed as a custom solution for [Aya](https://aya.tec.br/), designed to empower businesses with fully personalized AI agents. Any questions, feel free to [reach out](mailto:joaohenrique@jhbdev.com.br).

---
| page | Description |
|------------|-------------|
| [![User - Chat Text](https://drive.google.com/uc?export=view&id=1YJV8ZBjNma1OAktYyjvI0qIjd8fGJDLB)](https://drive.google.com/uc?export=view&id=1YJV8ZBjNma1OAktYyjvI0qIjd8fGJDLB) | User chat interface: conversation with agent (text) |
| [![User - Chat Voice](https://drive.google.com/uc?export=view&id=1EOjNcHOmwXiYjPz_gXJXcvZeN0OfSXBg)](https://drive.google.com/uc?export=view&id=1EOjNcHOmwXiYjPz_gXJXcvZeN0OfSXBg) | User chat interface: conversation with agent (voice enabled via ElevenLabs) |
| [![Admin - Edit Agent](https://drive.google.com/uc?export=view&id=1S8yY4OEF2lj9ZfqrYCnjcBA7EfKCuUoj)](https://drive.google.com/uc?export=view&id=1S8yY4OEF2lj9ZfqrYCnjcBA7EfKCuUoj) | Admin panel: editing an existing agent |
| [![Admin - Create Agent](https://drive.google.com/uc?export=view&id=1eaLUrE9MaEkJ8pNqPW46NcYD24OUtD2U)](https://drive.google.com/uc?export=view&id=1eaLUrE9MaEkJ8pNqPW46NcYD24OUtD2U) | Admin panel: creating a new agent for a tenant |

## Interface demonstration
👉 **[Watch MVP Demo](https://youtu.be/6_zmRWJ77Jg?feature=shared)**

---
## 📸 High-Level Architecture

---
Click below for a detailed view of the architecture:

[![Architecture Diagram](https://drive.google.com/uc?export=view&id=1pkytIwxN_MQBnnzKYjoi8ou9vrZbNWq-)](https://drive.google.com/uc?export=view&id=1pkytIwxN_MQBnnzKYjoi8ou9vrZbNWq-)

---

## 🚀 Why Oráculo?

Oráculo was developed as an MVP for Aya to give companies a flexible, private, and highly customizable platform to build and manage their own AI agents—far beyond generic chatbots.

### 🧠 **Enterprise AI with your brand’s voice**
Companies can create agents aligned with their brand, language, and tone. Agents can also speak using real cloned voices (e.g., CEO, product leads), making the interaction feel personal and trustworthy.

### 🎙️ **Voice & text interactions, powered by ElevenLabs**
Oráculo supports both text-based chat and natural voice conversations. Using the ElevenLabs API, companies can clone voices and deploy them in voice-enabled interactions—bridging the gap between AI and human communication.

### 🔓 **Unlimited scalability**
Oráculo allows unlimited agent instances and users under a single license. Companies can scale without friction or additional per-user costs.

### 🤖 **Multiple AI models in one platform**
Agents can leverage multiple LLM providers (GPT, Claude, Gemini, LLaMA, Mistral), selected dynamically per task or business need.

### 🔧 **Seamless integration & support**
The platform was built to easily integrate with CRM, ERP, and internal databases. Setup and onboarding are assisted to ensure fast and frictionless adoption.

### 📊 **From insights to action**
Oráculo agents can generate reports, documents, code, and other actionable outputs—automating workflows and enabling faster business decisions.

### 🛡️ **Privacy-first architecture**
All data remains under enterprise control. No third-party sharing without permission. The system supports enterprise-grade compliance and governance.

### 🌟 **Future-ready**
Planned enhancements include agent memory by function or role, BI dashboards, biometric-based secure access, and white-labeled mobile apps.

---

## 🛠️ How I Built It (Tech Stack)

Oráculo was built with a modern, scalable stack designed to support real-time voice and text interactions, high configurability, and secure enterprise integration.

| Component                  | Technology                            | 
|----------------------------|---------------------------------------|
| Frontend (Admin & User)    | React, TypeScript                      |
| Backend APIs               | Python (FastAPI), PostgreSQL           |
| Media Processing           | Python ecosystem (custom tools for PDF, image, audio extraction) |
| LLM Integration            | Multiple providers via dynamic API integration |
| Voice Synthesis / Cloning  | ElevenLabs API (real-time voice cloning) |
| Infrastructure             | Dockerized services on AWS EC2, behind an ALB |
| Authentication             | Token-based (JWT), multi-tenant support |
| RAG / Vector Search        | Custom vector database API integration |

---

👉 The architecture was designed with flexibility, scalability, and privacy in mind—supporting unlimited AI agent instances, voice and text conversations, and seamless integration with business systems.

---

## 🔗 Core Modules

- 📱 **User Frontend:** Real-time chat interface with text & voice (React + Vite)
- ⚙️ **Admin Dashboard:** Tenant & agent management (React + MUI)
- 🔐 **Orchestrator API:** Authentication, orchestration, multi-tenancy (FastAPI + Supabase)
- 🤖 **Multi-Agent LLM API:** LLM processing, RAG integration, media handling (FastAPI + Python)
- 🎙️ **Voice Integration:** Real-time voice cloning and synthesis via ElevenLabs API
- 📄 **Docling:** Media parsing (PDFs, images, audio)

---

## 🗂️ Interaction Flow

1. **Login:** Auth via Supabase JWT
2. **Pick an Agent:** User selects an agent (voice & text enabled)
3. **Start Interaction:** Real-time chat via `/chat/{agent_id}` — supports both text and voice input/output
4. **Enhanced Replies:** Prompt enriched with RAG context and processed by selected LLM
5. **Real-Time Delivery:** Responses are streamed live (text or voice) to the user interface

---

## 🔑 Essential API Endpoints

| Endpoint                | Function                              |
|-------------------------|---------------------------------------|
| `POST /auth/token`      | Authenticate and issue JWT             |
| `GET /client/agents`    | Fetch tenant-specific agents           |
| `POST /chat/{agent_id}` | Converse with AI agent (text & voice)   |
| `POST /admin/instances` | Create/manage tenants                  |

---

## 📊 Data Model Overview

| Entity            | Key Details                                           |
|-------------------|-------------------------------------------------------|
| `instances`       | Tenants (individual companies or departments)         |
| `users`           | Role-based user access (admins, users)                |
| `instance_agents` | Fully customizable agents per tenant                  |

---

## 📌 Roadmap (Next Steps)

- ✨ Full UI/UX redesign  
- 🌐 Multilingual automatic translations  
- 🔧 Tenant-specific model fine-tuning  
- 💳 Usage-based billing & rate limiting  
- 📂 Bulk RAG document uploads  
- 📱 White-labeled mobile app with voice support  

---

## 🙌 Interested?

Feel free to get in touch:
📧 [joaohenrique@jhbdev.com.br](mailto:joaohenrique@jhbdev.com.br)

---

## 📜 Licensing

All documentation and visuals provided here are under **Creative Commons CC-BY-NC-SA 4.0**.  
Source code remains private, under agreements with Aya.

---

Thanks for stopping by! 🚀
