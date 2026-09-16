# 04 — UAT Test Cases & Risk Register

**Technique:** Module-based UAT test case design (precondition/steps/expected result) with full requirement traceability, plus a probability × impact risk register with mitigation and contingency planning

## Objective
Define how the platform would be validated before launch, and proactively surface what could derail the project so risks are managed rather than discovered too late.

## Part 1 — UAT Test Cases

Test cases were organized by module (Registration via USSD, Registration via App, Payment via USSD, Payment via App, and more). Every test case carries a unique ID, preconditions, test steps, test data, expected result, a severity-if-fail rating, and traceability back to the user story/functional requirement it validates.

**Example — UAT-TC-001**
| Field | Detail |
|---|---|
| Scenario | New registration via USSD |
| Precondition | Phone number not previously registered |
| Steps | Dial \*111# → Select 'Register' → Enter phone number → Create 4-digit PIN → Confirm |
| Expected Result | Account created; confirmation SMS within 30 seconds; 6-digit Seller ID displayed |
| Severity if Fail | Critical |
| Linked FR | FR-001 |

**Example — UAT-TC-008 (negative test case)**
| Field | Detail |
|---|---|
| Scenario | Incorrect PIN entry leading to account lockout |
| Steps | Initiate a payment → enter incorrect PIN three times |
| Expected Result | Account locks after 3rd failed attempt; user directed to identity verification; no transaction processed |
| Severity if Fail | Critical |
| Linked FR | FR-007 |

Testing deliberately included both **positive paths** (successful registration, successful payment) and **negative/edge cases** (duplicate registration, insufficient balance, invalid Seller ID, no network connectivity) — a test suite that only checks the happy path doesn't validate the requirements that matter most (security, error handling).

## Part 2 — Risk Register

10 risks were logged across regulatory, technical, user adoption, security, financial, project management, integration, infrastructure, fraud, and marketing categories. Each has a probability × impact rating, a named **owner**, a preventive **mitigation strategy**, and a reactive **contingency plan**.

| Risk | Category | Rating | Mitigation | Contingency | Owner |
|---|---|---|---|---|---|
| CBN regulatory approval delayed beyond Month 2 | Regulatory | High | Engage regulatory consultants early; weekly CBN follow-ups | Continue non-regulated modules; revise schedule | CEO / Legal |
| USSD gateway outages during peak trading | Technical | High | Dual-provider partnership with automatic failover | Notify users via SMS; switch provider | CTO |
| Low-literacy users struggle to adopt platform | User Adoption | High | Usability testing with pilot traders; multilingual voice guidance | Deploy community ambassadors | Head of Product |
| Cyber-attack breaches financial data | Security | High | AES-256 encryption, TLS 1.3, quarterly pen testing | Activate incident response; notify NITDA within regulatory window | CTO / DPO |
| Development exceeds ₦85M budget | Financial | High | Strict change control; monthly expenditure monitoring | Seek additional funding or defer to V2 | PM / CFO |
| Fraudulent transactions / account takeover | Fraud | High | KYC verification, fraud detection, PIN lockout | Freeze suspicious accounts; investigate | Fraud & Compliance Manager |
| Network instability in rural areas | Infrastructure | High | Optimize for low bandwidth; prioritize USSD | Allow retries; queue pending requests | Infrastructure Manager |
| Low market awareness reduces registrations | Marketing | Medium | Targeted campaigns via market associations | Referral incentives; expand outreach | Head of Marketing |

## Why this approach
Tying every test case to a specific requirement means "done" is defined by evidence, not opinion. Pairing every risk with both a mitigation (reduce likelihood) and a contingency (respond if it happens anyway) — with a named owner — turns the risk register into something a project can actually be managed against, not just a list of concerns.
