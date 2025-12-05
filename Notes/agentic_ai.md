## 1. Claim Intake (Customer/Agent Interface)

### Agentic AI Role

1. Conversational intake agent collects required information.
2. Dynamically detects missing data and asks follow-up questions.
3. Auto-creates claim record via API.

Tools Used

Form extraction (structured field extractor)

Policy lookup tool

Claim creation API tool

Intake checklist tool (controls required fields)

Why Agentic AI?

Generative AI can answer questions but cannot follow a procedural intake flow.

Agentic AI ensures:

completeness (“I still need your policy number”)
validation (“the image is unclear, please upload again”)
structured output creation

## 2. Document and Evidence Ingestion

### Agentic AI Role

Routing agent decides what each document is (invoice, FIR, bill, medical record).

Orchestrates OCR, image enhancement, and embedding creation.

Decides next steps based on document type.

### Tools Used

1. OCR tool
2. Image quality tool
3. Document classifier tool
4. Embeddings generator
5. File storage API tool

Why Agentic AI?

Because ingestion is a pipeline that must branch intelligently.

Generative AI alone → only explains the file but cannot orchestrate actions.

## 3. Data Enrichment

### Agentic AI Role

Multi-step reasoning: “We need hospital address → fetch address → validate → standardize.”

Calls third-party APIs for enrichment: hospitals, garages, Aadhaar verification, police case lookup.

Fixes missing or inconsistent fields.

### Tools Used

1. External data API wrapper tools
2. Domain validation tools
3. Address standardization tool
4. Policy master lookup tool

Why Agentic AI?

Enrichment is procedural.

Generative AI can infer but cannot execute multi-step workflows with retries, conditional logic, or external integrations.

## 4. Initial Assessment and Triage

### Agentic AI Role

Runs triage decision-tree agent:

1. classifies urgency
2. estimates complexity
3. flags early fraud signals
4. Creates structured triage report.

### Tools Used

1. Triage ML model (tabular model)
2. Rule engine tool
3. Historical case similarity search (embedding-based)

Why Agentic AI?

Because triage is multifactor and has precedence rules (“if accident + nightlife + alcohol flag → route to high-risk”).

Generative AI cannot reliably honor deterministic rules.

## 5. Fraud Detection

Agentic AI Role

Runs multiple tools:

1. Tabular fraud model (XGBoost)
2. Network graph analysis (entity linking)
3. Document authenticity scoring
4. Combines tool outputs using agentic reasoning

Produces a fraud risk score + explanation

### Tools Used

Fraud ML model

1. Image forgery detection tool
2. Network graph lookup tool
3. Claim history search

Why Agentic AI?

Fraud detection requires:

1. model orchestration
2. multiple evidence types
3. cross-source correlation

Generative AI alone is not trustable for fraud decisions.

## 6. Damage Assessment

Agentic AI Role

For motor claims: runs image → damage part segmentation → cost estimation model → part pricing tool.

For health claims: extracts ICD codes, treatment types, verifies cost vs standard benchmarks.

Tools Used

1. Vision model for damage detection
2. Part-price lookup tool
3. Medical coding tool
4. Price benchmarking tool

Why Agentic AI?

Damage assessment requires:

1. multiple ML models
2. cost calculators
3. structured estimation logic

Generative AI cannot compute or enforce pricing rules.

7️⃣ Decision Engine and Auto Settlement
Agentic AI Role

Agent determines:

approve

reject

partial approve

escalate

Validates coverage using:

policy rules

exclusion checks

limit checks

Generates the settlement recommendation.

Tools Used

Policy rule engine

Benefit calculator

Coverage validation tool

Why Agentic AI?

Because settlement = business logic + math + rules.
Generative AI cannot guarantee compliance or deterministic decisions.

8️⃣ Escalation and Human Workbench
Agentic AI Role

Agent detects missing information requiring human approval.

Prepares a structured summary for adjuster.

Suggests next best actions.

Tracks SLAs.

Tools Used

Workbench API tool

SLA timer/queue tool

Explanation generation tool

Why Agentic AI?

Generative AI can summarize, but agentic system ensures:

correct routing

SLA tracking

action orchestration

9️⃣ Customer Communication
Agentic AI Role

Event-driven communication: “document missing”, “inspection scheduled”.

Chooses the right templates + channels (SMS, email, WhatsApp).

Maintains context and communication history.

Tools Used

Notification API tools

Template engine

Language translation tool

Why Agentic AI?

Customer communication must be:

timely

event-based

structured

Generative AI cannot manage state, channels, or events.

🔟 Payment Disbursement & Reconciliation
Agentic AI Role

Agent triggers when settlement approved.

Validates KYC, AML, bank details.

Initiates payment through gateway tools.

Runs reconciliation workflows.

Tools Used

Payment gateway API tool

KYC validation tool

Double-entry ledger tool

Reconciliation tool

Retry engine

Why Agentic AI?

Payments need:

strict sequence

idempotency

validation loops

audit trail

Generative AI cannot enforce financial compliance.

1️⃣1️⃣ Reporting and Analytics
Agentic AI Role

Agent computes KPIs:

claim cycle time

fraud catch rate

settlement ratio

Generates dashboards or writes into warehouse.

Creates automated insights using reasoning.

Tools Used

SQL warehouse tool

Metrics calculator

Insight generation tool

Why Agentic AI?

Analytics requires:

scheduled tasks

queries

aggregation logic

drift detection

Generative AI cannot autonomously run pipelines.

