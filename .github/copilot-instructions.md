# NetApp Data Classification - Copilot Instructions

## Repository Overview

**Product:** [Extract from project.yml settings.name]

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

Example format:
- **Concept name:** One sentence explanation

### Common Terminology

[Product-specific terms - extract from file names and content]

Example format:
- **Term:** Definition or preferred usage

### Typical User Workflows

[3-5 common task patterns users follow - analyze task groupings in sidebar]

Example format:
- **Deployment:** Deployment is process by which customers configure a Console agent and launch Data Classification, connecting to data resource and configuring networking. Key workflows are captured in task-deploy-cloud-compliance.adoc, task-deploy-compliance-onprem.adoc,task-deploy-compliance-dark-site.adoc, and task-test-linux-system.adoc.
- **Configure scanning:** Customers must configure scanning on their connected resources. The scope of scanning tasks is captured in task-scanning-overview.adoc. 
- **Classify and manage data:** After configuring scannings, data administrators capture information about compliance risks and stale data in Data Classification, prompting deletion and proper management of data. All data tasks capture under the "Use Data Classification" heading in project.yml capture the scope of actions. 


### Target audience

Data Classification is for enterprise IT administrators and data governance professionals who manage corporate data across hybrid cloud and on-premises environments. The product is specifically designed for compliance officers and security teams who need to identify and protect personal and sensitive information to meet regulatory requirements like GDPR, HIPAA, CCPA, and PCI. Additionally, it targets storage administrators and financial decision-makers looking to optimize storage costs and total cost of ownership (TCO) by identifying duplicate, inactive, or non-business-related data.

## Documentation Conventions

[OPTIONAL - Only include if the repository has unique patterns beyond standard NetAppDocs conventions]

Examples of when to include this section:
- Non-standard file naming patterns (beyond task_/concept_/reference_)
- Heavy use of `_include/` files with specific reuse patterns
- Special metadata requirements
- Unusual sidebar organization patterns
- Product-specific validation rules

If none apply, remove this section.

## Common Writer Tasks

- 
Examples:
- Update version-specific information
- Document new features for [component]
- Create integration guides
- Update specific file types when product changes
