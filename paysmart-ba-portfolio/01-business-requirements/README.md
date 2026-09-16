# 01 — Business Requirements Document (BRD)

**Technique:** Requirements elicitation & documentation using the BABOK-aligned BRD structure (Executive Summary → Problem Statement → Stakeholder Analysis → Scope → Functional/Non-Functional Requirements → User Stories with Acceptance Criteria)

## Objective
Turn a loosely understood business problem into a single, unambiguous source of truth that executives, engineers, and investors could all sign off on before development started.

## 1. Problem Framing (Situation–Complication–Impact–Question)
Rather than starting with a solution, the problem was framed using SCIQ to force a case for *why change is needed*:

- **Situation:** Millions of small business owners and market sellers in Nigeria operate in cash-based, offline market stalls.
- **Complication:** The transaction flow is entirely manual — prices negotiated verbally, no receipts, no records, and 5+ minute delays counting cash and making change.
- **Impact:** Financially (theft risk, no loan access), operationally (time lost, reconciliation errors), and socially (permanent exclusion from formal credit).
- **Question:** How can a digital platform digitize payments, generate real-time sales data, and align business/technical teams — without requiring smartphones, internet, or high literacy?

## 2. Stakeholder Analysis
Every stakeholder was mapped on a power/interest grid, each with a defined engagement strategy and cadence — not just a name and title:

| Stakeholder | Power/Interest | Primary Need | Engagement Cadence |
|---|---|---|---|
| CEO (Project Sponsor) | High/High | Delivery on investor promises within budget | Weekly steering committee |
| CTO (Technical Lead) | High/High | Unambiguous requirements, no mid-sprint scope creep | Daily standup |
| Market Traders (End Users) | Low/High | Usable without literacy or tech experience | User testing each sprint |
| Investor Representative | High/High | Visible ROI within 12-month window | Monthly board report |
| Central Bank of Nigeria (Regulator) | High/Low-Medium | Full compliance with payment/KYC/AML regulation | As required by approval milestones |
| Partner Microfinance Banks | Medium/High | Reliable data feed for credit assessment | Bi-weekly during integration |
| In-House Development Team | Low/High | Stable requirements, realistic timelines | Daily standups |

*(13 stakeholders were mapped in total, spanning sponsors, regulators, delivery teams, and community gatekeepers — the table above shows a representative sample.)*

## 3. Scope Definition
Each in-scope item for Version 1 was paired with what was deliberately excluded, and *why* — this is what prevents scope disputes later:

| Category | In Scope (V1) | Excluded | Rationale |
|---|---|---|---|
| User Access | Registration via phone number + 4-digit PIN | Email/ID-based registration | Minimizes onboarding friction for fast acquisition |
| Payment Channels | USSD payments | Card payments, QR codes | Prioritizes accessibility for unbanked users with basic phones |
| Data Reporting | PDF/Excel export of transaction reports | Real-time AI-driven analytics | Avoids upfront cost before a baseline dataset exists |
| Account Security | Lockout after 3 failed PIN attempts | Biometric authentication | Standardizes security without requiring high-end hardware |

A mid-project **change request** (a referral rewards feature, ₦200 credit per successful referral) was formally logged into this same table with its own rationale — demonstrating scope changes were governed, not informal.

## 4. Functional & Non-Functional Requirements
**25 functional requirements** were written, each with a unique ID, MoSCoW priority, and traceable source stakeholder. Example:

> **FR-002** (Must Have): *The system SHALL process a USSD payment transaction within 8 seconds of PIN confirmation under normal network conditions.* — sourced from CTO/End Users.

**10 non-functional requirements** each carried a measurable target rather than a vague quality statement. Example:

> **NFR-001** (Performance): *95% of transactions completed in under 10 seconds during peak load of 10,000 concurrent users.*
> **NFR-003** (Security): *AES-256 encryption for stored data; TLS 1.3 for all data in transit.*

## 5. User Stories with Acceptance Criteria
Requirements were made testable by writing them as user stories with Given/When/Then acceptance criteria, each linked back to its functional requirement:

> **PS-US-001 — Register as a new PaySmart user**
> *As a new customer, I want to register with my phone number so that I can start sending and receiving money on PaySmart.*
> - GIVEN I dial \*111# WHEN I enter my phone number and create a 4-digit PIN, THEN my account is created and I receive a confirmation SMS.
> - GIVEN the number is already registered WHEN I try to register, THEN I see a message directing me to the account recovery flow.
> - Linked to: FR-001, FR-002 | Priority: Must Have

## Why this approach
Framing the problem before the solution, tracing every requirement to a stakeholder, and writing testable acceptance criteria are what separate a requirements *document* from a requirements *list* — each layer here exists to make the next deliverable (process design, testing, risk) traceable back to a documented business need.
