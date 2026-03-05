# 🚀 Agency Drop-in AI Search Widget  
### Laravel 11 + Llama 3 | Production-Ready AI Upsell System for Web Agencies

A Proof-of-Work system built for modern development agencies to seamlessly upsell an AI Chat Assistant to WordPress and custom web clients.

This project demonstrates how agencies can convert any existing website into a grounded AI-powered knowledge assistant — without hallucinations and without rebuilding the client’s stack.

---

## 🧠 The Idea

Web agencies build hundreds of informational websites.

Clients increasingly want:
- AI chat on their website
- Smart FAQ systems
- Automated support
- Interactive product explanations

Instead of rebuilding each site with AI from scratch, this system allows agencies to:

Paste a client’s URL → Automatically generate a grounded AI assistant → Drop in a React widget → Done.

---

## 🏗 Architecture Overview

Client Website URL  
        ↓  
Laravel 11 API  
- Scrapes content  
- Cleans & chunks text  
- Generates embeddings  
        ↓  
PostgreSQL + pgvector (Supabase)  
        ↓  
Cosine Similarity Search  
        ↓  
Groq Llama-3.3-70B (RAG Prompting)  
        ↓  
React Chat Widget (Drop-in Script)

---

## ⚙️ Tech Stack

### Backend
- PHP 8.3
- Laravel 11
- Supabase PostgreSQL
- pgvector (Vector similarity search)
- Hugging Face Embeddings API
- Groq API (Llama-3.3-70B)

### Frontend Widget
- React
- TypeScript
- Tailwind CSS v4

---

## 🔍 How It Works

### 1️⃣ Website Ingestion

The agency submits a client URL to the Laravel API.

Laravel:
- Crawls the website
- Extracts visible content
- Cleans HTML, scripts, and noise
- Splits text into semantic chunks

---

### 2️⃣ Vectorization (Embeddings)

Each chunk is converted into vector embeddings using Hugging Face models.

Example models:
- sentence-transformers/all-MiniLM-L6-v2

Vectors are stored in PostgreSQL using pgvector.

---

### 3️⃣ Grounded Retrieval (RAG)

When a user asks a question:

1. The question is embedded.
2. A cosine similarity search retrieves the most relevant chunks.
3. The chunks are injected into a system prompt.
4. The request is sent to Groq’s Llama model.

The model is strictly instructed:
Answer only using the provided context.  
If the answer is not found, respond with “I don't know.”

No hallucinations. Fully grounded responses.

---

### 4️⃣ Drop-in Chat Widget

Clients embed the widget using a simple script:

```html
<script src="https://agency-ai-widget.com/widget.js"></script>
<script>
  AgencyAI.init({
    siteId: "CLIENT_SITE_ID"
  });
</script>
```

The widget:
- Uses an isolated React build
- Styled with Tailwind v4
- Supports dark/light themes
- Communicates securely with Laravel backend

No backend modification required on client side.

---

## 🧩 Database Design (Simplified)

### documents table

| Column      | Type          |
|-------------|--------------|
| id          | uuid         |
| site_id     | uuid         |
| content     | text         |
| embedding   | vector(768)  |
| created_at  | timestamp    |

Vector index:

```sql
CREATE INDEX ON documents
USING ivfflat (embedding vector_cosine_ops)
WITH (lists = 100);
```

---

## 🛡 Security & Isolation

- Multi-tenant architecture (isolated by site_id)
- API key per client
- Strict prompt grounding
- Rate limiting
- Server-side embedding only

---

## 📈 Why This Matters for Agencies

This enables agencies to:

- Offer AI as a premium add-on
- Generate recurring revenue
- Provide intelligent customer interaction
- Avoid rebuilding entire websites
- Integrate seamlessly into WordPress or static sites

It turns static websites into interactive AI-driven systems.

---

## 🚀 Future Improvements

- Agency dashboard
- Automated re-crawling scheduler
- Usage analytics
- Conversation memory
- Multilingual embeddings
- Fine-tuned domain models
- Streaming responses
- Webhook integrations

---

## 💡 Example Use Case

Real estate website:

User asks:
“Do you offer apartments in Colombo under 50M LKR?”

System:
- Retrieves relevant listing chunks
- Feeds them to Llama
- Returns grounded answer directly from website data

---

## 🧠 Core Concepts Demonstrated

- Retrieval-Augmented Generation (RAG)
- Vector similarity search
- Multi-tenant SaaS architecture
- Laravel API system design
- AI grounding techniques
- Production-grade AI integration

---

## 📦 Local Development

### Backend

```bash
git clone https://github.com/your-repo/agency-ai-backend
cd agency-ai-backend
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate
php artisan serve
```

---

### Frontend Widget

```bash
git clone https://github.com/your-repo/agency-ai-widget
cd agency-ai-widget
npm install
npm run dev
```

---

## 🎯 Project Goal

This project demonstrates:

- AI integration expertise
- Adaptability to Laravel ecosystem
- Real-world RAG architecture
- Commercial AI product thinking

Built as a deployable system — not just a demo.

---

## 📄 License

MIT License