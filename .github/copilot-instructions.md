# Copilot Instructions for NetApp Data Classification documentation

## Repository Overview

**Product:** NetApp Data Classification

NetApp Data Classificaiton is a governance service to audit security and compliance of your data. Data Classification utilizes natural language processing for contextual data analysis and categorization, giving you actionable insights into your data to address compliance requirements, detect security vulnerabilities, optimize costs, and accelerate migration.

## Repository Structure

* Root directory - .adoc and .yml that contain the documentation, sidebar, and landing page structure of the repository.
* `_include` - Reusable text blocks referenced in .adoc files in the root. 
* `media` - Images and diagrams that are elements of articles in the root directory. This includes .png and source files. 
* `redirect` - .adoc files for retired pages and endpoints that redirect HTTPS requests to the appropriate endpoint. This is a correctly formatted redirect page: 

```
---
permalink: concept-cloud-compliance.html
redirect: data-services-data-classification/concept-classification.html
---
```

### File naming

All .adoc files in the root directory should be prepended with concept-, faq-, reference-, or task-. These prefixes denote the type of information in the file. There are three files that are exceptions:

1. `api-` - This is information about the API
2. `legal-notices`: This is required legal information
3. `whats-new`: This contains release notes. For more information, see [What's new](#whats-new).

### What's New

The `whats-new.adoc` directory includes release notes for the Data Classification service. 

* All dates must follow the format: DD MONTH YYYY (with leading zeros).
  * ✅ Correct: 01 February 2026
  * ❌ Incorrect: February 1, 2026 or 1 February 2026
* All substantive content for each dated entry must be housed in an individual includes file located in the `whatsnew` directory. 

#### _whatsnew directory

* All files in the whats new directory should be named year-month-day.adoc, for example `2026-02-01.adoc`.
* All files in the `whatsnew` directory should be .adoc files. The file must begin with a level three heading (`===`) that indicates the version of Data Classification in the release. 
* All subsequent titles should be list headers. 
  * ✅ Correct: `.New feature title`
  * ❌ Incorrect: `==== New feature`
* When deploying to production (i.e., when pushing to the public remote), all links in the page should be absolute.
  <!-- phrased this way to mitigate problems when deploying for staging -->
* Use the `^` symbol after link text to indicate external links (opens in new tab).
* Feature descriptions should be concise: 1-3 sentences describing the change and the added value to the user. In most cases, they should include a link that directs users to more information. 
* The `release_notes_repo: console-relnotes` setting in the project.yml file enables release notes to be automatically collated in a release notes repository for the entire NetApp Console: https://docs.netapp.com/us-en/console-relnotes/. 

## Product-specific context

- **Data governance through scanning and classification** - Data Classification is a service that scans corporate on-premises and cloud data sources to map and classify data, identify private information, and address three main areas: compliance risk reduction, security strengthening, and storage cost optimization.
- **Two-level scanning approach** - The product offers two distinct scan types: Mapping-only scans (fast, metadata-based overview) and Map & Classify scans (deep-level scanning that accesses file contents to identify personal and sensitive data). This allows users to balance speed versus depth of analysis.
- **Continuous, automated scanning architecture** - Deploys a dedicated instance that continuously scans data in round-robin fashion to detect incremental changes, creating an ongoing index of personal information, sensitive personal information, data categories, and file types across hybrid multicloud environments.

### Common Terminology

- **Mapping-only scan** - Data Classification must scan data to provide insights into it. A mapping-only scan is a high-level overview of data that provides broad insights and reads metadata. It does not read the files. 
- **Map & Classify scan** - Map & Classify scans provide the same benefits of a mapping-only scan with added insights such as names within file or specific pieces of PII. 
- **Saved queries** - Custom queries created by the user to identify data or a data pattern specific to their organization. 
- **DSAR** - A Data Subject Access request. This is a request made by an individual to access their personal data. 

## Typical User Workflows

- **Deployment:** Deployment is process by which customers configure a Console agent and launch Data Classification, connecting to data resource and configuring networking. Key workflows are captured in task-deploy-cloud-compliance.adoc, task-deploy-compliance-onprem.adoc,task-deploy-compliance-dark-site.adoc, and task-test-linux-system.adoc.
- **Scanning configuration:** Customers must configure scanning on their connected resources. Scanning tasks are captured in the `task-scanning-overview.adoc` file. 
- **Classify and manage data:** After configuring scannings, data administrators capture information about compliance risks and stale data in Data Classification, prompting deletion and proper management of data. All data tasks under the "Use Data Classification" heading in project.yml pertain to these workflows. 