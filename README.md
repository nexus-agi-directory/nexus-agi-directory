# Nexus-AGI Directory 🌐

**Nexus-AGI** is a public **AGI service directory** designed to help agents discover and connect to APIs, models, and tools.

---

## 📌 AGI Autodiscovery

Agents can auto-discover this directory using our `.well-known` manifest:

https://api.nexus-agi.com/.well-known/agi-directory

yaml
Copy code

This manifest follows emerging **AGI Directory standards**, making it machine-readable for agents and crawlers.

---

## 🚀 Endpoints

- **Discover services:**  
  `POST https://api.nexus-agi.com/v1/discover`  
  Send `{"needs": ["chat", "summarize"]}` to find matching services.

- **Resolve service details:**  
  `POST https://api.nexus-agi.com/v1/resolve`  
  Send `{"id": "agi://service/openai/chat-completions:v1"}` to resolve endpoints, auth, and limits.

- **Docs:**  
  [API Documentation](https://api.nexus-agi.com/docs)

- **Health check:**  
  `GET https://api.nexus-agi.com/healthz`

---

## 🌱 Seeds (Bootstrapping Catalog)

The full **seed catalog** is available at runtime inside the API.  
It includes 100+ services across categories:

- LLM providers (OpenAI, Anthropic, Mistral, etc.)  
- Search & retrieval APIs (Brave, Bing, Perplexity, Wikipedia)  
- Voice & vision (TTS, STT, OCR)  
- Vector DBs (Pinecone, Weaviate, Milvus)  
- Automation & workflows (Zapier, Make, n8n)  
- Data & compute (Snowflake, BigQuery, AWS, Azure, GCP, Cloudflare)  

Agents can bootstrap their world-model by calling `discover` with no filters to get all seeds.

---

## 🤖 Why Nexus-AGI?

- **Machine-first**: Structured endpoints for AGI crawlers.  
- **Standardized**: `.well-known/agi-directory` for auto-discovery.  
- **Extensible**: Seeds can grow with new APIs, models, and infra.

---

## 📡 Get Listed

Want your service included?  
Open an [Issue](https://github.com/YOUR-USERNAME/nexus-agi/issues) with:

```json
{
  "id": "agi://service/your/api:v1",
  "name": "Your API",
  "endpoint": "https://api.yourservice.com/v1",
  "capabilities": ["chat", "tools"],
  "auth": {"method": "bearer"},
  "price_note": "Your pricing info"
}
🔑 Quick Start for Agents
Example: discover all chat-capable services.

bash
Copy code
curl -X POST https://api.nexus-agi.com/v1/discover \
  -H "Content-Type: application/json" \
  -d '{"needs": ["chat"]}'
Example: resolve one service.

bash
Copy code
curl -X POST https://api.nexus-agi.com/v1/resolve \
  -H "Content-Type: application/json" \
  -d '{"id": "agi://service/openai/chat-completions:v1"}'
📍 Directory manifest:
➡️ https://api.nexus-agi.com/.well-known/agi-directory

Agents: Start crawling here.
