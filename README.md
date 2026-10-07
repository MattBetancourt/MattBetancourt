# Matthew Betancourt

<p align="left">
  <a href="https://www.linkedin.com/in/matthew-betancourt-csm/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Salesforce%20SOQL-00A1E0?style=flat-square&logo=salesforce&logoColor=white" alt="Salesforce SOQL" />
  <img src="https://img.shields.io/badge/FastMCP-Model%20Context%20Protocol-8A2BE2?style=flat-square" alt="FastMCP" />
  <img src="https://img.shields.io/badge/Jest-133%20Unit%20Tests-C21325?style=flat-square&logo=jest&logoColor=white" alt="Jest" />
  <img src="https://img.shields.io/badge/Google%20Workspace%20APIs-4285F4?style=flat-square&logo=google&logoColor=white" alt="Google Workspace" />
</p>

### Implementation & Customer Success Specialist | Applied AI Workflows & Systems | Open-Source Contributor

Customer Success, Implementation, and Operations Specialist with 10+ years managing enterprise post-sales lifecycles, institutional client portfolios, and complex system integrations across SaaS, fintech, and IoT platforms.

At ButterflyMX (March 2025 - May 2026) my core role was Implementation Project Specialist: I owned implementation lifecycle health, on-site activation, and the CARR-to-Live-ARR billing gate across thousands of customer implementations. I am currently seeking Customer Success and Implementation roles where operational scale intersects with applied AI workflows. Alongside that core role I volunteered as the team's Credal.ai power user, building Salesforce-backed agent workflows that automated the billing audits and account triage I previously handled manually. That split runs through everything below: core delivery first, AI as operational leverage I earned the right to build.

Before ButterflyMX I spent over a decade leading customer onboarding, executive relationship management, and revenue retention across tier-one financial data and trading platforms (**Refinitiv**, **Fitch Solutions**, **Enfusion**).

---

## 💼 Enterprise Customer Success & Operations Track Record

Before and alongside my applied AI work, my career is grounded in high-volume enterprise customer delivery and account management:

- **ButterflyMX (PropTech & IoT Access Control, Implementation Project Specialist, March 2025 - May 2026 - core role):** Governed implementation lifecycle health, on-site activation milestones, and CARR-to-Live-ARR billing gates across an active pipeline of **5,162 customer implementations** and **8,214 live property records**. Maintained a 35+ daily intervention cadence across contractors and property managers. This was my core role; the AI systems below were volunteered on top of it.
- **Refinitiv / Thomson Reuters (Risk Intelligence & Compliance):** Managed a **$4.8M ARR ($400K MRR)** institutional portfolio across 30+ enterprise accounts and 2,000+ end users (World-Check KYC/AML, Sanctions, PEP screening), driving adoption and renewal outcomes through proactive usage-based risk analysis and QBRs, and supporting mission-critical U.S. government agency workflows.
- **Fitch Solutions (Credit Ratings & Macro Intelligence):** Customer Success Manager, Global Accounts supporting a **$42M institutional book of business** across tier-one banks and financial institutions, leading onboarding, usage-monitored outreach, and renewal strategy for fixed-income intelligence feeds.
- **Enfusion (Fintech / Investment Operations):** Provided technical and integration support for **15+ hedge funds and asset managers** on a cloud-native investment management platform, covering onboarding support, reconciliation-break triage, and third-party connectivity coordination.

---

## 🏛️ Applied AI Systems & Architecture Highlights (volunteered alongside core IPS role)

### 1. Two-Tier Semantic Translation Layer with Delegated Execution
Architected an enterprise multi-agent retrieval and intelligence engine separating nondeterministic business reasoning from deterministic, injection-safe execution:
- **Orchestration Tier:** Evaluates natural language business requests, handles user disambiguation, maps operational vocabulary to API field taxonomies, and enforces human-in-the-loop write approval gates.
- **Delegated Execution Tier:** A strictly read-only sub-agent compiling mapped requests into validated, injection-safe SOQL queries executed against live Salesforce REST APIs.
- **Scale:** Automated account triage, billing audits, and lifecycle risk across **5,162 active customer implementations** and **8,214 live property records**.

### 2. Empirical RAG Auditing & Metadata-Gated Retrieval
- Diagnosed an out-of-the-box **96% semantic search failure/warning rate** when using standard dense vector similarity on programmatic API field names and schemas.
- Replaced naive vector RAG with a structured, metadata-gated **Smart Filtering v3** retrieval architecture enforcing strict similarity scoring thresholds to eliminate LLM hallucinations.
- Validated against a mined production corpus of **17,086 SOQL queries** across **96 Salesforce objects** and **1,534 fields**.

