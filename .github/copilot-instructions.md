# NetApp Data Classification - Copilot Instructions

## Repository Overview

**Product:** NetApp Data Classification

**Repository Type:** NetApp documentation site (AsciiDoc-based)

**Target URL:** https://docs.netapp.com/data-services-data-classification/index.html

NetApp Data Classificaiton enables users to scan and classify data across your organization's hybrid multicloud. Data Classification utilizes AI-driven natural language processing (NLP) for contextual data analysis and categorization, giving you actionable insights into your data to address compliance requirements, detect security vulnerabilities, optimize costs, and accelerate migration.

**Intent**: This documentation repository provides comprehensive technical guidance for Data Classification, enabling data governance professionals and IT administrators to deploy, configure, and use the service to scan and classify data across hybrid multicloud environments. Documentation should clearly explain AI-driven scanning capabilities, compliance workflows, and data management features using AsciiDoc format while maintaining consistency with NetApp's documentation standards. All content must prioritize clarity for enterprise users addressing compliance requirements, security vulnerabilities, and storage optimization. When reviewing the documentation, there should be a focus on clarity of language and tangible benefit for using a feature. 

## Repository Structure

* The repository includes a root directory with .adoc files that contain content articles and .yml files that provide sidebar and homepage structure. It also includes necessary files (.gitignore and readme.md).
* The repository includes sub-directories including media for media files (.png and source files) and an _includes directory, which contains .adoc files with reusable text blocks. Other specific subdirectory information is captured below. 


### Key Configuration Files
- `project.yml`
- `_index.yml`

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
* All links in the page should be absolute.
* Use the `^` symbol after link text to indicate external links (opens in new tab).
* Feature descriptions should be concise (1-2 sentences) with a link to detailed documentation.

  <!-- this will be a problem for staging -->
#### Redirect directory

<!-- could this be org level or a separate agent -->

The redirect directory captures decomissioned content pages that redirect HTTP request to a designated page. There should only be two metadata tags on the page:
1. `permalink:` - the HTML endpoint of the page. This should be match the file name, file type excluded. 
2. `redirect:` - the page the HTML request should be directed to. This must include the repository name as expressed in the path and a working page in that exists. Redirects most often point to the same repository, though sometimes they point to other docs.netapp.com sites. 

This is a correctly formatting redirect page: 

```
---
permalink: concept-cloud-compliance.html
redirect: data-services-data-classification/concept-classification.html
---
```

## Product-Specific Context

### Key Concepts

- **Data governance through scanning and classification** - Data Classification is a service that scans corporate on-premises and cloud data sources to map and classify data, identify private information, and address three main areas: compliance risk reduction, security strengthening, and storage cost optimization.
- **Two-level scanning approach** - The product offers two distinct scan types: Mapping-only scans (fast, metadata-based overview) and Map & Classify scans (deep-level scanning that accesses file contents to identify personal and sensitive data). This allows users to balance speed versus depth of analysis.
- **Continuous, automated scanning architecture** - Deploys a dedicated instance that continuously scans data in round-robin fashion to detect incremental changes, creating an ongoing index of personal information, sensitive personal information, data categories, and file types across hybrid multicloud environments.

### Common Terminology

- **Mapping-only scan**
- **Map & Classify scan**
- **Saved searches**
- **DSAR**

### Typical User Workflows

- **Deployment:** Deployment is process by which customers configure a Console agent and launch Data Classification, connecting to data resource and configuring networking. Key workflows are captured in task-deploy-cloud-compliance.adoc, task-deploy-compliance-onprem.adoc,task-deploy-compliance-dark-site.adoc, and task-test-linux-system.adoc.
- **Configure scanning:** Customers must configure scanning on their connected resources. The scope of scanning tasks is captured in task-scanning-overview.adoc. 
- **Classify and manage data:** After configuring scannings, data administrators capture information about compliance risks and stale data in Data Classification, prompting deletion and proper management of data. All data tasks capture under the "Use Data Classification" heading in project.yml capture the scope of actions. 

### Target audience

Data Classification is for enterprise IT administrators and data governance professionals who manage corporate data across hybrid cloud and on-premises environments. The product is specifically designed for compliance officers and security teams who need to identify and protect personal and sensitive information to meet regulatory requirements like GDPR, HIPAA, CCPA, and PCI. Additionally, it targets storage administrators and financial decision-makers looking to optimize storage costs and total cost of ownership (TCO) by identifying duplicate, inactive, or non-business-related data. When reviewing the documentation, the audience should clearly understand a procedure and the use case--that is, how using this feature provides value to their organization. 
