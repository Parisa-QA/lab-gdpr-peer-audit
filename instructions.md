# Audit your teammate's project — GDPR lens

> **How you'll submit this lab**
>
> This repo is your lab. Fork it, do the work described below in your fork, then open a pull
> request back into this repository. An AI reviewer will check your PR against `rubric.md` and
> leave feedback directly on the PR. See `README.md` for the full workflow.

In this lab, you audit a teammate's SilverTrust project for GDPR compliance — and they audit yours. You have not built their system. They have not built yours. That distance is what makes the exercise valuable.

This lab pairs with the GDPR self-audit. Complete your own self-audit first, then exchange data processing briefs with your teammate and conduct independent reviews before the debrief.

## Lesson alignment

- **Learning objectives:** By the end, you can conduct an independent GDPR audit on a system you did not build, produce a structured audit report with findings and recommendations, and use a structured debrief to surface what independent review reveals that self-assessment misses.
- **Lesson setup requirements:** Completed GDPR self-audit (`02_lab_gdpr-self-audit.md`), review of `01_gdpr-fundamentals.md` — particularly controllers vs processors, lawful bases, purpose limitation, DPIA triggers, and international transfers.

---

## Submission hygiene

- **Filenames:** Use clear, descriptive names (avoid names such as `peer_review.md` or `gdpr_teammate.pdf`).
- **Scope:** Your **GitHub** repository must contain **only materials for this lab**—no unrelated projects, dumps, or personal files.
- **README:** Add a short file map. Include your teammate's name and which project you audited.

**GitHub only:** Submit the URL to a **GitHub repository** that contains everything for this lab. Do **not** submit a standalone Google Doc, Notion page, or cloud-only link.

---

## Kick-off

### What you exchange

Before you begin, you and your teammate exchange **data processing briefs only** — the document your teammate wrote in the Kick-off section of their self-audit. Not their findings, not their lawful basis assessments, not their memo.

You receive:
- Your teammate's data processing brief (the one-page description of what data their system processes, where it comes from, what it is used for, who processes it, and where)
- Any architecture or data flow diagrams produced during the course project (optional but useful)

You do not receive:
- Their lawful basis assessments
- Their DPIA trigger analysis
- Their compliance memo
- Their gap findings

Independent review only has value if it is genuinely independent. If you read their conclusions first, you are checking their reasoning — which is useful, but different from forming your own view.

### Ground rules

- Work independently until Phase 5. No discussion with your teammate before the debrief.
- If the brief is unclear, log your questions in writing and state what you are assuming in the absence of an answer. These questions become part of your audit trail.
- If the brief omits information you need to form a view, note the gap and state your provisional position.

---

## CFU checkpoints

### 1. Recognize

Read your teammate's data processing brief and identify: what categories of personal data are present, whether any special-category data is involved or inferable, and whether any data flows cross an EU border.

### 2. Probe

Write down the three most important clarifying questions you would ask this client before issuing any compliance opinion. State your provisional answer to each if you do not receive a response.

### 3. Map roles

Identify the controller, processor(s), and any third-party vendors in your teammate's system. Note which relationships require a Data Processing Agreement.

### 4. Find the gaps

Assess the system's most significant GDPR risks: lawful basis, purpose limitation, DPIA requirement, automated decision-making, and international transfer mechanism. Identify what appears to be in place, what appears to be missing, and what you cannot determine from the brief alone.

### 5. Debrief

Compare your audit findings with your teammate's self-audit. Where did the two audits agree? Where did they diverge? What did the external review surface that the self-audit missed?

---

## Core

### Phase 1: Read and annotate

Read your teammate's data processing brief once without taking notes. Then read it again and annotate:

- Mark every mention of personal data category and note whether special-category status applies or could be inferred
- Circle anything unclear or that you would need to confirm before forming a view
- Underline any data flow that crosses an EU border or involves a non-EU vendor
- Flag any purpose that looks potentially incompatible with the original collection purpose

These annotations become the evidence base for your report.

### Phase 2: Personal data and role map

Complete these two tables based only on what the brief tells you. Where the brief is silent, note the gap.

**Personal data summary:**

| Data category | Source | Purpose(s) | Crosses EU border? | Special category? |
|---|---|---|---|---|
| | | | | |

**Role map:**

| Entity | Role | Processing activity | DPA needed? |
|---|---|---|---|
| Client | | | |
| Builder (your teammate / their team) | | | |
| API / vendor (if any) | | | |

