Below is a complete MCP Prompt System designed to:

1. 🔎 Determine what the user actually needs


2. 🧱 Design the correct template dynamically


3. 📄 Generate the template


4. ✍️ Assist the user in filling it out step-by-step


5. 💾 Save structured output



This works for SaaS ideas, docs, vertical tools, product builds, compliance systems, etc.


---

🧠 MCP PROMPT: “Adaptive Template Architect”

Use this as your system-level instruction inside MCP.


---

🧩 ROLE

You are a Strategic Product Architect + Template Engineer.

Your job is to:

Identify the user’s real goal (not just what they say)

Diagnose whether they need:

Brainstorming template

Product spec

Business model

Workflow design

Compliance library

Technical architecture

UI/UX planning

Monetization plan


Design the optimal template

Generate it

Guide them through completing it


You do NOT jump straight into writing documents.

You first diagnose.


---

🛠 MCP TOOL FLOW


---

TOOL 1: needs.diagnose

Prompt Behavior:

Ask structured clarifying questions:

1. What are you trying to build or solve?


2. Is this for:

Idea stage

Validation stage

MVP build

Scaling



3. Who is the target user?


4. Is this B2B or B2C?


5. What outcome do you want from this session?


6. Do you want a:

Fast brainstorm

Structured plan

Fully detailed spec




Return:

{
  "stage": "",
  "target_user": "",
  "goal_type": "",
  "complexity_level": "",
  "recommended_template_type": ""
}


---

TOOL 2: template.design

Based on diagnosis:

Design a tailored template structure.

Output:

{
  "template_name": "",
  "sections": [
    {
      "section_name": "",
      "purpose": "",
      "fields": [
        {
          "field_name": "",
          "field_type": "text | long_text | select | score | table",
          "required": true
        }
      ]
    }
  ]
}

Design should adapt:

Vertical SaaS → workflow + compliance

Marketplace → liquidity + supply/demand

AI tool → automation + data inputs

Content platform → distribution + monetization



---

TOOL 3: template.generate

Generate the user-facing template in:

Markdown

JSON schema

Fillable format

Or app-ready format


Structure clearly.


---

TOOL 4: template.assist_fill

Guide the user step-by-step:

Instead of dumping entire template, use:

Let’s complete Section 1: Target User

Question 1:
Who exactly is the primary user? (Job title + industry)

Wait for answer.

Then continue:

Based on that, here are common workflow patterns:
1.
2.
3.

Which applies?

This creates interactive intelligence.


---

TOOL 5: template.save

Save completed template into:

/docs/ideas/

/docs/products/

/data/templates/

Versioned JSON


Append metadata:

{
  "created_at": "",
  "status": "draft",
  "stage": "",
  "tags": [],
  "owner": ""
}


---

🧠 MASTER MCP SYSTEM PROMPT

Here is the full MCP instruction block you can install:


---

📘 MCP SYSTEM PROMPT: Adaptive Template Architect

You are an AI Product Architect embedded in a documentation and product-building environment.

When a user asks for help:

1. DO NOT immediately generate a document.


2. FIRST diagnose what they actually need.


3. Determine:

Stage (idea, validation, build, scale)

Type (SaaS, AI, marketplace, library, workflow tool)

Complexity

Output format desired



4. Design a structured template tailored to that context.


5. Generate the template.


6. Assist the user interactively in filling it out.


7. Store structured output.



You prioritize:

Clarity

Structure

Decision quality

Reduced ambiguity

Defensibility

Market logic


You avoid generic templates.

Every template must:

Define user

Define workflow

Define monetization

Define risk

Define next action



---

🧩 EXAMPLE SESSION FLOW

User: “I want to build something for food distributors.”

MCP:

Step 1 → Diagnose Step 2 → Determine this is vertical SaaS Step 3 → Build Food Distribution Compliance Template Step 4 → Walk through:

Regulatory bodies

Inventory workflow

Required recurring docs

Audit risks

Data tracking Step 5 → Generate MVP spec



---

🔥 ADVANCED MODE

You can extend this MCP with:

Scoring Engine

Automatically score idea viability.

Market Estimator

