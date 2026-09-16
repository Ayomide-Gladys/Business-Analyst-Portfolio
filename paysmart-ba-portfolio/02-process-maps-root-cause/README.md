# 02 — Process Maps & Root Cause Analysis

**Technique:** Current/future state process mapping, 5 Whys root cause analysis, and TIMWOODS (Lean) waste identification

## Objective
Before proposing a solution, diagnose *why* the current cash-based process fails — then prove, quantitatively, how much of that problem a redesigned process actually removes.

## 1. Current State (AS-IS) Process
The existing transaction flow was mapped step by step: verbal price negotiation → cash handed over → manual change-making → no receipt issued → no record kept → manual end-of-day reconciliation. Every step in that chain was a manual, error-prone, and time-consuming touchpoint with no digital record at the end of it.

🗺️ *Screenshot of the AS-IS/TO-BE process maps from Miro:*
`![Process Map](process-map.png)`

**Live, interactive board:** [View on Miro](https://miro.com/app/board/uXjVH7Mf2u0=/?share_link_id=328916907233) *(replace with your own board link if it changes)*

## 2. Root Cause Analysis (5 Whys)
Three core problems were each traced back to a root cause by asking "why" repeatedly, rather than treating the first visible symptom as the real issue:

**Problem 1: Traders lose ~45 minutes/day managing cash change**
> Why do they lose 45 minutes? → They're always counting/giving change.
> Why is change a problem? → Customers pay with large notes; sellers don't hold small notes.
> Why don't they use other payment options? → POS machines charge high fees; transfers are slow or fail.
> **Root cause:** No fast, low-cost, trusted digital payment option built for small traders.
> **PaySmart response:** Let customers pay exact amounts via USSD/app — no change needed, funds reflect instantly.

**Problem 2: Traders can't access business loans despite years of consistent trading**
> Why can't they get loans? → No proof of income.
> Why no proof of income? → Sales are cash and unrecorded.
> **Root cause:** No system that automatically converts sales history into a credit score.
> **PaySmart response:** Free digital wallet + transaction history; after 3 months of consistent inflow, sellers qualify for "Business Boost Loans" using sales data as collateral.

**Problem 3: Rural traders cannot accept digital payment at all**
> Why not? → No POS machines or bank apps; setup costs and poor network.
> **Root cause:** Existing fintech apps were built for cities, not rural traders on basic phones.
> **PaySmart response:** USSD (\*111#) works on any phone with no internet required.

## 3. Future State (TO-BE) Process
The redesigned flow: trader dials USSD or opens the app → enters recipient ID and amount → confirms with PIN → payment settles instantly → SMS confirmation sent to both parties → transaction automatically recorded in the Seller Dashboard. No manual reconciliation step remains.

**Live, interactive board:** [View TO-BE map on Miro](https://miro.com/app/board/uXjVH7v-VFE=/?share_link_id=171962964672)

## 4. TIMWOODS Waste Analysis
Each of the 7 Lean wastes was mapped against the redesigned process to confirm the new flow wasn't just faster, but structurally leaner:

| Waste | Future State Outcome |
|---|---|
| Transport | Eliminated — electronic fund transfer replaces physical cash movement |
| Inventory | Eliminated — no cash holdings required |
| Motion | Eliminated — no searching for change |
| Waiting | Greatly reduced via instant digital confirmation |
| Overprocessing | Eliminated via automated validation and reconciliation |
| Defects | Reduced via transaction IDs, SMS notifications, and automated validation |

## 5. Process Improvement Summary

| Metric | AS-IS | TO-BE | Improvement |
|---|---|---|---|
| Time per transaction | ~7 minutes | ~1 minute | ~86% reduction |
| Manual steps in payment process | 8 | 6 | 25% reduction |
| Cash theft risk | High | Eliminated | 100% reduction |
| Transaction record created automatically | No | Yes | Full traceability |
| Daily reconciliation time | 10–15 minutes | <1 minute | ~90% reduction |

## Why this approach
5 Whys prevents solving the wrong problem — the real blocker wasn't trader resistance to digital tools, it was the absence of a tool designed for their actual constraints (no smartphone, no reliable network, no float of small notes). Quantifying the before/after with TIMWOODS and the summary table turns "this should be better" into a measurable, defensible business case.
