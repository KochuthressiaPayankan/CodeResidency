[readme.pdf](https://github.com/user-attachments/files/33211722/readme.pdf)
# CodeResidency

### The Clinical Rotation Simulator for Software Engineers

> **An AI-powered, safe-to-fail simulation platform that prepares computer science students for real-world software engineering.**

[![Status](https://img.shields.io/badge/Status-Architecture%20%26%20Design%20Complete-blue)]()
[![Frontend](https://img.shields.io/badge/Frontend-Next.js-black)]()
[![Backend](https://img.shields.io/badge/Backend-FastAPI-009688)]()
[![AI](https://img.shields.io/badge/AI-Google%20Gemini-4285F4)]()
[![Docker](https://img.shields.io/badge/Containerization-Docker-2496ED)]()

---

## 📌 Overview

**CodeResidency** is an AI-driven simulation platform designed to bridge the gap between theoretical computer science education and real-world software engineering readiness.

Inspired by the concept of **medical clinical rotations**, CodeResidency gives students a safe-to-fail environment where they can practice:

* Understanding ambiguous client requirements
* Debugging production systems under pressure
* Handling simulated incidents and outages
* Participating in technical interviews
* Collaborating through Git
* Resolving merge conflicts
* Communicating technical concepts clearly

The platform combines **Large Language Models, containerized execution environments, and modern web technologies** to create realistic engineering simulations.

---

## 🎯 Problem Statement

Traditional computer science education focuses heavily on:

* Programming syntax
* Algorithms and data structures
* Greenfield development
* Isolated coding exercises

However, professional software engineering also requires:

* Reading and debugging existing code
* Managing ambiguous client expectations
* Responding to production incidents
* Collaborating through version control
* Communicating with technical and non-technical stakeholders

CodeResidency addresses this gap by allowing students to practice these situations before encountering them in real workplaces.

---

## 💡 Proposed Solution

CodeResidency creates realistic, interactive simulations using AI personas and isolated execution environments.

Students interact with:

* AI clients
* AI HR managers
* AI teammates
* Simulated production servers
* Docker-based coding environments

Performance is evaluated using measurable criteria such as:

| Skill                 | What is Evaluated                              |
| --------------------- | ---------------------------------------------- |
| Requirement Discovery | Communication and requirements elicitation     |
| System Recovery       | Debugging and incident response                |
| Version Control       | Git investigation and conflict resolution      |
| Code Quality          | Maintainability and correctness under pressure |
| Communication         | Clarity, professionalism and empathy           |
| Technical Knowledge   | Technical explanations and implementation      |

---

# 🚀 Core Modules

CodeResidency currently consists of four primary simulation modules.

## 1. 🗣️ The Difficult Client

### Requirements Engineering Simulation

The student acts as a freelance developer interviewing an intentionally difficult AI client.

The client may be:

* Vague
* Non-technical
* Contradictory
* Frustrated
* Budget-conscious

The AI maintains a hidden **Truth File** containing critical requirements that the student must discover through effective questioning.

### Example Scenario

> An angry bakery owner needs a website but refuses to pay for hosting.

### Skills Developed

* Active listening
* Requirements elicitation
* Client communication
* Requirement prioritization
* Translating business requirements into technical requirements

### Evaluation

* Communication Clarity — 25%
* Completeness — 40%
* Efficiency — 20%
* Professionalism — 15%

---

## 2. 🚨 The War Room

### Incident Response & SRE Simulation

A high-pressure production outage simulation.

Students are connected to an isolated, malfunctioning Docker environment and must diagnose and resolve the issue within a limited time.

The environment can simulate:

* Memory leaks
* Disk exhaustion
* Crashed processes
* Misconfigured services
* Database connection problems
* Nginx failures

A simulated CTO sends increasingly urgent messages while real-time metrics show system degradation.

### Example Incidents

```text
Node.js server crash
Nginx 502 Bad Gateway
Database connection pool exhaustion
Unbounded log file growth
```

### Skills Developed

* Linux command-line usage
* Log analysis
* Root-cause analysis
* Incident response
* Debugging under pressure

### Evaluation

* Time to Resolution — 35%
* Root Cause Identification — 30%
* Fix Quality — 25%
* Debugging Process — 10%

---

## 3. 🎤 The Gatekeeper

### AI HR Interview & Code Defense

An AI-powered technical and behavioral interview that dynamically adapts to the student's resume.

The student uploads a resume, after which the AI extracts claimed:

* Technologies
* Projects
* Skills
* Leadership experience

The system then generates targeted interview questions.

### Example

If the resume states:

```text
Proficient in SQL
```

The AI may ask:

```text
Write a query to find the second-highest salary.
```

If the resume states:

```text
Built a REST API
```

The AI may ask about:

```text
Idempotency
PUT vs POST
API design
```

The module can also include behavioral questions and an optional coding challenge.

### Skills Developed

* Technical communication
* Resume integrity
* Thinking aloud
* Interview composure
* STAR-based behavioral answering

### Evaluation

* Technical Accuracy — 40%
* Communication — 30%
* Composure — 15%
* Authenticity — 15%

---

## 4. 🔀 The Imposter

### Team Collaboration & Git Simulation

The student works with three AI teammates in a simulated software development team.

An **Imposter AI** secretly introduces a bug into the repository.

The student must investigate the repository history and identify the problematic commit.

### Git Skills Used

```bash
git log
git blame
git bisect
git diff
git revert
git rebase
```

AI teammates can also introduce new commits and merge conflicts during the simulation.

### Example Problems

* Incorrect tax calculation
* Off-by-one errors
* Conflicting changes to the same function
* Misleading commit messages

### Skills Developed

* Git forensics
* Code review
* Bug identification
* Merge conflict resolution
* Safe rollback strategies
* Repository management

---

# 🏗️ System Architecture

CodeResidency uses a modular, decoupled architecture designed for real-time interaction, secure code execution and scalability.

```text
                         ┌──────────────────────┐
                         │     Web Browser      │
                         │                      │
                         │ Next.js │ Monaco     │
                         │ xterm.js│ Chat UI    │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │    API Gateway       │
                         │ Nginx / Load Balancer│
                         └──────────┬───────────┘
                                    │
              ┌─────────────────────┼─────────────────────┐
              ▼                     ▼                     ▼
      ┌──────────────┐      ┌──────────────┐      ┌──────────────┐
      │   Next.js    │      │   FastAPI    │      │   Appwrite   │
      │   Frontend   │      │   Backend    │      │     BaaS     │
      └──────────────┘      └──────┬───────┘      └──────────────┘
                                   │
                    ┌──────────────┼──────────────┐
                    ▼              ▼              ▼
               ┌─────────┐   ┌───────────┐  ┌─────────────┐
               │  AI     │   │  Docker   │  │   Redis /   │
               │ Agents  │   │ Sandbox   │  │ PostgreSQL  │
               └────┬────┘   └───────────┘  └─────────────┘
                    │
                    ▼
             ┌──────────────┐
             │ Gemini API   │
             └──────────────┘
```

---

# 🤖 Dual-Agent AI Architecture

The conversational modules use a **Dual-Agent architecture**.

### Director Agent

The hidden game master responsible for:

* Maintaining the Truth File
* Tracking discovered requirements
* Evaluating communication
* Controlling hints
* Calculating score changes

### Actor Agent

The visible AI persona responsible for:

* Playing the client or character
* Generating natural responses
* Adapting its mood
* Maintaining the assigned personality
* Following Director instructions

```text
Student
   │
   ▼
Frontend
   │
   ▼
FastAPI
   │
   ▼
Director Agent
   │
   ├── Evaluate student input
   ├── Check hidden requirements
   ├── Calculate score
   └── Decide what to reveal
   │
   ▼
Actor Agent
   │
   ▼
Natural AI Response
   │
   ▼
Student
```

This prevents the AI from simply revealing the solution while keeping the simulation dynamic.

---

# 🛠️ Technology Stack

## Frontend

| Technology      | Purpose                   |
| --------------- | ------------------------- |
| Next.js 14+     | Web application           |
| React 18+       | UI components             |
| TypeScript 5+   | Type safety               |
| Tailwind CSS 3+ | Styling                   |
| Monaco Editor   | Browser-based code editor |
| xterm.js        | Web terminal              |
| Socket.io       | Real-time communication   |
| Zustand         | State management          |
| React Hook Form | Form handling             |

## Backend

| Technology   | Purpose               |
| ------------ | --------------------- |
| Python 3.11+ | Backend language      |
| FastAPI      | REST API              |
| LangChain    | AI orchestration      |
| LangGraph    | Multi-agent workflows |
| Pydantic     | Data validation       |
| Uvicorn      | ASGI server           |
| Docker SDK   | Container management  |
| Pytest       | Testing               |

## Database & Infrastructure

| Technology     | Purpose                                     |
| -------------- | ------------------------------------------- |
| Appwrite       | Authentication, database, storage, realtime |
| PostgreSQL     | Primary database                            |
| Redis          | Cache and session store                     |
| Docker         | Secure code execution                       |
| Docker Compose | Local development                           |
| Nginx          | Reverse proxy                               |
| GitHub Actions | CI/CD                                       |
| Prometheus     | Monitoring                                  |
| Grafana        | Visualization                               |
| Loki           | Log aggregation                             |

## AI

| Technology              | Purpose                        |
| ----------------------- | ------------------------------ |
| Google Gemini 1.5 Pro   | Complex reasoning & evaluation |
| Google Gemini 1.5 Flash | Fast conversational responses  |
| LangChain               | Agent framework                |
| LangGraph               | Stateful multi-agent workflows |

---

# 🔐 Security

Code execution takes place inside isolated Docker containers.

Each execution environment is designed with:

```text
CPU Limit       : 0.5 core
Memory Limit    : 256 MB
Network         : Disabled
Execution Limit : 30 seconds
```

Security architecture includes:

* OAuth 2.0 authentication
* JWT sessions
* Role-based access control
* TLS encryption
* AES-256 encryption at rest
* Input validation
* Rate limiting
* Container isolation
* Secret management through environment variables
* Audit logging
* Dependency scanning

---

# 🗄️ Database Structure

The primary entities include:

```text
Users
 │
 ├── Sessions
 │    ├── ChatLogs
 │    ├── CodeSubmissions
 │    ├── TerminalLogs
 │    └── EvaluationReports
 │
 └── Achievements

Modules
 │
 └── Scenarios
       │
       └── Sessions
```

### Main Collections

* `Users`
* `Modules`
* `Scenarios`
* `Sessions`
* `ChatLogs`
* `CodeSubmissions`
* `TerminalLogs`
* `EvaluationReports`
* `Achievements`

---

# 📊 Evaluation System

Each simulation generates measurable performance data.

Example evaluation structure:

```json
{
  "communication_score": 85,
  "technical_score": 80,
  "efficiency_score": 90,
  "overall_score": 85,
  "letter_grade": "B+",
  "strengths": "Clear and structured communication",
  "areas_for_improvement": "Improve requirement coverage"
}
```

Students can receive:

* Numerical scores
* Letter grades
* Strengths
* Areas for improvement
* Rubric-level feedback
* Achievements and badges

---

# 🏆 Achievement System

Example achievements include:

| Achievement             | Requirement                                  |
| ----------------------- | -------------------------------------------- |
| 🎓 Clinical Resident    | Complete all 4 modules                       |
| 💬 Communication Master | Score 90+ in Difficult Client                |
| 🚨 Incident Commander   | Resolve War Room in under 5 minutes          |
| 🔀 Git Expert           | Score 95+ in Imposter                        |
| 💯 Perfect Score        | Achieve 100 in any scenario                  |
| ⚡ Speed Demon           | Complete a module in half the benchmark time |

---

# 📈 Success Metrics

The project targets:

* **90%** student engagement
* **40%** reduction in industry onboarding time
* **85%** positive feedback
* **80%+** hidden requirement discovery
* **95%** success in Git conflict/bad-commit identification
* Production incident resolution target of **under 15 minutes**

---

# 🗺️ Development Roadmap

### Phase 1 — Foundation

* [x] System architecture
* [x] Database schema
* [x] Technology selection
* [x] Dual-Agent AI proof of concept

### Phase 2 — Core Development

* [ ] Next.js frontend
* [ ] FastAPI backend
* [ ] Docker sandbox
* [ ] Appwrite integration

### Phase 3 — Simulation Modules

* [ ] The Difficult Client
* [ ] The War Room
* [ ] The Gatekeeper
* [ ] The Imposter

### Phase 4 — Testing

* [ ] Unit testing
* [ ] Integration testing
* [ ] AI evaluation
* [ ] Beta testing
* [ ] Performance optimization

### Phase 5 — Deployment

* [ ] Production deployment
* [ ] CI/CD pipeline
* [ ] Monitoring
* [ ] Load testing
* [ ] Auto-scaling

### Phase 6 — Launch

* [ ] Educational institution launch
* [ ] User feedback collection
* [ ] Feature iteration
* [ ] Advanced simulation modules

---

# 🔮 Future Features

Planned extensions include:

* **The Code Reviewer**
* **The Database Detective**
* **The Security Audit**
* **The System Designer**
* Instructor dashboard
* Multiplayer simulations
* Custom scenario builder
* AI voice mode
* LMS integrations
* Advanced learning analytics
* Internationalization
* Career-specific learning pathways
* Peer review
* Third-party API integrations

---

# 📂 Suggested Repository Structure

```text
CodeResidency/
│
├── frontend/
│   ├── app/
│   ├── components/
│   ├── hooks/
│   ├── lib/
│   └── public/
│
├── backend/
│   ├── api/
│   ├── agents/
│   │   ├── director/
│   │   ├── actor/
│   │   └── evaluator/
│   ├── modules/
│   ├── services/
│   ├── models/
│   ├── database/
│   └── tests/
│
├── docker/
│   ├── python/
│   ├── node/
│   └── java/
│
├── infrastructure/
│   ├── nginx/
│   ├── prometheus/
│   └── grafana/
│
├── docs/
│
├── docker-compose.yml
├── .env.example
├── README.md
└── LICENSE
```

---

# ⚙️ Development Environment

The documented stack targets:

```text
Node.js / Next.js 14+
Python 3.11+
Docker 24+
Docker Compose 2.24+
PostgreSQL 15+
Redis 7+
Appwrite 1.5+
```

The project documentation specifies Google Gemini API access, OAuth providers, Docker, Appwrite and the supporting infrastructure as part of the intended system.

> **Note:** The project document describes the architecture and technology stack but does not provide a complete verified step-by-step local installation procedure. The commands below should therefore be added once the actual repository implementation is finalized.

---

# 🧪 Testing

The planned testing strategy includes:

* Unit testing
* Integration testing
* AI agent evaluation
* Docker sandbox testing
* API testing
* Performance testing
* Load testing
* Security testing
* Beta testing with student cohorts

Testing tools include:

```text
Pytest
Pytest-Asyncio
Postman
Docker
GitHub Actions
```

---

# 📊 Monitoring

The production architecture uses:

### Prometheus

For collecting:

* HTTP request metrics
* Response times
* Gemini API calls
* Gemini latency
* Active Docker containers
* Container execution duration

### Grafana

Dashboards cover:

* Application health
* User activity
* AI performance
* Docker statistics
* Database performance

### Loki

Used for centralized log aggregation.

---

# 👥 Project Team

**CodeResidency Team — MuLearn SCET**

* Sourav P Bijoy
* Niya Rose
* Richard Martin
* Kochuthressia Payankan

**Project Status:** Architecture & Design Complete
**Document Version:** 1.0
**Last Updated:** February 20, 2026

---

# 🌐 Project

**Website:** [coderesidency.com](https://coderesidency.com)

**Contact:** [coderesidency@mulearn.scet](mailto:coderesidency@mulearn.scet)

---

# 📚 References

The project documentation references research and technical documentation covering:

* Programming education
* Software engineering work practices
* Deliberate practice
* Software errors
* Git collaboration
* Graduate skills gaps
* Gemini API
* Docker security
* Appwrite
* Next.js
* Bloom's Taxonomy
* Reflective practice

---

# ⭐ Vision

> **CodeResidency aims to become the "flight simulator" for software engineers.**

The goal is to ensure that when students write their first line of production code, they have already practiced:

* Extracting requirements from non-technical stakeholders
* Debugging production incidents
* Collaborating through version control
* Explaining technical concepts
* Handling ambiguity
* Working under pressure

**CodeResidency — From classroom coding to real-world engineering readiness.**
