# Copilot Instructions for NetApp Data Classification documentation

## Repository overview

**Product:** NetApp Data Classification

NetApp Data Classificaiton is a governance service to audit security and compliance of your data. Data Classification utilizes natural language processing for contextual data analysis and categorization, giving you actionable insights into your data to address compliance requirements, detect security vulnerabilities, optimize costs, and accelerate migration.

## Repository structure

* Root directory - .adoc and .yml that contain the documentation, sidebar, and landing page structure of the repository.
* `_include` - Reusable text blocks referenced in .adoc files in the root. 
* `media` - Images and diagrams that are elements of articles in the root directory. This includes .png and source files. 
* `redirect` - .adoc files for retired pages and endpoints that redirect HTTPS requests to the appropriate endpoint. This is a correctly formatted redirect page: 

## Product-specific context

- **Map-only scan** - Data Classification must scan data to provide insights into it. A map-only scan is a high-level overview of data that provides broad insights and reads metadata. It does not read the files. 
- **Full scan** - Full scans provide the same benefits of a map-only scan with added insights such as names within file or specific pieces of PII. Full scans read file data, whereas mapping only scans do not. Full scans were previously known as "map & classify" scans. 
- **Saved queries** - Custom queries created by the user to identify data or a data pattern specific to their organization. 
- **DSAR** - A Data Subject Access request. This is a request made by an individual to access their personal data. 

## Typical user workflows

- **Deployment:** Deployment is process by which customers configure a Console agent and launch Data Classification, connecting to data resource and configuring networking. Key workflows are captured in task-deploy-cloud-compliance.adoc, task-deploy-compliance-onprem.adoc,task-deploy-compliance-dark-site.adoc, and task-test-linux-system.adoc.
- **Scanning configuration:** Customers must configure scanning on their connected resources. Scanning tasks are captured in the `task-scanning-overview.adoc` file. 
- **Classify and manage data:** After configuring scannings, data administrators capture information about compliance risks and stale data in Data Classification, prompting deletion and proper management of data. All data tasks under the "Use Data Classification" heading in project.yml pertain to these workflows. 