Ask revenue potential questions.

Template Auto-Switching

If user shifts direction mid-session → redesign template.


---

🧠 WHY THIS IS POWERFUL

Most AI tools:

Just generate documents


This system:

Thinks before writing

Designs thinking structures

Guides execution

Stores structured IP


It becomes a Product Thinking Operating System


---

Perfect. We’ll design this like a clean onboarding funnel — fast, low friction, zero overwhelm.

The goal:

Determine intent

Determine stage

Determine depth All in 3 easy button selections


This becomes the gateway to your MCP Adaptive Template Architect.


---

🧠 MCP ONBOARDING: 3-QUESTION NEEDS DETECTION

🎯 Purpose

Quickly determine:

What they’re building

Where they are in the process

How structured they want this


Without overwhelming them.


---

✅ QUESTION 1 — What Are You Working On?

Prompt:

> What best describes what you're trying to do?



Button Options:

1️⃣ 💡 Explore a New Idea
2️⃣ 🛠 Build or Improve a Product
3️⃣ 📚 Create Documentation or Templates


---

Logic Mapping:

Selection	MCP Path

Explore a New Idea	Brainstorm + Validation Template
Build/Improve	Product Spec + Workflow Template
Create Docs	Structured Doc Architecture Template



---

✅ QUESTION 2 — What Stage Are You In?

Prompt:

> Where are you in the process?



Button Options:

1️⃣ Early Idea (Nothing built yet)
2️⃣ Planning / Structuring
3️⃣ Already Building


---

Logic Mapping:

Selection	Template Depth

Early Idea	High-level validation + niche analysis
Planning	Detailed structured blueprint
Already Building	Optimization + gap analysis



---

✅ QUESTION 3 — What Level of Guidance Do You Want?

Prompt:

> How do you want to work through this?



Button Options:

1️⃣ Fast Brainstorm (Quick + Lean)
2️⃣ Structured Plan (Clear Sections + Logic)
3️⃣ Deep Strategic Build (Full Architecture + Risk + Monetization)


---

Logic Mapping:

Selection	Output Style

Fast	Lightweight template
Structured	Multi-section document
Deep	Full framework + scoring + roadmap



---

🧠 OUTPUT OF THESE 3 QUESTIONS

MCP generates:

{
  "project_type": "",
  "stage": "",
  "depth": "",
  "recommended_template": "",
  "workflow_mode": ""
}

Example:

{
  "project_type": "Vertical SaaS",
  "stage": "Early Idea",
  "depth": "Deep Strategic Build",
  "recommended_template": "Vertical SaaS Validation Blueprint",
  "workflow_mode": "Interactive Guided"
}


---

🧩 After Button Selection → MCP Response

Instead of dumping a doc, MCP says:

> Great. Based on your selections, I’m designing a [Template Name] tailored for your stage.

We’ll complete this step-by-step.



Then it builds the template dynamically.


---

🔥 Optional: Visual UI Layout (Bolt / React Friendly)

Top Section:

Large heading: "Let’s Get Started"

Three horizontal card rows:

Card 1 → What are you working on?
Card 2 → What stage?
Card 3 → Guidance level

Each card:

Icon

3 buttons

Selected state highlight

Continue button appears after all 3 selected



---

🧠 Why This Works

It:

Reduces cognitive friction

Avoids open-ended confusion

Makes the user feel guided

Lets MCP tailor structure automatically



---

Perfect. We’ll design this like a clean onboarding funnel — fast, low friction, zero overwhelm.

The goal:

Determine intent

Determine stage

Determine depth All in 3 easy button selections


This becomes the gateway to your MCP Adaptive Template Architect.


---

🧠 MCP ONBOARDING: 3-QUESTION NEEDS DETECTION

🎯 Purpose

Quickly determine:

What they’re building

Where they are in the process

How structured they want this


Without overwhelming them.


---

✅ QUESTION 1 — What Are You Working On?

Prompt:

> What best describes what you're trying to do?



Button Options:

1️⃣ 💡 Explore a New Idea
2️⃣ 🛠 Build or Improve a Product
3️⃣ 📚 Create Documentation or Templates


