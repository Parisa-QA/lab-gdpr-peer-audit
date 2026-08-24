# GDPR and EU AI Act Peer Audit — Previously On: Love Is Blind  

**Auditor:** Parisa Dehghani  
**Builder:** Louise Plessis  
**Review date:** 19 August 2026  
**Status:** Updated after written clarification responses  
**Evidence reviewed:** System brief, Project 3 repository, user interface, and Louise's answered clarification log

## Phase 1 — Read and annotate

I reviewed Louise's system brief independently before consulting her self-audit conclusions. I then checked material technical statements against the [Project 3 repository](https://github.com/lou-PL-dev/project3_autonomous_research_-and_report_generation_agent).

| System element | Annotation | Audit relevance |
|---|---|---|
| AI-powered recap shown directly to viewers | **Risk tier / obligation** | Entertainment use is outside Annex III, but direct AI interaction raises Article 50(1). |
| OpenAI generates recap text | **Obligation** | Synthetic text raises the provider marking requirement in Article 50(2). |
| Public web content and YouTube comments are processed | **GDPR / clarification** | Personal-data, lawful-basis, vendor, transfer, retention and rights questions arise. |
| Recaps discuss named contestants and relationships | **Parallel-law issue** | Accuracy, privacy, personality-rights and correction controls are relevant. |
| Output reaches viewers without human editorial review | **Control gap** | Hard-coded facts reduce some errors but do not replace review or correction processes. |
| Spoiler-check and retry loop | **Technical finding** | The code's failure behaviour must support the “spoiler-free, always” claim. |
| Louise may launch the prototype later | **Scope / role question** | Current development status and future provider/deployer roles must be separated. |

## Phase 2 — First-pass classification

| Question | Auditor's answer |
|---|---|
| Does the system fall under an Article 5 prohibited category? | **No.** No prohibited manipulation, social scoring, criminal-risk assessment, biometric practice or other Article 5 purpose is identified. |
| Does it operate in an Annex III area? | **No.** Consumer entertainment recaps are outside the eight Annex III areas. |
| If Annex III, does it significantly influence decisions or remain narrow/preparatory? | **Not applicable.** |
| Does it interact with users or generate content requiring Article 50 transparency? | **Yes for a future EU product.** It directly provides AI-generated recap text, engaging Articles 50(1), 50(2) and 50(5). |
| First-pass risk tier | **Limited risk / transparency.** |
| One-sentence legal justification | The intended entertainment use is neither prohibited nor high-risk, but a future EU-facing product would fall within Article 50's direct-interaction and synthetic-content transparency framework. |

