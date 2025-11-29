# Customer Communication 

This layer ensures that every claim action results in the right message, sent to the right customer, through the right channel, with the right context

### 1. Event-Based Trigger System

Every communication begins with an event coming from the workflow engine or microservices.

Typical events from previous stages

| Stage      | Example Event                           |
| ---------- | --------------------------------------- |
| FNOL       | ClaimReceived, FNOLAcknowledged         |
| Assessment | EstimateReady, InspectionRequired       |
| Fraud      | AdditionalInfoNeeded, FraudCheckPending |
| Settlement | SettlementApproved, SettlementRejected  |
| Payments   | PaymentDisbursed                        |
| Others     | DocumentMissing, CustomerUpdatedPhoto   |

### 2. Template Service vs LLM — The Decision Engine

This component decides FAST whether a communication should come from a template or LLM

#### Template Service (Static Messages)

#### Use when:

Message is simple, factual, low context.
Needs extremely low latency (<5–10 ms).
Must be cost-efficient (no token usage).

#### Examples:

Claim #{{id}} acknowledged
Payment of ₹{{amount}} processed
Document received
“Your appointment is scheduled for {{date}}.”

#### LLM Generation (Dynamic Messages)

Used when communication requires thinking, summarizing, or empathy.

#### Example uses:

Ask for missing photos with context
Explain why documents are insufficient
Discrepancy between GPS location and accident story
Clarify complex policy coverage

### 3. Smart Channel Router

Route messages intelligently based on preferences, urgency, and past failures.

Channel Selection Logic

Primary: customer_preference.preferred_channel
Fallback: customer_preference.fallback_channel
Escalation: SMS if urgent (missing doc, fraud check)
Multi-channel: for high-value claims (>₹1L)

### 4. Delivery Engines (Channel-Specific Services)

#### WhatsApp Business API

Rich media (photos, PDFs)
Buttons, menus, quick replies
End-to-end read receipts

#### Email Service

For long-form messages
For PDF-based settlement letters
Attach payment summary