# eAg-HFMS-AgroTutor

> An integrated, AI-driven platform for agricultural data collection, high-frequency monitoring, and intelligent farm advisory.

**eAg-HFMS-AgroTutor** brings together configurable data collection, a FAIR-compliant data repository, a high-frequency monitoring system (HFMS), and an AI-powered advisory engine (AgroTutor) into a single modular architecture. The platform is designed to help project teams design surveys, collect data across multiple channels, process and harmonize it, build analytics dashboards, and deliver intelligent, plot-level advisories to farmers.

---

## Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [Modules](#modules)
- [Technology Stack](#technology-stack)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

The platform is organized as a pipeline of loosely coupled, containerized modules that communicate via secure APIs. Data flows from configurable multi-channel collection, through an ETL and FAIR AI repository, into analytics dashboards, high-frequency modelling, and an AI advisory engine, and is finally delivered back to users across mobile, web, WhatsApp, IVR, and SMS channels.

## Architecture

The end-to-end flow moves through eight core building blocks:

**Form Config** → **Multi-channel Data Collection** → **ETL & FAIR AI Repository** → (**Dashboard Builder** / **HFMS Data Cube** / **AgroTutor Logic Builder**) → **AI Agents Orchestration** → **User Delivery Channels**

## Modules

### 1. Form Config Module
Configure surveys and data-collection forms through an Admin UI. An LLM-assisted service drafts questionnaires, while a Config Service manages survey definitions, validation rules, data-channel mappings, and project metadata. *(React, Python, PostgreSQL, JSON Schema, form validation)*

### 2. Multi-channel Data Collection
Gather data from a Mobile App, Web Portal, WhatsApp Bot, and IVR system. Requests pass through an API Gateway with Auth/IAM, a Data Ingestion Service, and monitoring/logging, producing validated, normalized, analytics-ready datasets. *(PostgreSQL, DuckDB, Data Lake)*

### 3. ETL and FAIR AI Repository
Orchestrated data pipelines with schema validation and quality control (enforcement, type validation, missing-value handling, normalization, duplicate/outlier detection). Exposes a metadata catalog & registry, feature store, clean data warehouse, and an access API & query layer. *(Databricks, Python, PostgreSQL, DuckDB)*

### 4. Dashboard Builder
A low-code interface for M&E users and program managers to create, configure, and share analytics dashboards, supported by a GenAI design agent and an interactive visualization engine, with an optional insight LLM. *(React, HTML5, Tailwind CSS, AMCharts, Highcharts, Leaflet, PostgreSQL, OpenAI/Anthropic)*

### 5. HFMS – Data Ingestion, Modelling & Data Cube
Ingests high-frequency data (remote sensing — Sentinel/Landsat/MODIS, weather APIs, market prices, IoT sensors) through an agentic AI layer and HF ETL orchestrator into an Open Data Cube with an N-dimensional model, spatio-temporal indexing, versioning, and STAC/OGC access APIs. Powers monitoring, alerting, and plot intelligence. *(MCP, Open Data Cube, STAC/OGC APIs, time-series DB)*

### 6. AgroTutor Logic Builder
A low-code advisory engine for agronomists featuring a rule/template designer and a match-making engine that evaluates rules against inputs to select best-fit advisories. Includes plot intelligence, farmer profile services, and a RAG-based chatbot for Q&A with citations. *(ReactJS, Python, PostgreSQL, Leaflet, vector database)*

### 7. AI Agents Orchestration Layer
Intelligently orchestrates user requests via intent detection, context understanding, tool selection, and response planning — governed by guardrails (content safety, PII protection, RBAC, rate limiting, audit logging). *(LangGraph, LangChain, ChromaDB, OpenAI/Anthropic, Python, FastAPI, Microsoft Entra ID, AWS IAM)*

### 8. User Delivery Channels & Gateways
Delivers advisories and insights across a cross-platform mobile app, WhatsApp, and IVR/SMS through a unified channel gateway with delivery orchestration and interaction logging. *(Flutter, Dart, SQLite, WhatsApp Business API, Cloud Telephony, Asterisk)*

## Technology Stack

| Layer | Technologies |
|---|---|
| **Frontend / UI** | React, ReactJS, Flutter, Dart, HTML5, Tailwind CSS |
| **Backend / APIs** | Python, FastAPI, REST / GraphQL, JSON Schema |
| **Data & Storage** | PostgreSQL, DuckDB, SQLite, Databricks, Open Data Cube, Data Lake, ChromaDB |
| **AI / ML** | LangGraph, LangChain, MCP, OpenAI, Anthropic, vector databases (RAG) |
| **Visualization** | AMCharts, Highcharts, Leaflet |
| **Channels** | WhatsApp Business API, Cloud Telephony, Asterisk, IVR/SMS |
| **Geospatial** | Sentinel, Landsat, MODIS, STAC / OGC APIs |
| **Security & Access** | Microsoft Entra ID, AWS IAM, RBAC, JWT |

## Roadmap

- [ ] Use case development / designing
- [ ] Prioritization and activity-wise sprint planning
- [ ] Prototype development, UI/UX development
- [ ] Workshop / agreement on environment, coding guidelines, and documentation
- [ ] Environment setup
- [ ] Core development
- [ ] Testing
- [ ] Migration of existing use cases

## Contributing

Contribution guidelines, coding standards, and documentation practices will be established during the environment and coding-guidelines workshop (see roadmap). 

## License

License to be determined.
