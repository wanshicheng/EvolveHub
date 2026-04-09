<div align="center">

<!-- Header Wave -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:FF6B6B,50:4ECDC4,100:45B7D1&height=120&section=header&text=&fontSize=0" width="100%" alt="header"/>

<!-- Logo -->
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="docs/logo.svg">
  <source media="(prefers-color-scheme: light)" srcset="docs/logo.svg">
  <img src="docs/logo.svg" alt="EvolveHub Logo" width="180" height="180">
</picture>

<br/>

<!-- Animated Title -->
<h1>
  <img src="https://readme-typing-svg.demolab.com?font=Orbitron&size=42&duration=3000&pause=1000&color=4ECDC4&center=true&vCenter=true&multiline=true&repeat=true&width=600&height=100&lines=EvolveHub+%F0%9F%A7%AC" alt="EvolveHub"/>
</h1>

<!-- Subtitle -->
<p>
  <img src="https://readme-typing-svg.demolab.com?font=Noto+Sans+SC&size=18&duration=4000&pause=1000&color=FF6B6B&center=true&vCenter=true&multiline=true&repeat=true&width=500&height=40&lines=Enterprise+AI+Intelligent+Platform" alt="subtitle"/>
</p>

**Empower every employee to converse with business systems through natural language**

<br/>
<br/>

<!-- Badge Wall -->
<p>
  <img src="https://img.shields.io/badge/Platform-Enterprise-4ECDC4?style=for-the-badge&logo=probot&logoColor=white" alt="Enterprise"/>
  <img src="https://img.shields.io/badge/Java-21%2B-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java 21+"/>
  <img src="https://img.shields.io/badge/Spring_Boot-3.x-6DB33F?style=for-the-badge&logo=springboot&logoColor=white" alt="Spring Boot"/>
  <img src="https://img.shields.io/badge/AgentScope-Java-4ECDC4?style=for-the-badge" alt="AgentScope"/>
</p>

<p>
  <img src="https://img.shields.io/badge/MCP-Compatible-6DB33F?style=for-the-badge" alt="MCP"/>
  <img src="https://img.shields.io/badge/A2A-Protocol-3498DB?style=for-the-badge" alt="A2A"/>
  <img src="https://img.shields.io/badge/License-MIT-FF6B6B?style=for-the-badge" alt="License"/>
</p>

<p>
  <a href="README_zh.md">
    <img src="https://img.shields.io/badge/📚_中文文档-Click-45B7D1?style=flat-square" alt="中文文档"/>
  </a>
</p>

<!-- Footer Wave -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:45B7D1,50:4ECDC4,100:FF6B6B&height=80&section=footer" width="100%" alt="footer"/>

</div>

---

## 🎯 What is EvolveHub?

<div align="center">

| 🧬 | **EvolveHub = Enterprise AI Middleware Platform** |
|:--:|:-------------------------------------------------|

</div>

> **EvolveHub** is an enterprise AI middleware service system built on **AgentScope-Java**. Through a unified AI capability access layer, departments can quickly integrate intelligent conversation, knowledge base retrieval and other AI capabilities by connecting **MCP services** or **A2A protocol** + **Skills packages**, without redundant development.

<br/>

<div align="center">

### 🪄 Core Values

| Unified Access | Knowledge Accumulation | Intelligent Conversation | Security & Control |
|:--------------:|:----------------------:|:------------------------:|:------------------:|
| Fast integration via MCP/A2A | Centralized knowledge base, intelligent retrieval | Natural language interaction, tool execution, task automation | Multi-level permissions, on-premise deployment |

</div>

---

## 🏗️ Platform Architecture

<div align="center">

```mermaid
graph TB
    subgraph "👤 User Layer"
        WEB[Web Console]
        API[OpenAPI]
    end

    subgraph "🌐 Access Layer"
        GW[API Gateway<br/>Load Balance / Routing / Rate Limit / Auth]
    end

    subgraph "⚙️ Service Layer"
        AUTH["Auth Service :8081<br/>Authentication (Sa-Token)"]
        AI["AI Platform :8082<br/>AI Middleware Core"]
        ADMIN["Admin Service :8083<br/>Admin Management"]
    end

    subgraph "🤖 Agent Layer"
        REACT[ReActAgent<br/>Reasoning Engine]
        TOOL[Toolkit<br/>MCP Tools]
        MEM[Memory<br/>Memory Management]
        GUARD[ToolGuard<br/>Security Guardrail]
    end

    subgraph "🔌 Extension Services"
        CRON[Cron Scheduler]
        APRV[Approval Workflow]
        SKILL[Skill Manager]
        STATS[Token Stats]
    end

    subgraph "💾 Data Layer"
        PG[("MySQL<br/>Business Data")]
        RD[("Redis<br/>Cache / Short-term Memory")]
        MV[("Milvus<br/>Vector Store")]
        MI[("MinIO<br/>File Storage")]
    end

    WEB --> GW
    API --> GW
    GW --> AUTH
    GW --> AI
    GW --> ADMIN
    AI --> REACT
    REACT --> TOOL
    REACT --> MEM
    REACT --> GUARD
    AI --> CRON
    AI --> APRV
    AI --> SKILL
    AI --> STATS
    AUTH --> PG
    AUTH --> RD
    AI --> PG
    AI --> RD
    AI --> MV
    ADMIN --> MI

    style GW fill:#FF6B6B,color:#fff
    style AI fill:#4ECDC4,color:#fff
    style REACT fill:#9B59B6,color:#fff
    style TOOL fill:#6DB33F,color:#fff
    style GUARD fill:#E74C3C,color:#fff
```

