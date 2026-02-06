# NetApp Data Classification - Copilot Instructions

## Repository Overview

**Product:** NetApp Data Classification

**Repository Type:** NetApp documentation site (AsciiDoc-based)

**Target URL:** https://docs.netapp.com/data-services-data-classification/index.html

NetApp Data Classificaiton enables you to scan and classify data across your organization's hybrid multicloud. Data Classification utilizes AI-driven natural language processing (NLP) for contextual data analysis and categorization, giving you actionable insights into your data to address compliance requirements, detect security vulnerabilities, optimize costs, and accelerate migration.

## Repository Structure

### Key Configuration Files
- `project.yml`
- `_index.yml`

## Product-Specific Context

### Key Concepts

[2-5 core concepts unique to this product - analyze concept_ files]

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

Data Classification is for enterprise IT administrators and data governance professionals who manage corporate data across hybrid cloud and on-premises environments. The product is specifically designed for compliance officers and security teams who need to identify and protect personal and sensitive information to meet regulatory requirements like GDPR, HIPAA, CCPA, and PCI. Additionally, it targets storage administrators and financial decision-makers looking to optimize storage costs and total cost of ownership (TCO) by identifying duplicate, inactive, or non-business-related data.

## Common Writer Tasks

Examples:
- Document new features to manage data classification reporting
- Update release nnotes in whats-new.adoc
