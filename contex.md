# Nexora Cloud — Business Context

## 1. Company Overview

**Nexora Cloud** is a fictional enterprise B2B SaaS company headquartered in London, United Kingdom.

- **Employees:** Approximately 450
- **Primary markets:** UK, Europe, and North America
- **Infrastructure:** Primarily hosted on AWS
- **Business model:** Subscription-based enterprise SaaS
- **Security organization:** Dedicated Security/GRC function, supported by engineering, operations, privacy, and legal teams
- **Security maturity:** Moderately mature, with established security policies and assurance activities, including SOC 2 and ISO 27001

Nexora Cloud provides a multi-tenant platform for document processing and workflow automation. Customers may process confidential business documents and personal data through the platform.

## 2. Products and Services

Nexora Cloud provides the following capabilities:

- **Document processing:** Ingesting and processing business documents.
- **Workflow automation:** Automating document-related business processes.
- **Document storage and retrieval:** Storing and retrieving documents and associated information.
- **APIs and integrations:** Connecting the platform with customers' internal systems.
- **AI-assisted document capabilities:** Using AI for functions such as document classification and summarization.

The company's use of AI in its customer-facing product is separate from its internal security questionnaire process.

## 3. Customer Profiles

Nexora Cloud serves enterprise customers across several industries. The following fictional customers represent different security assessment requirements.

| Customer | Industry | Typical security concerns |
|---|---|---|
| Northstar Bank | Financial services | Regulatory obligations, access controls, encryption, incident response, resilience |
| MedAxis Health | Healthcare | Personal and sensitive data, privacy, access restrictions, retention and deletion |
| UrbanCart Group | Retail | Customer data protection, availability, integrations, third-party risk |
| Vertex Systems | Enterprise technology | Secure development, infrastructure security, vulnerability management, supply-chain security |

Customers may send standard security questionnaires, customized questionnaires, requests for supporting evidence, or combinations of these.

## 4. Internal Teams and Responsibilities

| Team | Main responsibilities |
|---|---|
| Security/GRC | Security governance, risk management, questionnaire coordination, control oversight, and response review |
| Cloud Infrastructure | AWS infrastructure, cloud configuration, network security, and infrastructure controls |
| Application Engineering | Application architecture, secure development, code security, and tenant isolation |
| Security Operations | Security monitoring, vulnerability management, threat detection, and incident response |
| Privacy/Legal | Privacy obligations, contractual commitments, regulatory interpretation, and legal review |
| IT/IAM | Employee identity, authentication, access management, and access reviews |
| SRE/Operations | Service reliability, backups, availability, disaster recovery, and operational resilience |
| Vendor Management | Third-party relationships, supplier information, and vendor risk coordination |
| Sales/Customer Success | Customer communication, questionnaire intake, deadlines, and delivery coordination |

The Security/GRC team coordinates questionnaire completion, but individual technical, privacy, legal, and operational questions may require input from their respective subject-matter experts.

## 5. Existing Tools and Platforms

Nexora Cloud uses a combination of internal systems and business platforms.

| Tool or platform | Primary purpose |
|---|---|
| AWS | Cloud infrastructure and hosting |
| AWS IAM | AWS identity and access management |
| Microsoft Entra ID | Workforce identity and access management |
| Jira | Work tracking, tickets, and internal task coordination |
| Confluence | Internal documentation and knowledge sharing |
| SharePoint | Document storage and collaboration |
| Google Workspace | Email and productivity |
| GitHub | Source code and software development collaboration |
| SIEM platform | Security event collection, monitoring, and investigation |
| Vulnerability management platform | Tracking vulnerabilities and remediation |
| GRC/TPRM platform | Tracking risk assessments, third-party assessments, and questionnaire progress |
| Vendor trust center | Sharing approved security information with customers |

The specific SIEM, vulnerability management, and GRC/TPRM products have not been defined.