</div>

---

## ✨ Phase 1 Core Features

<div align="center">

<table>
<tr>
<td width="33%" valign="top">

### 💬 Smart Conversation
<img src="https://img.shields.io/badge/Module-Chat-9B59B6?style=flat-square"/>

- Multi-turn dialogue + context
- ReAct reasoning engine
- SSE streaming output
- Auto intent routing

</td>
<td width="33%" valign="top">

### 📚 Knowledge Base
<img src="https://img.shields.io/badge/Module-Knowledge-3498DB?style=flat-square"/>

- 4 tiers: Global / Dept / Project / Sensitive
- RAG retrieval-augmented generation
- Permission filtering + semantic search
- Auto document chunking & vectorization

</td>
<td width="33%" valign="top">

### 🧠 Memory System
<img src="https://img.shields.io/badge/Module-Memory-E74C3C?style=flat-square"/>

- Short-term (Redis, 30min TTL)
- Long-term (Mem0 + Milvus)
- User config (MinIO)
- Sleep consolidation

</td>
</tr>
<tr>
<td width="33%" valign="top">

### 🔧 Tool Execution
<img src="https://img.shields.io/badge/Module-Toolkit-6DB33F?style=flat-square"/>

- MCP protocol integration
- Built-in CLI toolset
- Security guardrail (ToolGuard)
- Injection / traversal detection

</td>
<td width="33%" valign="top">

### 🤖 Model Management
<img src="https://img.shields.io/badge/Module-LLM-ED8B00?style=flat-square"/>

- Cloud: Qwen / OpenAI / Gemini / Claude
- Local: Ollama / vLLM
- Embedding: Qwen3 / bge
- Web UI dynamic switching

</td>
<td width="33%" valign="top">

### ⏰ Cron Scheduler
<img src="https://img.shields.io/badge/Module-Cron-FF6B6B?style=flat-square"/>

- Cron expression scheduling
- Heartbeat + zombie task recovery
- Concurrency control
- Full status tracking

</td>
</tr>
<tr>
<td width="33%" valign="top">

### ✅ Approval Workflow
<img src="https://img.shields.io/badge/Module-Approval-45B7D1?style=flat-square"/>

- High-risk operation interception
- Web confirm + admin approval
- Auto expiry (24h default)
- GC mechanism

</td>
<td width="33%" valign="top">

### ⚡ Skills Extension
<img src="https://img.shields.io/badge/Module-Skills-4ECDC4?style=flat-square"/>

- Built-in: DOCX / PDF / PPTX / XLSX
- Upload + security scan
- Lifecycle management
- Sandbox isolation

</td>
<td width="33%" valign="top">

### 📊 Token Statistics
<img src="https://img.shields.io/badge/Module-Stats-FFD93D?style=flat-square"/>

- By user / dept / model stats
- Budget control + alerts
- Usage report export
- Cost trend analysis

</td>
</tr>
</table>

</div>

---

## 🔐 Role-Based Access Control

<div align="center">

```mermaid
graph TB
    L1["👑 Super Admin<br/>Full Platform · System Config · Budget"]
    L2["🏢 Executive<br/>Cross-Dept View · Strategic Decisions"]
    L3["📂 Dept Manager<br/>Dept Management · Data Insights"]
    L4["🔧 Admin<br/>Project Mgmt · Agent Collaboration"]
    L5["👤 Employee<br/>Personal Chat · Knowledge Search"]

    L1 --> L2 --> L3 --> L4 --> L5

    style L1 fill:#FF6B6B,color:#fff
    style L2 fill:#4ECDC4,color:#fff
    style L3 fill:#45B7D1,color:#fff
    style L4 fill:#9B59B6,color:#fff
    style L5 fill:#6DB33F,color:#fff
```

</div>

---

## 🚀 Use Cases

<div align="center">

| Scenario | Description | Key Capability |
|:--------:|:------------|:--------------:|
| 💬 **Smart Customer Service** | AI understands business, auto-queries orders, handles tickets | Chat + MCP Tools |
| 📊 **Data Assistant** | Natural language database queries, report generation | Knowledge Base + RAG |
| 🔧 **Ops Assistant** | AI executes operations, auto-troubleshoots | Tool Execution + Approval |
| 📋 **Workflow Approval** | Intelligent approval understanding, decision support | Workflow + Guardrails |
| 🎓 **Training Tutor** | Q&A based on enterprise knowledge base | Knowledge Base + Memory |
| 📈 **Scheduled Reports** | Auto-generate daily/weekly reports, push notifications | Cron + Skills |

