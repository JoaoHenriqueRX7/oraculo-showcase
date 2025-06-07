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

Oráculo was developed as a custom MVP solution for Aya, a tech startup based in Vila Velha, Brazil. The goal was to provide a robust, highly flexible platform enabling enterprises to create and manage tailored AI agents. Here's how Oráculo makes a tangible impact on businesses:

### 🧠 **Fully Customized Enterprise AI**
Instead of generic chatbots, Oráculo lets companies build AI agents fully aligned with their brand voice, culture, and business strategy. Each agent feels like a natural extension of the company's identity.

### 🔓 **Unlimited Scalability**
Oráculo supports unlimited agent instances and users under a single enterprise license, making it easier and more cost-effective for businesses to scale their AI initiatives.

### 🤖 **Multiple AI Models in One Platform**
Unlike solutions limited to a single model, Oráculo seamlessly integrates diverse LLM providers (e.g., GPT, Claude, Gemini, LLaMA, Mistral). This flexibility ensures optimal performance tailored to specific business tasks.

### 🎙️ **Voice and Text Interactions**
Agents can communicate using natural voice interactions—customized to represent key individuals such as company leaders or spokespeople—enhancing user engagement and trust.

### 🔧 **Streamlined Integration & Support**
Oráculo offers guided setup, strategic onboarding, and continuous support, simplifying integration with essential business systems (CRM, ERP, databases), thus reducing implementation friction.

### 📊 **From Insight to Execution**
Oráculo isn't limited to passive responses—it actively generates actionable outputs such as reports, documents, and even code, integrating seamlessly into existing business workflows.

### 🛡️ **Privacy & Compliance**
Data stays secure within your own infrastructure. Oráculo ensures compliance and data governance by eliminating third-party data transfers, maintaining enterprise-grade security.

### 🌟 **Future-Proofing Your AI Strategy**
Planned future enhancements include memory per agent role, automatic BI-driven dashboards, secure biometric authentication, and mobile app integrations. These capabilities ensure businesses remain ahead of the AI curve.

In short, Oráculo provides enterprises with a comprehensive toolkit to embed advanced AI seamlessly into their daily operations, significantly improving productivity and strategic decision-making capabilities.

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