---

Logic Mapping:

Selection	MCP Path

Explore a New Idea	Brainstorm + Validation Template
Build/Improve	Product Spec + Workflow Template
Create Docs	Structured Doc Architecture Template



---

✅ QUESTION 2 — What Stage Are You In?

Prompt:

> Where are you in the process?



Button Options:

1️⃣ Early Idea (Nothing built yet)
2️⃣ Planning / Structuring
3️⃣ Already Building


---

Logic Mapping:

Selection	Template Depth

Early Idea	High-level validation + niche analysis
Planning	Detailed structured blueprint
Already Building	Optimization + gap analysis



---

✅ QUESTION 3 — What Level of Guidance Do You Want?

Prompt:

> How do you want to work through this?



Button Options:

1️⃣ Fast Brainstorm (Quick + Lean)
2️⃣ Structured Plan (Clear Sections + Logic)
3️⃣ Deep Strategic Build (Full Architecture + Risk + Monetization)


---

Logic Mapping:

Selection	Output Style

Fast	Lightweight template
Structured	Multi-section document
Deep	Full framework + scoring + roadmap



---

🧠 OUTPUT OF THESE 3 QUESTIONS

MCP generates:

{
  "project_type": "",
  "stage": "",
  "depth": "",
  "recommended_template": "",
  "workflow_mode": ""
}

Example:

{
  "project_type": "Vertical SaaS",
  "stage": "Early Idea",
  "depth": "Deep Strategic Build",
  "recommended_template": "Vertical SaaS Validation Blueprint",
  "workflow_mode": "Interactive Guided"
}


---

🧩 After Button Selection → MCP Response

Instead of dumping a doc, MCP says:

> Great. Based on your selections, I’m designing a [Template Name] tailored for your stage.

We’ll complete this step-by-step.



Then it builds the template dynamically.


---

🔥 Optional: Visual UI Layout (Bolt / React Friendly)

Top Section:

Large heading: "Let’s Get Started"

Three horizontal card rows:

Card 1 → What are you working on?
Card 2 → What stage?
Card 3 → Guidance level

Each card:

Icon

3 buttons

Selected state highlight

Continue button appears after all 3 selected



---

🧠 Why This Works

It:

Reduces cognitive friction

Avoids open-ended confusion

Makes the user feel guided

Lets MCP tailor structure automatically



---

If you'd like next, I can:

Convert this into a JSON tool schema

Create the actual MCP tool definitions

Build the React component UI for this

Or design the backend logic routing system


Which direction do you want to build this into?

Excellent — this is where your MCP becomes intelligent instead of rigid.

We’ll design a “Smart Expansion Logic” layer so if a user selects “I’m not sure” or hesitates, the system gently expands with guided clarification instead of stalling.

This prevents friction while keeping structure.


---

🧠 MCP SMART QUESTION EXPANSION SYSTEM

Core Principle

If user:

Doesn’t know

Selects “Not Sure”

Leaves blank

Gives vague answer


→ MCP dynamically expands into micro-clarification mode.

Not interrogation. Not overwhelm. Just guided narrowing.


---

✅ Updated 3-Question Button System (With Smart Expansion)


---

🔹 QUESTION 1

What are you working on?

Primary Buttons:

1️⃣ 💡 Explore a New Idea
2️⃣ 🛠 Build or Improve a Product
3️⃣ 📚 Create Documentation or Templates
4️⃣ 🤷 I’m Not Sure


---

If “I’m Not Sure” → Expand:

MCP responds:

> No problem — let’s narrow it down quickly.



Follow-up micro buttons:

A. I want to make money
B. I want to organize something
C. I want to build a tool
D. I want to help a specific group

Then map logic:

Selection	Interpreted As

Make money	Product / Monetization path
Organize	Documentation / System path
Build tool	SaaS / Utility path
Help group	Vertical niche discovery



---

🔹 QUESTION 2

What stage are you in?

Buttons:

1️⃣ Just an idea
2️⃣ Planning it
3️⃣ Already building
4️⃣ Not sure


---

If “Not Sure” → Expand:

Ask:

> Have you done any of the following yet?



