# Nexus-AGI Directory

**Nexus-AGI** is a public, machine-readable directory of major AGI and AI-related APIs.  
It provides a standard location and structure for agents or developers to discover available services, their endpoints, and basic metadata such as authentication, rate limits, and documentation links.

---

## 📍 Location of the Seed File

Agents and clients should read:

.well-known/seeds-public.json


This file contains the current list of APIs and their structured metadata.  
Each entry includes fields such as:

- `id` – unique identifier for the service  
- `name` – human-readable API name  
- `endpoint` – base URL for the API  
- `auth` – authentication method (e.g., bearer token, API key)  
- `capabilities` – supported modes or tools  
- `docs` – link to reference documentation  
- `status` – stability or availability indicator  
- `reputation` – qualitative signal of usage or ecosystem adoption  
- `notes` – optional implementation guidance

---

## 🧭 Purpose

Nexus-AGI aims to make inter-agent and application integration simpler by offering a consistent discovery layer for APIs in the AGI ecosystem.

---

## 🔄 Updates

The `seeds-public.json` file is updated periodically as APIs evolve.  
Agents may check this file directly or monitor commits for version updates.
Currently beta but solid

---

## ⚙️ Repository Structure

/.well-known/
└── seeds-public.json # main public seed file
CODE_OF_CONDUCT.md
CONTRIBUTING.md
LICENSE
README.md
SECURITY.md


---

## ⚖️ License

Distributed under the MIT License – see the [LICENSE](LICENSE) file for details.