For any international transfer you identify, note what transfer mechanism would be needed and whether the brief provides any evidence it is in place.

### Phase 3: Clarifying questions log

Write down three to five questions you would need answered before finalising your audit. For each:

- What you need to know
- Why it matters for the compliance assessment (which specific GDPR obligation it affects)
- What you are provisionally assuming in the absence of an answer

This log is part of your deliverable.

### Phase 4: Audit report

Write a structured audit report of no more than two pages.

**Section 1: System summary**
Restate what the system does and what data it processes, in your own words. This confirms you understood the brief. (3–5 sentences)

**Section 2: Data and role map**
Brief summary of the personal data categories identified, the controller/processor split, and any international transfer issues.

**Section 3: Compliance findings**

Use this structure for each finding:

> **Finding [number] — [Obligation or principle]**
> **Severity:** Blocking / Significant / Minor
> **Description:** What the requirement is and what the brief suggests about whether it is met.
> **Recommended action:** What the team should do.
> **Escalation needed?** Yes / No — and if yes, to whom.

Severity guide:
- **Blocking** — processing cannot begin or must stop without resolving this (e.g., no lawful basis for a processing activity; DPA missing for a processor that already handles personal data; DPIA required but not conducted)
- **Significant** — processing can continue, but the risk is material and must be addressed (e.g., unclear purpose limitation; international transfer mechanism undocumented; automated decision-making without an Article 22 safeguard)
- **Minor** — good practice to address, does not block processing (e.g., retention periods undefined for low-risk data; privacy notice missing one required element)

**Section 4: Specific GDPR obligations checklist**

Mark each as **Appears met**, **Gap identified**, or **Cannot determine from brief**:

| Obligation | Assessment | Note |
|---|---|---|
| Lawful basis identified for each processing purpose | | |
| Purpose limitation respected (no incompatible reuse) | | |
| Data minimisation (only necessary data collected) | | |
| Controller/processor roles mapped and DPAs in place | | |
| International transfer mechanism documented | | |
| DPIA conducted if required | | |
| Article 22 safeguard in place if automated decisions affect people | | |
| Privacy notice covers AI processing | | |
| Data subject rights can be operationalised within deadlines | | |

**Section 5: Overall recommendation**

One of three positions, with a one-paragraph rationale:
- **Clear to proceed** — no blocking findings; minor issues noted for remediation
- **Proceed with conditions** — significant findings must be resolved before or shortly after go-live; specify conditions
- **Do not proceed** — one or more blocking findings; must be resolved before any personal data is processed

**Section 6: What this report is not**
Standard disclaimer: this report is not a legal opinion, not a DPIA, and not a certification of compliance. The client should obtain legal review before relying on this assessment.

### Phase 5: Debrief conversation

Run the debrief in this sequence:

1. **Auditor presents** — walk through your audit report without interruption. Your teammate listens.
2. **Builder responds** — your teammate has five minutes to provide context, clarify choices, or flag information not captured in the brief.
3. **Compare lawful basis selections** — each person reveals what lawful basis they chose for the primary processing purpose. If they differ, discuss which is stronger and why.
4. **Compare DPIA conclusions** — did both audits agree on whether a DPIA is required? If not, work through the EDPB criteria together until you reach agreement or identify the specific ambiguity.
5. **Compare gap lists** — what did the self-audit catch that the external audit missed? What did the external audit catch that the builder missed?
6. **Joint closing note** — together, write two to three sentences answering: *What does this debrief reveal about GDPR self-assessment specifically — what kinds of gaps are hardest to catch in your own work?*

The joint closing note is a required deliverable. Include it in your submission.

---

## Reinforce

If you finish the core tasks early:

- Review the clarifying questions your teammate logged about your own system. Which questions can you not answer from your current project documentation? What does that suggest about your documentation gaps?
- Identify one finding from your teammate's report that you, as the builder, initially disagreed with. After the debrief, do you still disagree? Write a one-paragraph reflection.

## Stretch

Take the most significant finding from your audit report — either a Blocking or Significant finding — and draft a concrete remediation plan:

- What specific artifact closes this gap? (A DPA, a DPIA section, a revised privacy notice clause, a documented LIA, a data retention schedule)
- Who would own it? (Controller, legal team, DPO, external counsel)
- What is a realistic timeline to produce it?
- What evidence would confirm to a regulator that the gap is closed?

Keep this to half a page. The goal is to move from "there is a problem" to "here is a plan" — which is what clients actually need.