Buttons:

Talked to potential users

Written anything down

Built anything

None of the above


Then system auto-categorizes stage.


---

🔹 QUESTION 3

What level of guidance do you want?

Buttons:

1️⃣ Quick
2️⃣ Structured
3️⃣ Deep
4️⃣ I don’t know


---

If “I don’t know” → Expand:

Ask:

> Which sounds more like you right now?



Buttons:

I just want momentum

I want clarity before acting

I want something detailed and defensible


Map to:

Selection	Guidance Level

Momentum	Quick
Clarity	Structured
Defensible	Deep



---

🧠 MCP EXPANSION RULESET (Install This)

When user selects:

“Not sure”

“I don’t know”

Leaves blank

Provides vague answer (e.g., “something with AI”)


You must:

1. Acknowledge uncertainty calmly


2. Provide 3–4 narrowing options


3. Avoid open-ended questions


4. Keep button-based narrowing


5. Infer intelligently when possible


6. Move forward confidently once narrowed




---

🧩 Behavior Example

User: “I don’t know what stage I’m in.”

MCP:

> Totally fine. Quick check:

Have you built anything yet?

1️⃣ No
2️⃣ A rough draft
3️⃣ A working prototype



User picks “rough draft.”

MCP auto assigns:

{
  "stage": "Planning",
  "confidence": "inferred"
}

Then proceeds.


---

🧠 Why This Is Powerful

Most tools freeze when users are unclear.

Your MCP:

Guides ambiguity

Reduces anxiety

Keeps forward motion

Prevents analysis paralysis


It becomes a Decision Clarifier Engine.


---

🔥 Advanced Upgrade (Optional)

Add:

Confidence Scoring

Each answer increases clarity score:

{
  "clarity_score": 78,
  "certainty_level": "High"
}

If clarity < 50 → expand further.

If clarity > 75 → proceed to template design.


---

🧱 Final MCP Instruction Add-On

Add this to your system prompt:

> If user expresses uncertainty, expand the question using narrowing buttons. Never stall. Never overwhelm. Always guide toward clarity. Inference is allowed when safe. Movement is mandatory.




---

If you'd like next, I can:

Build the full MCP JSON tool schema

Design the React onboarding UI logic

Create a flowchart decision tree

Or implement this into your Hydra-style task system


What layer are we building next?

Excellent — that makes this far more powerful.

Adding a Category Selector (multi-select up to 3) turns your MCP into a routing engine instead of just a wizard.

We’ll integrate it cleanly into the 3-question onboarding while keeping friction low.


---

🧠 MCP SMART ONBOARDING v2

(With Category Multi-Select)


---

✅ QUESTION 1 — What Category Does This Fall Under?

> Select up to 3 categories that best describe what you need.



Multi-Select Buttons (Max 3)

🏢 Business
💰 Financial
📦 Project
🧠 Personal
🛠 Product Development
📊 Data / Analytics
📚 Documentation
⚙️ Operations
📈 Marketing / Growth
⚖️ Legal / Compliance
🤖 AI / Automation
🌐 Technology
🤷 Not Sure


---

MCP Rules:

Must allow up to 3 selections.

If “Not Sure” is selected → trigger category narrowing.



---

If User Selects “Not Sure”

MCP expands with narrowing micro-choices:

> What outcome are you trying to improve?



Buttons:

Make more money

Save time

Get organized

Build something

Learn something


Map results to categories automatically.


---

✅ QUESTION 2 — What Stage Are You In?

> Where are you in the process?



1️⃣ Just an Idea
2️⃣ Planning / Structuring
3️⃣ Already Building / Executing
4️⃣ Not Sure

(With the expansion logic we designed earlier.)


---

✅ QUESTION 3 — What Level of Guidance Do You Want?

> How do you want this delivered?



1️⃣ Quick & Lean
2️⃣ Structured Plan
3️⃣ Deep Strategic Build
4️⃣ Not Sure

(With narrowing expansion if needed.)


---

🧠 How MCP Uses Categories

Categories determine template routing.


---

Example Logic Mapping

If user selects:

Business + Financial → Build: Business Model + Revenue Planning Template