Louise confirmed that the system is currently a **closed prototype** and is not offered to EU users. Article 2(8) excludes pre-market research, testing and development activities from the AI Act, provided they are not real-world testing; GDPR and other applicable Union law still apply to personal data processed during development. Before any EU launch, the classification and role allocation must be confirmed again. See [AI Act Article 2](https://ai-act-service-desk.ec.europa.eu/en/ai-act/article-2) and [Article 50](https://ai-act-service-desk.ec.europa.eu/en/ai-act/article-50).

## Phase 3 — Clarifying questions log

**Information requested from Louise on 19 August 2026; written answers received on 19 August 2026.** The returned questionnaire is retained separately as audit-trail evidence. Its evidence-link fields were blank, so Louise's responses are treated as client statements unless independently supported by the repository or further documentation.

| Question | Louise's answer — concise record | Effect on audit |
|---|---|---|
| Is this a closed prototype, or will it be offered to EU users, and by which entity? | It is currently closed. Louise may launch it later but has no present launch. | **Assumption updated; tier unchanged.** Current AI Act development exclusion is relevant; future EU launch remains conditional. |
| What Article 50 notice and machine-readable marking exist? | None. | **Findings 1 and 2 confirmed.** |
| Will it remain entertainment, and is there human editorial review? | Entertainment only; no human editorial review. Some facts are hard-coded. | **Finding 4 updated.** Public-interest publishing is not the current purpose; hard-coded facts are a partial control only. |
| Which personal data enters the pipeline, and is it filtered? | Comment text, public web text, contestant information and user requests are processed. Usernames are unnecessary, but no systematic filter removes identifiers or sensitive claims from free text. | **Finding 3 strengthened.** Data minimisation and special-category screening remain unresolved. |
| What vendor safeguards, retention, deletion and data-subject-rights processes exist? | OpenAI receives task context; Pinecone stores indexed material; Tavily and YouTube receive search/API requests. Legitimate interests is proposed, but the LIA, regions, DPAs and transfer safeguards are not evidenced. Indexed material can remain until manual deletion, and no access, correction, objection or erasure workflow exists. | **Finding 3 materially strengthened.** Vendor compliance remains “cannot determine,” and a clear production governance gap is confirmed. |

## Phase 4 — Audit report

### 1. System summary

Previously On generates a Love Is Blind recap up to a viewer-selected episode. It searches public sources, processes YouTube comments, uses Pinecone retrieval and OpenAI generation, and runs an automated spoiler check. The output discusses identifiable contestants and reaches the viewer without human editorial review. Louise confirms that it is presently a closed prototype.

### 2. Risk classification

The future-deployment tier is **limited risk / transparency**. The entertainment use is neither prohibited nor listed in Annex III. For a future EU product, Articles 50(1), 50(2) and 50(5) address direct interaction, machine-readable marking of synthetic text, and clear accessible notice at first interaction or exposure. Article 50(4)'s public-interest text rule is not the main basis because Louise confirms an entertainment-only purpose. Current closed development may fall within Article 2(8), but that does not remove GDPR duties.

### 3. Role map

| Role | Entity | Key obligations or controls |
|---|---|---|
| Future AI-system provider | Louise or the entity launching the product | Article 50 design, intended-purpose documentation, AI literacy and product-level compliance. |
| Future deployer | Consumer-service operator, potentially the same entity | Intended-purpose operation, user communication, privacy and content governance. |
| GDPR controller | Louise, a future operator, or another entity determining purpose and means — **to confirm** | Lawful basis, transparency, rights, retention, security and processor governance. |
| GPAI/model vendor | OpenAI | Upstream model obligations and contractual information; product duties remain with the system provider. |
| Data/infrastructure vendors | Pinecone, Tavily, YouTube/Google, TMDB and OMDb | Processor/controller analysis, DPAs, hosting, transfers, retention, licences and API terms. |

### 4. Compliance findings

#### Finding 1 — No direct-interaction AI disclosure  
**Severity:** Significant for EU launch  
**Description:** Louise confirms that no dedicated AI notice exists. Article 50(1) and 50(5) require clear, accessible disclosure by first interaction unless the AI nature is obvious. Current branding does not safely establish the exception.  
**Recommended action:** Before launch, add a notice before submission and beside each result: “This recap is generated by AI from public sources and may contain inaccuracies or spoilers.”  
**Escalation needed?** **Yes — EU AI Act counsel** to validate final placement and wording.

#### Finding 2 — No machine-readable synthetic-text marking  
**Severity:** Significant for EU launch  
**Description:** Louise confirms that no marking exists. Article 50(2) separately requires generated text to be marked in a machine-readable format and detectable as artificially generated, subject to its technical-feasibility and stated exceptions. A visible label alone is not the same control.  
**Recommended action:** Select and test a standards-aligned marking method and preserve it in copied or exported outputs, including PDFs.  
**Escalation needed?** **Yes — AI Act counsel and a technical specialist.**

#### Finding 3 — GDPR data lifecycle, vendors and data-subject rights  
**Severity:** Significant  
**Description:** The system processes public comment text, contestant information and source material that may contain personal or sensitive claims. Commenter identities are not needed, but no systematic filtering exists. Legitimate interests is proposed without a documented LIA. Actual vendor regions, DPAs and transfer safeguards remain unverified. Indexed data can remain until manually deleted, and there is no retention schedule, privacy contact, correction process or workflow for access, objection and erasure. Public availability does not itself remove GDPR obligations.  
**Recommended action:** Before public deployment, complete a field-level data inventory and DPIA screening; document the lawful basis and LIA; filter unnecessary identifiers and special-category material; verify vendor roles, DPAs, regions and Chapter V safeguards; set retention/deletion rules; publish a privacy notice; and implement data-subject-request handling.  
**Escalation needed?** **Yes — DPO/privacy counsel.**

#### Finding 4 — Accuracy, provenance and correction for claims about people  
**Severity:** Significant  
**Description:** Hard-coded facts, RAG and source links are useful controls, but Louise confirms there is no human editorial review. No user or contestant correction route is visible, and the spoiler check does not verify factual accuracy. Incorrect claims about identifiable people create privacy, personality-rights, defamation and consumer risks.  
**Recommended action:** Distinguish sourced fact from fan reaction and AI synthesis; attach provenance to material claims; add reporting and correction mechanisms; and define when human review is required.  
**Escalation needed?** **Yes — media/privacy counsel** for the production policy.

#### Finding 5 — Spoiler safeguard fails open  
**Severity:** Significant  
**Description:** Repository inspection shows that invalid spoiler-check JSON defaults to `passed=True`, while exhausted retries return the draft. This conflicts with “spoiler-free, always.” Louise's written answers do not change this code-based finding.  
**Recommended action:** Fail closed on inconclusive checks, qualify the absolute UI claim, log safeguard failures and test adversarial future-episode leakage.  
**Escalation needed?** **No** for the engineering change; seek consumer-law review before making an absolute production claim.

### 5. Overall recommendation

**Proceed with conditions.** Closed-prototype development may continue. A public EU launch should not proceed until Article 50 disclosure and marking are implemented, the GDPR data and vendor lifecycle is documented, retention/deletion and data-subject-rights controls exist, claims about people can be corrected, and the spoiler safeguard fails safely. Louise's answers confirm rather than remove the material gaps.

### 6. What this report is not

This report is not a legal opinion, conformity assessment or certification. It is a first-pass educational review based on the system brief, repository and written responses available on 19 August 2026. Conclusions must be verified with qualified legal counsel before placement on the EU market or putting the system into service.

## Phase 5 — Debrief record

### Auditor presentation and builder response

- Written builder responses received: **19 August 2026**
- New information: current closed-prototype status; no Article 50 controls; entertainment-only purpose; hard-coded facts; proposed legitimate-interests basis; no documented retention or rights workflow.
- Evidence status: responses retained in the answered questionnaire, but no supporting links were supplied.

### Classification comparison

- Auditor's tier: **Limited risk / transparency for a future EU deployment**
- Builder's self-audit tier: **Limited risk / transparency**
- Result: **Agreement.** The answers clarify present development scope but do not change the future-deployment tier.

### Gap-list comparison

- Identified by both: missing AI disclosure, personal-data minimisation, vendor/data-flow documentation, provenance and production governance.
- Strengthened by Louise's answers: no retention schedule, deletion mechanism or data-subject-rights workflow; legitimate interests remains only provisional.
- Identified particularly by the external audit: separate Article 50(2) marking and the spoiler check's fail-open implementation.
- Mitigation added by Louise: some facts are hard-coded, reducing but not eliminating accuracy risk.
- Unresolved: actual vendor regions, DPAs, transfer safeguards and source/platform-rights evidence.

### Required joint closing note

**Draft for Parisa and Louise to confirm together:**

> The debrief showed that the builder had deeper knowledge of the data flows and intended purpose, while the external review identified control failures and legal distinctions that were easier to miss from inside the project. Combining both perspectives produced a more complete audit and showed why written evidence is needed to turn assumptions into defensible conclusions.

### Post-debrief audit update

- Classification changed: **No**
- Findings changed: **Yes — Findings 3 and 4 were expanded using Louise's responses; Findings 1 and 2 were confirmed.**
- Overall recommendation changed: **No — Proceed with conditions remains appropriate for any future EU launch.**
- Final action: Parisa and Louise must approve or amend the joint closing note before submission.

## Sources

- [Regulation (EU) 2024/1689 — AI Act Article 2](https://ai-act-service-desk.ec.europa.eu/en/ai-act/article-2)
- [Regulation (EU) 2024/1689 — AI Act Article 50](https://ai-act-service-desk.ec.europa.eu/en/ai-act/article-50)
- [Regulation (EU) 2016/679 — GDPR](https://eur-lex.europa.eu/eli/reg/2016/679/oj)
- [Project 3 repository](https://github.com/lou-PL-dev/project3_autonomous_research_-and_report_generation_agent)
