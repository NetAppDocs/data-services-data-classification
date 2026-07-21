## Copilot instructions for NetApp Data Classification documentation

### Repository overview
**Product:** NetApp Data Classification

NetApp Data Classification is a data governance service in the NetApp Console, the centralized management interface for NetApp data services, that scans enterprise data sources to map and classify data. It uses AI and NLP-based analysis to identify personal and sensitive data for compliance, security, and data lifecycle decisions. Data Classification can be deployed on-premises, in the cloud, or in a dark site. 

### Repository structure
- `./` – Primary documentation set; root `.adoc` files capture task/concept/reference page; `project.yml` and `_index.yml` define site navigation and landing content.
- `_include/` – Reusable include snippets for shared prerequisites, limits, and repeated procedural text.
- `_whatsnew/` – Date-based release-note source files used by `whats-new.adoc`.
- `media/` – Product diagrams and UI screenshots referenced by documentation pages.
- `redirect/` – Redirect-only legacy pages that preserve retired URLs and endpoints.
- `.github/` – Repository-scoped Copilot instructions and automation metadata.

### Product-specific context
**Architecture and components:**
- *NetApp Console* - the management interface where users deploy and operate Data Classification.
- *Console agent* - a software component you install in your network to connect your storage infrastructure to the NetApp Console; it's required for Data Classification deployment. 
- The **Data Classification instance** connects to data sources over standard protocols (such as NFS, CIFS, and database connections), scans content, and indexes findings in an Elasticsearch cluster deployed on the same Data Classification server set. One Data Classification instance is deployed per Console agent.

**Key concepts:**
- *Map-only scans* collect high-level metadata and usage insights without reading file contents.
- *Full scans* include map-level metadata plus in-file classification for personal/sensitive data and entity extraction; in legacy references this appears as *map & classify* scans.

**Naming conventions and terminology:**
- *DSAR* - *Data Subject Access Request* and is used for subject-based personal-data retrieval workflows.
- *Saved queries* - user-defined query filters for recurring investigations and policy-driven detection.

### Typical user workflows

- **Deployment:** Deployment is the process by which customers configure a Console agent and launch Data Classification, connecting to data resource and configuring networking. Key workflows are captured in task-deploy-cloud-compliance.adoc, task-deploy-compliance-onprem.adoc,task-deploy-compliance-dark-site.adoc, and task-test-linux-system.adoc.
- **Scanning configuration:** Customers must configure scanning on their connected resources. Scanning tasks are captured in the `task-scanning-overview.adoc` file. 
- **Classify and manage data:** After configuring scans, data administrators capture information about compliance risks and stale data in Data Classification, prompting deletion and proper management of data. All data tasks under the "Use Data Classification" heading in project.yml pertain to these workflows. 