**Questionnaire tooling assumption:** Nexora Cloud uses its existing GRC/TPRM platform to track assessments, but does not any dedicated AI-powered security questionnaire automation platform.

## 6. Security Questionnaire Process

Nexora Cloud receives security questionnaires from enterprise customers as part of their vendor risk and third-party risk management processes.

### 6.1 Typical workflow

1. **Intake:** Security/GRC or the relevant customer-facing team receives the questionnaire and records the assessment.
2. **Scoping:** Security/GRC reviews the questionnaire, identifies the relevant services and scope, and notes the deadline.
3. **Question assignment:** A human coordinator reviews the questions and manually assigns them to the appropriate internal teams or subject-matter experts.
4. **Information gathering:** Assigned teams review internal documentation, technical information, existing control descriptions, and available evidence.
5. **Answer preparation:** Security/GRC and subject-matter experts prepare responses based on their responsibilities and available information.
6. **Evidence collection:** Relevant teams locate supporting documents, reports, configurations, or other evidence where required.
7. **Review and approval:** Security/GRC reviews the responses for accuracy, consistency, completeness, and appropriate disclosure. Relevant specialists may be asked to clarify or verify answers.
8. **Customer delivery:** The completed questionnaire and approved evidence are provided to the customer.
9. **Retention:** The assessment and its responses are retained in the appropriate internal systems.

### 6.2 How questions are distributed

Question assignment is **human-led, not AI-driven**.

A Security/GRC coordinator reviews the questions and assigns them to the relevant teams. The existing GRC/TPRM platform, Jira, email, or other internal collaboration tools may be used to track and communicate assignments.

For example:

- Questions about encryption and AWS configuration go to Cloud Infrastructure.
- Questions about secure coding and application testing go to Application Engineering or the relevant security specialist.
- Questions about incident response go to Security Operations.
- Questions about personal data processing go to Privacy/Legal.
- Questions about employee MFA and access reviews go to IT/IAM.
- Questions about backups and disaster recovery go to SRE/Operations.

Security/GRC remains responsible for coordinating the assessment and reviewing and consolidating the final responses. The team does not necessarily have the specialist knowledge or direct evidence required to answer every question independently.

### 6.3 Current use of AI

Nexora Cloud **does not currently use AI to answer security questionnaires**.

It also does not use dedicated AI-powered questionnaire automation platform for this process.

Answers are prepared by humans using internal documentation, subject-matter expertise, and available previous responses. Human reviewers validate the answers before submission.

This assumption concerns the internal security questionnaire process only. It does not mean that Nexora Cloud avoids AI in its customer-facing product.

Even if it did, it will not be better because our specific project will be better than each and every tool on the web due to highly customization with negligible cost and with negligible security threat with ease and with a ton of time saved and no compromise on quality as well.

### 6.4 Common challenges

The questionnaire process can involve several recurring difficulties:

- Different customers use different questionnaire formats and terminology.
- Standard questionnaires may contain additional customer-specific questions.
- Relevant documentation and evidence are distributed across multiple internal systems.
- Previous answers may need to be verified before reuse.
- Policy statements do not necessarily demonstrate that a control operates effectively.
- Some questions require input from multiple teams.
- Sensitive internal information must be protected when sharing evidence externally.
- Answers may become outdated when systems, processes, or controls change.
- AI-related questions may require clarification about data handling, model usage, and customer information.

## 7. Standards, Frameworks, and Assessment Types

Nexora Cloud may receive questionnaires based on recognized industry frameworks or customer-specific requirements.

