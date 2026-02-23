Perfect. Below is the Production-Ready PRD + API Contract + Database Schema Pack for DocaDoca.

This is structured so you can hand it directly to a dev (or yourself in builder mode) and start implementation.


---

📘 DOCA DOCA

Product Requirements Document (PRD)


---

1️⃣ Product Summary

DocaDoca is an AI-powered document generation platform that:

Routes users through intelligent onboarding

Recommends 5 curated templates at a time

Allows smart search

Supports Quick or Custom generation

Offers branding & CSS customization

Gates full document after 2-page preview

Captures email before unlock

Offers eSign when relevant

Suggests related documents

Enables document bundling



---

2️⃣ Core User Flow

Step 1: Onboarding

Category (max 3)

Intent

Reading Mode

Depth


Step 2: Lifecycle inference

Current situation

Biggest friction


Step 3: Show 5 templates

Paginated

Search available


Step 4: Template selection

Step 5: Fork

⚡ Generate Now

🎨 Customize & Build


Step 6: Generate doc

Step 7: Preview (2 pages visible)

Step 8: Email gate unlock

Step 9:

Download

Offer eSign

Suggest related docs



---

3️⃣ Functional Requirements


---

3.1 Template System

Store template metadata

Rank by category + intent + reading mode

Return 5 at a time

Support cursor-based pagination

Support search by title/tags



---

3.2 Document Generation

Support formats:

HTML (primary internal format)

PDF

DOCX

Markdown

PPTX (optional later)


Must:

Render structured content

Apply reading mode tone

Apply depth expansion

Support branding injection

Support CSS override (HTML/PDF)



---

3.3 Preview Gating

Show first 2 pages

Blur or lock overlay

Disable scroll past page 2

Unlock on email submission



---

3.4 Email Capture

On unlock:

Save email

Tag with:

Template ID

Category

Intent

Mode

Format


Send email with:

Online link

Download links

Suggested related docs




---

3.5 eSign

If esign_relevant = true on template:

Offer eSign

Allow:

Signer roles

Signature/date/initials


Inject signature blocks



---

3.6 Related Documents

Each template must define:

{
  "related_templates": ["tpl_002", "tpl_003"]
}

After generation, show 2–3 related suggestions.


---

4️⃣ API CONTRACTS

Base: /api/v1/


---

Templates

GET /templates/recommend

Query:

categories[]
intent
reading_mode
depth
context_mode
limit=5
cursor=

Response:

{
  "templates": [],
  "next_cursor": "abc123"
}


---

GET /templates/search?q=

Response:

{
  "results": []
}


---

GET /templates/:id

Returns full template definition.


---

Documents

POST /documents/generate

Body:

{
  "template_id": "",
  "generation_mode": "quick|custom",
  "format": "pdf|docx|html|markdown",
  "answers": {},
  "branding": {},
  "reading_mode": "",
  "depth": ""
}

Response:

{
  "doc_id": "",
  "page_count": 12,
  "assets": {
    "html": "",
    "pdf": "",
    "docx": ""
  },
  "esign_relevant": true
}


---

GET /documents/:id/preview?page_limit=2

Response:

{
  "preview_pages": [],
  "is_gated": true
}


---

POST /documents/:id/unlock

Body:

{
  "email": "",
  "consent": true
}

Response:

{
  "unlocked": true,
  "full_access_url": ""
}


---

eSign

POST /documents/:id/esign

Body:

{
  "signers": [],
  "fields": ["signature", "date"]
}

Response:

{
  "esign_added": true
}


---

Leads

POST /leads

Body:

{
  "email": "",
  "tags": []
}


---

5️⃣ DATABASE SCHEMA

PostgreSQL


---

templates

CREATE TABLE templates (
  id UUID PRIMARY KEY,
  name TEXT NOT NULL,
  description TEXT,
  category TEXT[],
  intent TEXT[],
  reading_modes TEXT[],
  depth_levels TEXT[],
  esign_relevant BOOLEAN DEFAULT FALSE,
  related_templates UUID[],
  complexity TEXT,
  estimated_time_minutes INT,
  created_at TIMESTAMP DEFAULT NOW()
);


---

documents

CREATE TABLE documents (
  id UUID PRIMARY KEY,
  template_id UUID REFERENCES templates(id),
  generation_mode TEXT,
  format TEXT,
  reading_mode TEXT,
  depth TEXT,
  branding JSONB,
  page_count INT,
  esign_added BOOLEAN DEFAULT FALSE,
  created_at TIMESTAMP DEFAULT NOW()
);


---

document_assets

CREATE TABLE document_assets (
  id UUID PRIMARY KEY,
  document_id UUID REFERENCES documents(id),
  format TEXT,
  file_url TEXT,
  created_at TIMESTAMP DEFAULT NOW()
);


---

leads

CREATE TABLE leads (
  id UUID PRIMARY KEY,
  email TEXT NOT NULL,
  tags TEXT[],
  created_at TIMESTAMP DEFAULT NOW()
);


---

style_profiles

CREATE TABLE style_profiles (
  id UUID PRIMARY KEY,
  name TEXT,
  logo_assets JSONB,
  theme JSONB,
  typography_preset TEXT,
  border_style TEXT,
  css_asset_id UUID,
  created_at TIMESTAMP DEFAULT NOW()
);


---

6️⃣ EVENT SYSTEM (Optional but Powerful)

Add event tracking:

CREATE TABLE events (
  id UUID PRIMARY KEY,
  event_type TEXT,
  metadata JSONB,
  created_at TIMESTAMP DEFAULT NOW()
);

Track:

template_viewed

template_selected

document_generated

email_unlocked

esign_enabled

related_clicked


This powers analytics + conversion optimization.


---

7️⃣ Security Considerations

Signed URLs for document access

Expiring unlock tokens

Rate limiting on generation

Validate CSS uploads

Sanitize user inputs before rendering HTML

Prevent script injection



---

8️⃣ MVP Build Order (Realistic)

Phase 1:

Template catalog

Generate HTML

2-page preview gate

Email capture

Download HTML/PDF


Phase 2:

DOCX export

Guided branding

Related docs


Phase 3:

CSS upload

eSign integration

Saved accounts



---

9️⃣ Monetization Strategy (Foundation)

Free:

Limited templates

2-page preview gate

Download after email


Paid:

Unlimited docs

Save history

Style profiles

eSign

Premium templates

Bulk export



---

🔟 Final Architecture Summary

Frontend: Next.js
Backend: Fastify + PostgreSQL
AI Orchestration: MCP tool layer
Storage: S3-compatible
Email: SendGrid/Mailgun
Queue: BullMQ

Modular monolith now → microservices later.


---

If you want next, I can generate:

📁 Exact repo starter structure with file contents

🧠 The complete MCP system prompt (production ready)

🚀 A 30-day build roadmap

💰 Monetization & pricing tiers model

🎨 Brand system for DocaDoca


Which direction are we taking next?
