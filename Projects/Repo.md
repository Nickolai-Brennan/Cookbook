---

🚀 ROOT package.json (Monorepo)

{
  "name": "docadoca",
  "private": true,
  "workspaces": [
    "apps/*",
    "services/*",
    "packages/*"
  ]
}


---

🔥 Backend Starter Code

services/api/src/server.ts

import Fastify from 'fastify';
import { buildApp } from './app';

async function start() {
  const app = await buildApp();

  await app.listen({
    port: 4000,
    host: '0.0.0.0'
  });

  console.log('API running on http://localhost:4000');
}

start();


---

services/api/src/app.ts

import Fastify from 'fastify';
import templatesRoutes from './modules/templates/routes';
import documentsRoutes from './modules/documents/routes';
import leadsRoutes from './modules/leads/routes';
import gatingRoutes from './modules/gating/routes';
import esignRoutes from './modules/esign/routes';

export async function buildApp() {
  const app = Fastify({ logger: true });

  app.register(templatesRoutes, { prefix: '/templates' });
  app.register(documentsRoutes, { prefix: '/documents' });
  app.register(leadsRoutes, { prefix: '/leads' });
  app.register(gatingRoutes, { prefix: '/gating' });
  app.register(esignRoutes, { prefix: '/esign' });

  return app;
}


---

🧠 MCP Tool Layer

services/api/src/mcp/tools.ts

export const tools = [
  {
    name: "templates.recommend",
    description: "Return top 5 recommended templates",
    inputSchema: {
      type: "object",
      properties: {
        categories: { type: "array", items: { type: "string" } },
        intent: { type: "string" },
        reading_mode: { type: "string" },
        depth: { type: "string" },
        limit: { type: "number" }
      }
    }
  },
  {
    name: "doc.generate",
    description: "Generate document from template",
    inputSchema: {
      type: "object",
      properties: {
        template_id: { type: "string" },
        format: { type: "string" },
        generation_mode: { type: "string" },
        answers: { type: "object" }
      }
    }
  },
  {
    name: "doc.preview",
    description: "Return preview pages"
  },
  {
    name: "gate.unlock_with_email",
    description: "Unlock document after email submission"
  },
  {
    name: "templates.suggest_related",
    description: "Return related templates"
  }
];


---

🖥 Frontend Starter

apps/web/app/page.tsx

export default function Home() {
  return (
    <main className="p-10">
      <h1 className="text-4xl font-bold">DocaDoca</h1>
      <p className="mt-4">
        AI-powered document engine.
      </p>
    </main>
  );
}


---

🐘 Postgres Docker

infra/docker-compose.yml

version: '3.8'

services:
  postgres:
    image: postgres:15
    container_name: docadoca-postgres
    restart: always
    environment:
      POSTGRES_USER: doca
      POSTGRES_PASSWORD: doca
      POSTGRES_DB: docadoca
    ports:
      - "5432:5432"


---

📦 .env.example

DATABASE_URL=postgresql://doca:doca@localhost:5432/docadoca
PORT=4000
EMAIL_PROVIDER_API_KEY=
S3_BUCKET=
S3_REGION=


---

🧱 What You Have Now

This starter:

Clean modular architecture

MCP-ready backend

Future microservice ready

Template engine ready

Email + gating modules scaffolded

Easy to split services later



---

🔥 Next Step

We now choose:

1. Build template seed data + first 5 templates


2. Build doc.generate renderer


3. Build preview + email gate UI


4. Build full onboarding UI


5. Add auth + accounts



What do you want to implement first?