| Framework or assessment | Description |
|---|---|
| [CSA Cloud Controls Matrix (CCM)](https://cloudsecurityalliance.org/artifacts/cloud-controls-matrix-v4-1) | Cloud security control framework used to assess cloud providers |
| [CSA Consensus Assessments Initiative Questionnaire (CAIQ)](https://cloudsecurityalliance.org/artifacts/cloud-controls-matrix-v4-1) | Standardized questions aligned with cloud security controls |
| [Shared Assessments SIG](https://sharedassessments.org/) | Standardized third-party risk assessment questionnaires |
| [Vendor Security Alliance (VSA)](https://www.vendorsecurityalliance.org/) | Security assessment resources and questionnaires |
| [HECVAT](https://www.educause.edu/higher-education-community-vendor-assessment-toolkit) | Vendor security assessment toolkit designed for higher education |
| Customer-specific questionnaires | Questionnaires created or customized by individual customers |

These items are related but not interchangeable:

- **Questionnaire:** A set of questions used to assess a provider's security and risk posture.
- **Control framework:** A structured set of security control objectives or requirements.
- **Certification:** An independent certification against a defined standard, such as ISO/IEC 27001.
- **Audit report:** A report describing an independent examination, such as a SOC 2 report.
- **Evidence:** Documentation or other information used to substantiate a response or demonstrate a control.
- **Trust center:** A location where approved security documentation and assurance information can be shared with customers.

A completed questionnaire is not itself a certification or independent audit report.

## 8. Core Security Domains

Security questionnaires may cover the following domains.

| Domain | Example topics |
|---|---|
| Governance and risk management | Security policies, risk assessments, accountability |
| Identity and access management | MFA, least privilege, access reviews, privileged access |
| Data protection and encryption | Encryption in transit and at rest, key management |
| Network and infrastructure security | Network segmentation, cloud configuration, infrastructure hardening |
| Application security | Secure development lifecycle, code reviews, application testing |
| Vulnerability management | Scanning, remediation, patching, penetration testing |
| Logging and monitoring | Audit logs, alerting, monitoring coverage |
| Incident response | Response procedures, escalation, notification |
| Business continuity and disaster recovery | Backups, recovery objectives, resilience testing |
| Data retention and deletion | Retention schedules, deletion procedures, disposal |
| Third-party and supply-chain security | Supplier reviews, dependency risks, vendor oversight |
| Privacy and compliance | Personal data processing, regulatory requirements, privacy obligations |
| Personnel security | Employee screening, security training, termination procedures |
| Tenant isolation | Separation of customer data and access boundaries |
| AI security and data handling | AI data use, model-provider relationships, data retention, AI-related risks |

Not every questionnaire covers every domain. The level of detail depends on the customer, the service being assessed, and the customer's risk requirements.

## 9. Internal Versus External Security Information

Nexora Cloud maintains information that can support internal security operations and external customer assessments.

**Examples of information that may be shared externally, subject to approval:**

- Approved security policies or policy summaries
- SOC 2 reports and ISO 27001 certification information
- Security architecture descriptions
- Business continuity and disaster recovery summaries
- Incident response policy summaries
- Approved descriptions of security controls

**Examples of information that may require restricted access or careful review:**

- Detailed infrastructure diagrams
- Internal vulnerability reports
- Raw security logs
- Penetration testing reports containing exploitable details
- Detailed configurations and access-control information
- Internal incident records
- Secrets, credentials, and sensitive operational information

The fact that a document exists does not necessarily mean it is appropriate to share with a customer. Disclosure must follow the company's security, confidentiality, and approval requirements.

Documentation also does not automatically prove that a control operates effectively. The nature and quality of supporting evidence matter.

## 10. Summary of the Business Context

Nexora Cloud is an established enterprise SaaS provider with a dedicated Security/GRC function, multiple specialist teams, recognized security assurance activities, and a mixture of internal systems.

Its customer security questionnaire process is **human-led**:

- Security/GRC coordinates each assessment.
- Humans manually assign questions to the relevant internal teams.
- Subject-matter experts prepare answers and provide supporting evidence.
- Security/GRC reviews and consolidates the final responses.
- The existing GRC/TPRM platform tracks assessments and progress.
- The company does not currently use Loopio or another dedicated AI-powered questionnaire automation platform to answer questionnaires.

These assumptions describe the company's current business process without presupposing any future changes to its tools or workflow.