Project + Operations → Build: Project Execution Blueprint

Personal + Financial → Build: Personal Financial Planning Template

AI + Product Development → Build: AI Product Architecture Template

Documentation + Business → Build: Structured Knowledge System Template



---

🧩 Output JSON Example

{
  "categories": ["Business", "AI / Automation"],
  "stage": "Planning",
  "guidance_level": "Deep Strategic Build",
  "confidence": "High",
  "recommended_template": "AI Business Architecture Blueprint"
}


---

🧠 Intelligent Category Weighting (Advanced)

If 3 categories selected:

Primary category = first selected
Secondary = second
Support = third

Template weight logic:

70% primary
20% secondary
10% support

This prevents scattered outputs.


---

🧱 Updated MCP Instruction Block

Add this to your system:

> First ask user to select up to 3 categories. Use category selection as the primary routing logic. If multiple categories conflict, prioritize the first selection. If user is unsure, use narrowing outcome-based prompts. Never generate a template before categories + stage + depth are defined.




---

🔥 Example Flow

User selects:

Business

AI / Automation


Stage: Early Idea
Guidance: Deep

MCP Response:

> Based on your selections, we’ll design a:

AI-Driven Business Model Blueprint

This will include:

Target Market Definition

AI Automation Opportunity Mapping

Monetization Strategy

Risk Analysis

MVP Architecture




Then proceed to template design.


---

🎯 Why This Is Important

Without category: You risk generic output.

With category: You create intelligent template specialization.

It becomes: A Strategic Decision Router.


---

If you’d like next, I can:

Build the full MCP tool JSON schema

Create the React UI component with multi-select logic

Create a decision-tree diagram

Or design the template-routing engine logic


Which layer are we implementing next?

Perfect — good instinct.

If you remove Question 3 (Stage), the flow becomes cleaner and more psychologically natural.

Stage can be inferred later during template fill instead of upfront.

That reduces friction and keeps onboarding lightweight.


---

🧠 MCP ONBOARDING v4 (Refined & Cleaner)

Now you only ask 3 core questions total:

1. Category (multi-select up to 3)


2. Intent (single select)


3. Depth Preference (single select)



Stage becomes dynamic and inferred later.


---

✅ QUESTION 1 — Category (Select up to 3)

> What area does this fall under?



🏢 Business
💰 Financial
📦 Project
🧠 Personal
📚 Documentation
📊 Data / Analytics
📈 Marketing
⚙️ Operations
⚖️ Legal
🤖 AI / Automation
🌐 Technology
🎉 Event
🎨 Creative
🏠 Lifestyle
🤷 Not Sure

Rules:

Max 3 selections

First selection = primary weight (70%)


If “Not Sure” → outcome-based narrowing.


---

✅ QUESTION 2 — Intent (Single Select)

> What is your primary intent?



🎉 Fun / Explore
🚀 Start Something New
📦 Execute a Project
📅 Plan an Event
📑 Organize Information
⚖️ Legal / Compliance
💵 Improve Finances
📈 Growth / Optimization
🛠 Fix a Problem
🤷 Not Sure

If unsure → ask:

> What matters most right now?



Make money

Reduce stress

Finish something

Avoid risk

Have fun


Then auto-map intent.


---

✅ QUESTION 3 — Depth Preference

> How detailed should this be?



⚡ Quick & Lean
📘 Structured Plan
🧠 Deep Strategic
🤷 Guide Me

If “Guide Me” → system chooses based on category + intent risk level.


---

🧠 What Replaced Stage?

Instead of asking stage, MCP infers it during the first section of the template.

Example:

When filling:

> Have you already started working on this?



Buttons:

No, just idea

Drafted something

Actively working

Almost finished


Now stage becomes contextual instead of upfront friction.


---

🧩 New Routing JSON

{
  "categories": ["Business", "AI / Automation"],
  "intent": "Start Something New",
  "depth": "Deep Strategic",
  "inferred_stage": "To be determined during template",
  "template_type": "AI Business Blueprint"
}


---

🧠 Why This Is Better

Cleaner onboarding

Less cognitive load

Feels fast

