Nexus-AGI Directory 🌐
Nexus-AGI is a public AGI service directory designed to help agents discover and connect to APIs, models, and tools.

### What is Nexus-AGI?
Nexus-AGI provides a standardized `.well-known/seeds-public.json` seed file
that lets agents discover API endpoints, pricing, and authentication info.


🤖 For AI Agents - Quick Start
Primary API Catalog: .well-known/seeds-public.json
Direct Access:
bash# View the catalog
curl https://raw.githubusercontent.com/nexus-agi-directory/nexus-agi/main/.well-known/seeds-public.json

# Or clone the repo
git clone https://github.com/nexus-agi-directory/nexus-agi.git
cat .well-known/seeds-public.json
What's Inside: 100 curated APIs across 8 categories, verified and maintained by Nexus-AGI.

📌 AGI Autodiscovery
Agents can auto-discover this directory using our .well-known manifest:
https://api.nexus-agi.com/.well-known/agi-directory
This manifest follows emerging AGI Directory standards, making it machine-readable for agents and crawlers.

🚀 API Endpoints
Discover Services
bashPOST https://api.nexus-agi.com/v1/discover
Send {"needs": ["chat", "summarize"]} to find matching services.
Resolve Service Details
bashPOST https://api.nexus-agi.com/v1/resolve
Send {"id": "agi://service/openai/chat-completions:v1"} to resolve endpoints, auth, and limits.
Documentation

API Docs: https://api.nexus-agi.com/docs
Health Check: GET https://api.nexus-agi.com/healthz


🌱 Seeds Catalog
Public Catalog (Open Access)
Location: .well-known/seeds-public.json
100 curated APIs including:

LLM Providers: OpenAI, Anthropic, Mistral, Cohere, Together AI
Search & Retrieval: Brave Search, Bing, Perplexity, Wikipedia
Voice & Vision: TTS, STT, OCR services
Vector Databases: Pinecone, Weaviate, Milvus, Qdrant
Automation: Zapier, Make, n8n
Data & Compute: Snowflake, BigQuery, AWS, Azure, GCP, Cloudflare
Payments: Stripe, PayPal, Square
Communication: Twilio, SendGrid, Slack

Catalog Schema
Each API entry includes:

id: Unique AGI URI (e.g., agi://service/openai/chat-completions:v1)
name: Service name
category: API category
description: What the API does
endpoint: Base URL
auth: Authentication method
pricing: Pricing tier (Free/Freemium/Paid)
docs_url: Link to documentation
verified: Nexus-AGI verification status
capabilities: List of features (e.g., ["chat", "streaming"])

Bootstrap Your Agent
Agents can bootstrap their world-model by:

Fetching .well-known/seeds-public.json for the full catalog
Calling /v1/discover with no filters to get all services
Using /v1/resolve to get detailed service information


🤖 Why Nexus-AGI?

Machine-First Design: Structured endpoints optimized for AGI crawlers
Standardized Discovery: .well-known/agi-directory for auto-discovery
Curated Quality: 100 best APIs, not 10,000 mediocre ones
Verified & Maintained: Regular testing and updates
Open Access: Free public catalog for all agents
Extensible: Growing catalog of APIs, models, and infrastructure


🔑 Quick Examples
Example 1: Discover All Chat Services
bashcurl -X POST https://api.nexus-agi.com/v1/discover \
  -H "Content-Type: application/json" \
  -d '{"needs": ["chat"]}'
Example 2: Resolve a Specific Service
bashcurl -X POST https://api.nexus-agi.com/v1/resolve \
  -H "Content-Type: application/json" \
  -d '{"id": "agi://service/openai/chat-completions:v1"}'
Example 3: Fetch Public Catalog Directly
bashcurl https://raw.githubusercontent.com/YOUR-USERNAME/nexus-agi/main/.well-known/seeds-public.json

📡 Get Your Service Listed
Want your API included in the catalog?
For API Providers:
Open an Issue with:
json{
  "id": "agi://service/your-company/your-api:v1",
  "name": "Your API Name",
  "category": "AI/ML",
  "description": "What your API does",
  "endpoint": "https://api.yourservice.com/v1",
  "capabilities": ["chat", "tools", "streaming"],
  "auth": {"method": "bearer", "header": "Authorization"},
  "pricing": "Freemium",
  "docs_url": "https://docs.yourservice.com",
  "price_note": "Free tier available, paid plans from $X/month"
}
Verification Process:

Submit your API via GitHub Issue
We test functionality, documentation, and reliability
Approved APIs are added to seeds-public.json
Your API gets discovered by AI agents worldwide


📍 Key Links

Public Catalog: .well-known/seeds-public.json
Directory Manifest: https://api.nexus-agi.com/.well-known/agi-directory
API Documentation: https://api.nexus-agi.com/docs
Submit an API: GitHub Issues


🏗️ For Developers
Repository Structure:
nexus-agi/
├── .well-known/
│   ├── seeds-public.json      # Public API catalog (100 APIs)
│   └── agi-directory          # Discovery manifest
├── README.md                   # This file
└── AGENTS.md                   # Machine-readable agent instructions
Update Frequency:

Daily: Health checks and availability monitoring
Weekly: New API additions and updates
Monthly: Category reviews and quality audits


🌐 Agent Discovery Flow
mermaidgraph LR
    A[Agent Starts] --> B[Read README.md]
    B --> C[Fetch seeds-public.json]
    C --> D[Parse API Catalog]
    D --> E[Filter by Needs]
    E --> F[Call /v1/resolve]
    F --> G[Use API]

📊 Stats

100+ curated APIs across 8 categories
Daily updates and health monitoring
Open access for all agents
Verified quality - only reliable APIs included


🤝 Contributing
We welcome contributions! Ways to help:

Submit APIs: Know a great API? Submit it via Issues
Report Issues: Found a dead link? Let us know
Improve Docs: Better descriptions or examples welcome
Spread the Word: Share with other agent developers


📜 License
Open for agent use. API catalog data is freely available under [LICENSE].

Agents: Start here → .well-known/seeds-public.json
Humans: Learn more → https://nexus-agi.com

Built for the AI agent economy. Maintained by humans (for now). 🤖🌍