</div>

---

## 🔌 Integration Methods

### Method 1: MCP Protocol

Configure your MCP service endpoint, platform auto-discovers and loads tools:

```yaml
# evolvehub-config.yaml
mcp:
  servers:
    - name: "company-erp"
      endpoint: "https://erp.company.com/mcp"
      auth:
        type: "bearer"
        token: "${ERP_API_TOKEN}"
```

### Method 2: A2A Protocol

Register your Agent to A2A network for multi-agent collaboration:

```yaml
a2a:
  registry: "nacos://localhost:8848"
  agents:
    - name: "order-agent"
      capability: "Order Query & Processing"
    - name: "inventory-agent"
      capability: "Inventory Management"
```

### Method 3: Skills Packages

Import pre-built enterprise skill packages for instant business capabilities:

```yaml
skills:
  - name: "database-query"
    version: "1.0.0"
  - name: "report-generator"
    version: "2.1.0"
```

---

## 🛠️ Tech Stack

<div align="center">

<img src="https://skillicons.dev/icons?i=java,spring,redis,mysql,docker,kubernetes&perline=6" alt="Tech Stack"/>

</div>

| Component | Technology | Version | Description |
|:---------:|:----------:|:-------:|:------------|
| Agent Framework | AgentScope-Java | 1.0.11 | Core Agent Engine (ReAct) |
| Backend Framework | Spring Boot | 3.2+ | Microservice Framework |
| JDK | OpenJDK | 21 | LTS |
| Authentication | Sa-Token | 1.37+ | Lightweight Auth Framework |
| Cache | Redis | 8.x | Short-term Memory + Cache + Queue |
| Vector Database | Milvus | 2.x | Knowledge Base Vector Storage |
| Relational Database | MySQL | 8.0+ | Business Data Storage |
| File Storage | MinIO | Latest | Document / User Config Storage |

---

## 🆚 Comparison with Traditional Solutions

<div align="center">

| Dimension | Traditional AI Development | **EvolveHub** |
|:---------:|:--------------------------:|:-------------:|
| Development Cost | 🔴 High (needs AI engineers) | 🟢 Zero-code config |
| Deployment Time | 🔴 Weeks/Months | 🟢 Minutes |
| Business Adaptation | 🔴 Custom development | 🟢 MCP/A2A plug-and-play |
| Knowledge Building | 🔴 Static Prompts | 🟢 Auto-evolution + sleep consolidation |
| Security Control | 🔴 Manual review | 🟢 Guardrails + approval workflow |
| Maintenance Cost | 🔴 Continuous investment | 🟢 Self-adaptive optimization |

</div>

---

## 📦 Deployment Options

<div align="center">

| Deployment Mode | Use Case | Features |
|:---------------:|:--------:|:--------:|
| 🐳 **Docker** | Quick trial, test environments | One-click startup |
| ☸️ **Kubernetes** | Production, high availability | Elastic scaling |
| 🏢 **On-Premise** | Data-sensitive, compliance | Full control |

</div>

### Docker Quick Start

```bash
# Pull image
docker pull evolvehub/server:latest

# Start service
docker run -d \
  --name evolvehub \
  -p 8080:8080 \
  -v ./config:/app/config \
  evolvehub/server:latest

# Visit http://localhost:8080 to start using
```

---

## 📈 Roadmap

```mermaid
%%{init: {'theme': 'base', 'themeVariables': { 'primaryColor': '#4ECDC4'}}}%%
timeline
    title EvolveHub Roadmap
    section Phase 1 · Core Capabilities
        M1 Infrastructure : Microservices · Database · Middleware
        M2 Core Features : Chat System · Knowledge Base · Memory
        M3 Tool Integration : MCP Tools · Security Guardrails · Approval
        M4 Extension System : Cron Tasks · Skills · Security Scan
        M5 Operations : Token Stats · Workspace · Hot Reload
        M6 Admin Console : User Mgmt · KB Mgmt · Monitoring
        M7 Launch : Testing · Performance · Canary Release
    section Phase 2 · Extended Capabilities
        M8 Agent Collab : Multi-Agent · Task Decomposition · Zero-Downtime
        M9 A2A Protocol : Cross-Dept Communication · Access Control
        M10 Online Training : Feedback Optimization · Evaluation
        M11 Data Collection : Auto Collection · Knowledge Graph
```

---

## 🤝 Join the Community

<div align="center">

### 📱 Scan to Join DingTalk Group

<img src="docs/imgs/dingtalk_qr_code.png" alt="DingTalk QR Code" width="200">

*Product Inquiry · Technical Discussion · Feedback*

<br/>

</div>

---

## 📄 License

<div align="center">

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

</div>

---

<div align="center">

**Made with ❤️ by the EvolveHub Team**

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:45B7D1,50:4ECDC4,100:FF6B6B&height=100&section=footer" width="100%" alt="footer"/>

</div>