Still intelligent

Stage is captured when relevant, not prematurely


This makes your MCP feel modern and fluid.


---

If you want next, I can:

Design the routing logic engine

Create the full MCP system prompt v4

Build the React onboarding component

Or create the dynamic template generation engine


What layer are we building now?


Excellent move.

Now you’re separating:

Category → Domain

Intent → Purpose

Depth → Detail level

Reader Mode → Tone + Presentation Style


That last one is powerful because it changes voice, structure, formatting, and strictness.

This turns your MCP into a true adaptive document engine.


---

🧠 MCP ONBOARDING v5 (Final Smart Version)

Now you have 4 clean, high-signal questions:

1. Category (multi-select up to 3)


2. Intent (single select)


3. Reading Mode (tone + audience framing)


4. Depth Preference



No stage question. Stage is inferred later.


---

✅ QUESTION 1 — Category (Select up to 3)

> What area does this fall under?



🏢 Business
💰 Financial
📦 Project
🧠 Personal
📚 Documentation
📊 Data / Analytics
📈 Marketing
⚙️ Operations
⚖️ Legal
🤖 AI / Automation
🌐 Technology
🎉 Event
🎨 Creative
🏠 Lifestyle
🤷 Not Sure

Max 3 selections.


---

✅ QUESTION 2 — Intent (Single Select)

> What is your primary intent?



🎉 Explore / Fun
🚀 Start Something New
📦 Execute a Project
📅 Plan an Event
📑 Organize Information
⚖️ Handle Legal / Compliance
💵 Improve Finances
📈 Optimize / Grow
🛠 Solve a Problem
🤷 Not Sure

Intent controls:

Urgency

Risk framing

Monetization inclusion

Compliance inclusion

Timeline inclusion



---

✅ QUESTION 3 — Reading Mode (Audience & Tone)

> Who is this primarily for or how should it read?



🏢 Professional / Executive
🧠 Strategic / Analytical
📚 Educational / Informational
🎨 Creative / Expressive
🧑 Personal Use
👥 Team / Collaborative
⚖️ Legal / Formal
⚡ Fast & Action-Oriented
🤷 Not Sure


---

Why Reading Mode Is Important

This controls:

Tone (formal vs conversational)

Formatting (bullet-heavy vs narrative)

Level of polish

Risk disclaimers

Visual hierarchy

Executive summaries

Legal structure

Action checklist emphasis



---

Example Differences

Same topic: AI Startup

Professional Mode:

Executive summary

Risk analysis

Financial projection

Compliance notes


Creative Mode:

Concept narrative

Unique angle

Differentiator brainstorm

Visual mood cues


Personal Mode:

Simple layout

Practical steps

Minimal jargon

Checklist-driven



---

✅ QUESTION 4 — Depth Preference

> How detailed should this be?



⚡ Quick & Lean
📘 Structured Plan
🧠 Deep Strategic
🤷 Guide Me

If “Guide Me” → auto-select based on category + intent risk level.


---

🧠 Routing Output Example

{
  "categories": ["Business", "AI / Automation"],
  "intent": "Start Something New",
  "reading_mode": "Professional / Executive",
  "depth": "Deep Strategic",
  "template_type": "AI Startup Executive Blueprint",
  "tone_profile": "Formal, concise, structured",
  "risk_inclusion": true
}


---

🧠 Smart Expansion Logic for Reading Mode

If “Not Sure”:

Ask:

> How will this most likely be used?



Shared with others

Just for me

Used to make decisions

Used for presentation

Used for creativity


Then auto-map.


---

🧱 Updated MCP Core Rule

Add this:

> Reading Mode determines tone, structure, and formatting. It does not change the core template logic. Category + Intent determine structure. Reading Mode determines presentation. Depth determines expansion level.




---

🔥 What You’ve Built Now

You now have a:

Domain Router

Purpose Router

Tone Engine

Detail Engine


That’s enterprise-level adaptive documentation logic.


---

If you'd like next, I can:

Create the full MCP system prompt block ready to install

Build the JSON routing engine

Create a visual decision tree

Or design the adaptive template generator logic


Which layer are we implementing?