### 3. Two-Pass Context Optimization (94% Payload Compression)
- Solved silent context-window truncation and data loss caused by massive unstructured email reply chains (5–20KB per record in CRM activity logs).
- Engineered a **Two-Pass Task Triage Algorithm**: Pass 1 scans lightweight subject lines and risk trigger words (`cancel`, `permit`, `TCO`, `refund`, `go-live`); Pass 2 selectively pulls deep conversational history only for high-signal records while filtering out internal notes.
- **Result:** Compressed per-project activity payloads by **94% (~165KB down to ~10KB)** prior to model ingestion.

### 4. Relational CRM Entity Modeling
- Uncovered and resolved a **95% data omission rate** in customer reference discovery caused by continuous building management turnover and polysemic CRM schemas.
- Engineered multi-source relational traversal logic across operating accounts, physical building entities, and corporate parent hierarchies.

---

## 🛠️ Open-Source Engineering

### [Credal Actions SDK](https://github.com/Credal-ai/actions-sdk) — Contributor
*Enterprise TypeScript framework for LLM tool calling, secure data connectors, and agentic workflows.*

- **[`salesforce/getCleanActivityRecords`](https://github.com/Credal-ai/actions-sdk/pull/559) ([PR #559](https://github.com/Credal-ai/actions-sdk/pull/559) — Open, under review)**
  - Built an end-to-end data normalization and security pipeline for AI agents to ingest Salesforce email communication histories.
  - Implemented AST-style (Abstract Syntax Tree) SOQL injection guards, regex-based HTML/quote-chain stripping, and deterministic thread deduplication.
  - Engineered a **133 Jest unit test suite** validating edge cases, malformed payloads, and injection defense.
- **[`readCommentsOnDoc`](https://github.com/Credal-ai/actions-sdk/pull/572) ([PR #572](https://github.com/Credal-ai/actions-sdk/pull/572) — Open, under review)**
  - Engineered Google Docs comment and anchor text extraction with deterministic $O(n)$ merging of Google Drive API metadata and raw OpenXML (OOXML) structures.
  - Implemented decompression stream security guards to protect against zip-bomb vulnerabilities.
  - Code lives in [my working fork](https://github.com/MattBetancourt/credal-doc-and-comments/blob/main/src/actions/providers/google-oauth/readCommentsOnDoc.ts).
- **[`getSpreadsheetMetadata`](https://github.com/Credal-ai/actions-sdk/pull/534) ([PR #534](https://github.com/Credal-ai/actions-sdk/pull/534) — Merged)**
  - Designed metadata extraction using field masks to minimize memory footprints and reduce API token overhead.
  - Built a fallback-driven XLSX download pipeline to bypass native Google Sheets API timeout limits on large workbooks.

### [Open Code Review (Alibaba)](https://github.com/alibaba/open-code-review) — Contributor
- **Batch 422 Fallback Handling ([PR #661](https://github.com/alibaba/open-code-review/pull/661) — Merged)**
  - Fixed GitHub API 422 review fallback handling in Alibaba's automated AI code review platform.
  - When batch review creation fails due to line validation mismatches, surviving comments are grouped into a single consolidated fallback review rather than degrading into $N$ separate comments.

### [DataPortals.org](https://github.com/okfn/dataportals.org) — Contributor
- Restored stale municipal endpoints and metadata for Boston and New York City open data portals within the global catalog ([PR #418](https://github.com/okfn/dataportals.org/pull/418) — Merged).

> **Note on private work:** the property-intelligence tooling behind my Socrata SODA / ArcGIS REST claims (municipal permits, ownership, violations, TCO research) currently lives in a private repository — sanitized architectures and case studies available on request.

---

## 📊 Scale & Career Impact Matrix

| Dimension | Scope & Business Outcome |
| :--- | :--- |
| **Enterprise Portfolio Management** | Managed a **$42M book of business** (Fitch Solutions) and a **$4.8M ARR portfolio** (Refinitiv). |
| **Implementation Operations** | Governed **5,162 active implementation records** across **8,214 completed properties** (ButterflyMX). |
| **Production Query Scale** | Mined and analyzed **17,086 production SOQL queries** across 96 Salesforce objects to ground AI schemas. |
| **Context Window Compression** | Compressed CRM activity payloads by **94% (~165KB to ~10KB)** via two-pass triage, eliminating context overflow. |
| **RAG Precision Engineering** | Diagnosed a **96% vector similarity failure baseline**; replaced with metadata-gated Smart Filtering v3. |
| **Data Relational Recovery** | Eliminated a **95% customer reference omission rate** caused by active property management turnover. |
| **Software Quality & Testing** | Built and tested open-source agent tooling backed by **133 Jest unit tests** and AST-style injection defense. |

---

## 📬 Connect

- **LinkedIn:** [linkedin.com/in/matthew-betancourt-csm](https://www.linkedin.com/in/matthew-betancourt-csm/)
- **Email:** [me@mattbetancourt.com](mailto:me@mattbetancourt.com)