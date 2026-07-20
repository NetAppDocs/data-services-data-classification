## Copilot instructions for NetApp Data Classification documentation

### Repository overview
**Product:** NetApp Data Classification

NetApp Data Classification is a data governance service in the NetApp Console, the centralized management interface for NetApp data services, that scans enterprise data sources to map and classify data.
It uses AI and NLP-based analysis to identify personal and sensitive data for compliance, security, and data lifecycle decisions.

### Repository structure
- `./` – Primary documentation set; root `.adoc` task/concept/reference pages plus `project.yml` and `_index.yml` define site navigation and landing content.
- `_include/` – Reusable include snippets for shared prerequisites, limits, and repeated procedural text.
- `_whatsnew/` – Date-based release-note source files used by `whats-new.adoc`.
- `media/` – Product diagrams and UI screenshots referenced by documentation pages.
- `redirect/` – Redirect-only legacy pages that preserve retired URLs and endpoints.
- `.github/` – Repository-scoped Copilot instructions and automation metadata.

### Product-specific context
**Architecture and components:**
- *NetApp Console* is the management interface where users deploy and operate Data Classification.
- A *Console agent* deploys and manages the *Data Classification instance* in cloud or on-premises environments.
- The Data Classification instance connects to repositories over standard protocols (such as NFS, CIFS, and database connections), scans content, and indexes findings in an Elasticsearch cluster deployed on the same Data Classification server set.
- One Data Classification instance is deployed per Console agent, and scanning is continuous after initial indexing.

**Key concepts:**
- *Repositories* are scan targets—such as volumes, database schemas, and other user data sources—selected for analysis.
- *Map-only scans* collect high-level metadata and usage insights without reading file contents.
- *Full scans* include map-level metadata plus in-file classification for personal/sensitive data and entity extraction; in legacy references this appears as *map & classify* scans.
- Scans are enabled per volume or per database schema and continue in round-robin incremental cycles, repeatedly revisiting sources to detect changes.

**Naming conventions and terminology:**
- *DSAR* means *Data Subject Access Request* and is used for subject-based personal-data retrieval workflows.
- *Saved queries* are user-defined query filters for recurring investigations and policy-driven detection.
- *Sensitive personal data* is used for Sensitive Personally Identifiable Information (SPII)-style regulated data categories, distinct from broader *personal data* (PII).
- The term *private mode* refers to dark-site on-premises deployment without SaaS-layer connectivity.

### Typical user workflows
**Cloud deployment:** Create Console agent → validate networking/permissions prerequisites → deploy Data Classification instance from Console → select repositories to scan (see `task-deploy-cloud-compliance.adoc`, `task-deploy-overview.adoc`)

**On-premises deployment:** Verify Linux host readiness → run installation script (internet-connected or private mode) → complete instance setup → open configuration and choose repositories (see `task-deploy-compliance-onprem.adoc`, `task-deploy-compliance-dark-site.adoc`, `task-test-linux-system.adoc`)

**Data discovery and governance:** Enable map-only or full scans per repository → review governance/compliance dashboards and investigation views → run saved queries and reports (including DSAR-related reporting) → take remediation actions (copy/move/delete or scan-setting changes) (see `task-scanning-overview.adoc` and pages under *Use Data Classification* in `project.yml`)
