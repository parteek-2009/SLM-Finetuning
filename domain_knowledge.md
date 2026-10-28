# Security Questionnaires: A Domain Knowledge Guide

**Purpose of this document:** to give a reader with no background in cybersecurity or procurement a complete picture of what a *vendor security questionnaire* is, why it exists, who is involved, what it contains, what proof backs it up, and what tools companies use to handle it. It is written as background for a project in this space, so every term a later document might rely on is explained here.

**Scope:** domain knowledge only. It does not frame a specific project problem and does not compare individual tools in depth.

**A note on numbers:** question counts, time estimates, and percentages in this guide are reported figures or planning estimates. Where a number could not be verified from an official source, the text says so. Standards are revised regularly, so always check the current version before relying on a count.

---

## Table of contents

1. The big picture in one page
2. Core concepts and how they differ
3. The business context: where this appears in a sale
4. Who is involved
5. Standard questionnaires (CAIQ, SIG, VSA, HECVAT) and custom ones
6. The anatomy of a questionnaire: 15 recurring domains
7. Proof: the evidence buyers ask for
8. How a seller actually answers a questionnaire
9. Why "just publish it once" doesn't fully work
10. The tool landscape (categories and examples)
11. Where AI fits into this domain
12. Common mistakes
13. Glossary
14. Source list

---

## 1. The big picture in one page

A company (the **buyer**) wants to purchase software or a cloud service from another company (the **seller**, also called the **vendor** or **provider**). That service will often touch the buyer's data, connect to its systems, or become part of how it operates.

Before agreeing, the buyer must decide: *can we trust this vendor with our information and operations?* To find out, the buyer's security team sends the vendor a **security questionnaire**: a structured list of questions about how the vendor protects data, controls access, responds to incidents, recovers from disasters, and manages its own suppliers. The buyer usually also asks for **evidence**, such as an independent audit report, to confirm the answers.

The key facts that define the whole domain:

- **It is a gate in the sales process.** Procurement often will not sign the contract until the security review is complete. A slow questionnaire therefore means a slow sale.
- **It is repetitive.** Every enterprise customer asks largely the same questions but there are highly customized as well and usually they're, in different wording and file formats.
- **It is cross-functional.** The answers live in the heads and documents of security, engineering, IT, HR, legal, and privacy teams, not in one place.
- **It is high-stakes.** A vendor's answers are formal representations. A wrong "Yes" can create contractual liability, damage trust, or hide a real risk.
- **Answering is not the same as passing.** A questionnaire is not an exam where every answer must be "Yes." The buyer is trying to understand risk, and an honest "No, but here is our compensating control" can be perfectly acceptable.
- **Proof matters more than claims.** A questionnaire is the vendor's own statement. Buyers corroborate it with independent evidence.

A rough mental model:

```
Buyer wants a product
        |
        v
Buyer classifies the vendor's risk  --->  chooses questionnaire depth
        |
        v
Vendor receives questionnaire + evidence request
        |
        v
Vendor's security/GRC lead coordinates experts to answer
        |
        v
Buyer reviews answers + evidence, records findings
        |
        v
Approve / approve with conditions / defer / reject
        |
        v
Contract signed, vendor monitored over time
```

---

## 2. Core concepts and how they differ

These terms are used interchangeably in casual conversation but are not identical.

| Term | Meaning |
|---|---|
| **Security questionnaire** | The list of questions itself. One input into a review. |
| **Vendor security assessment** | The broader evaluation: questionnaire, evidence, testing, external signals, and discussion with the vendor. |
| **Third-party risk assessment** | Broader still. Covers security, privacy, legal and regulatory compliance, financial health, business continuity, and operational risk. |
| **Third-Party Risk Management (TPRM)** | The ongoing program an organization runs to identify, assess, monitor, and manage risks from its suppliers. Also called **Vendor Risk Management (VRM)**. |
| **Due diligence** | The investigation a buyer performs before committing to a vendor. The questionnaire is a main tool of due diligence. |
| **GRC** | Governance, Risk, and Compliance. The function (and the software category) that manages policies, risks, controls, and audits inside an organization. |
| **RFP / RFI / DDQ** | Request for Proposal / Request for Information / Due Diligence Questionnaire. Documents buyers send to evaluate suppliers. Security questions often appear inside them. |

### Two directions of the same activity

- **Buyer side (vendor risk management):** assessing *other* companies. The organization asking the questions.
- **Seller side (questionnaire response):** answering questions about *your own* company. The organization receiving the questions.

The two use related vocabulary but are different jobs. Much of this guide takes the seller's perspective while explaining the buyer's reasoning, because the buyer's intent determines what a good answer looks like.

### What the buyer is really trying to establish

Beneath the questions, a buyer is evaluating five concerns:

1. **Data protection:** can the vendor protect the confidentiality, integrity, and availability of the data it handles? (These three together are the **CIA triad**.)
2. **Regulatory obligations:** could using this vendor cause the buyer to violate a law or regulation?
3. **Operational resilience:** can the vendor keep running, or recover quickly, if something goes wrong?
4. **Supply-chain exposure:** does the vendor depend on other companies that introduce risk?
5. **Accountability:** can the buyer later demonstrate that it performed reasonable due diligence?

The fifth point explains much of the process's rigidity. Buyers need a paper trail they can show to auditors, regulators, and executives.

---

## 3. The business context: where this appears in a sale

### 3.1 Where it sits in the sales cycle

There is no universal sequence, but enterprise software deals tend to follow this pattern.

| Stage | Commercial activity | Security and procurement activity |
|---|---|---|
| 1. Discovery | Buyer identifies a problem and looks at options | Light vendor screening may begin |
| 2. Qualification | Product fit is established | Buyer asks for a security overview or a Trust Center link |
| 3. Technical evaluation | Proof of concept, pilot, architecture talks | Security team identifies data, access, and integration risks |
| 4. Shortlisting | Buyer narrows to finalists | Formal risk assessment may start for finalists |
| 5. Negotiation | Pricing, scope, contract terms | Questionnaire, evidence collection, and privacy review run in parallel |
| 6. Approval | Business owner picks a preferred vendor | Security, privacy, legal, and procurement sign off |
| 7. Contract signature | Agreement signed | Security addenda and data-processing terms finalized |
| 8. Onboarding | Service configured and activated | Access, integrations, and data flows verified |
| 9. Ongoing oversight | Vendor delivers the service | Reassessment after incidents or material changes |

The questionnaire most often lands in stages 4 to 6, which is late and commercially painful: pricing is agreed, the champion inside the buyer wants to proceed, and then the deal waits on a spreadsheet. Some buyers screen earlier; highly regulated ones may require approval before even a pilot receives real data.

### 3.2 Why procurement blocks a contract

Procurement often acts as the **operational gatekeeper** for purchasing. A security review may be a mandatory condition for:

- approving a new vendor,
- executing the contract,
- granting access to production systems,
- transferring sensitive data,
- activating the service,
- renewing an existing agreement.

Important nuance: procurement blocking a deal does **not** mean procurement judged the vendor insecure. It usually means a *required approval has not yet been recorded*. The buyer's policy might say "no vendor processes sensitive data until security and privacy assessments are complete," and procurement enforces that policy.

### 3.3 Why it matters commercially to the seller

A single unresolved item can stall a deal for weeks: an unclear subprocessor list, a missing breach-notification clause, or a recovery commitment the vendor cannot make. For sellers, security review speed is a **sales-velocity** issue. This is why sales teams care about a task that salespeople are rarely qualified to answer.

---

## 4. Who is involved

### 4.1 Buyer side

| Role | Responsibility |
|---|---|
| **Business owner / sponsor** | Owns the need; may accept business-level residual risk within delegated authority |
| **Procurement** | Coordinates onboarding and approvals; may block purchase orders |
| **InfoSec** | Evaluates technical and organizational security controls; reviews answers and evidence |
| **TPRM team** | Classifies vendor risk, sets assessment depth, tracks findings |
| **Privacy / Data Protection** | Reviews personal-data processing, retention, transfers |
| **Legal** | Negotiates security addenda, liability, audit rights, breach notification |
| **Compliance** | Checks industry-specific regulatory obligations |
| **IT / Enterprise Architecture** | Reviews SSO, APIs, network connections, technical fit |
| **Business Continuity / Resilience** | Reviews disaster recovery and recovery commitments |
| **Internal Audit** | Independently checks that the process works; does not normally approve vendors |

**Who initiates?** It varies. The business creates the need, procurement registers the vendor, TPRM classifies risk, and InfoSec runs the technical review, but the order differs by company. "Procurement always starts it" and "InfoSec always starts it" are both oversimplifications.

**Who decides?** The reviewer who reads the answers is not necessarily the person who accepts the risk. Typical outcomes the decision-maker can choose: reject, choose another product, require remediation first, approve a time-limited exception with compensating controls, or accept the residual risk. Risk-acceptance authority should be documented, and a salesperson or procurement coordinator should not waive a material requirement on their own.

### 4.2 Seller side

| Role | Responsibility |
|---|---|
| **Account Executive / Sales** | Tracks the deal, deadlines, buyer communication; escalates delays |
| **Sales Engineer / Solutions Architect** | Explains architecture, integrations, deployment options |
| **Security / GRC lead** | Owns the response, validates control statements, manages evidence, escalates exceptions |
| **CTO / Engineering lead** | Confirms architecture; decides on engineering controls or remediation |
| **IT / IAM admin** | Evidence on SSO, MFA, privileged access, endpoint management, access reviews |
| **DevOps / Platform engineering** | Infrastructure, logging, backups, recovery architecture |
| **Legal / Privacy** | Contract commitments, data-processing terms, what documents may be disclosed |
| **HR / People Ops** | Background screening, security training, onboarding and offboarding |
| **Finance / Business Ops** | Insurance, financial and continuity information where needed |
| **Executive management** | Approves material representations and exceptions |

### 4.3 The "golden rule" of seller-side answering

**Assign each answer to the person who knows the truth.** A question like "Are all employees required to complete annual security awareness training?" should be answered from HR or training records, not by a sales rep who assumes it sounds standard.

| Topic | Natural source of truth |
|---|---|
| Encryption architecture | Security or platform engineering |
| Disaster recovery testing | Infrastructure or business-continuity owner |
| Breach notification | Incident-response owner, reviewed by legal |
| Data retention | Engineering, data governance, privacy |
| Subprocessor list | Vendor management, legal, privacy |
| Insurance coverage | Finance, risk, or legal |

### 4.4 Three kinds of ownership

A healthy response process separates:

- **Process owner:** accountable for delivering the completed questionnaire on time.
- **Control owner:** responsible for confirming a specific control exists and operates.
- **Approver:** authorized to approve the final response and any commitment it implies.

### 4.5 How company size changes things

| Seller profile | Typical model | Main challenge |
|---|---|---|
| Early-stage startup | CTO or a senior engineer answers, often with the founder | Controls may exist without formal policies or evidence |
| Growing SaaS company | Security/GRC lead coordinates engineering, HR, legal, sales engineering | Knowledge is scattered; answers drift out of sync |
| Mid-market company | Dedicated questionnaire owner or GRC team maintains approved answers | Keeping content current as volume grows |
| Large enterprise provider | Centralized response operations across many products and regions | Different products, entities, and regulatory regimes |

---

## 5. Standard questionnaires and custom ones

### 5.1 Why standards exist

Without them, every buyer invents its own questionnaire. One asks 40 questions, another 300, a third asks the same things in different words and formats. Standard questionnaires provide a **common structure, shared control domains, and reusable questions**.

But a standard questionnaire is **not** a certification, an audit, or a guarantee of security. It records what a vendor *says*. Independent reports provide independent evidence, and those have their own scope and limits.

### 5.2 CAIQ (Cloud Security Alliance)

- **Full name:** Consensus Assessments Initiative Questionnaire.
- **Publisher:** Cloud Security Alliance (CSA).
- **Companion framework:** the **Cloud Controls Matrix (CCM)**, a cloud-security control framework. CCM v4.1 was released in January 2026 with 207 controls across 17 domains.
- **Focus:** security controls of **cloud services**.
- **Question counts:** v3.1 had 310, v4.0 had 261, and v4.1 is reported at about 283 in secondary comparisons (the official page did not state the count). **CAIQ-Lite**, a streamlined version released January 2026, has 138 questions.
- **Typical users:** SaaS, PaaS, and IaaS providers; enterprises assessing cloud services.
- **Related program:** **CSA STAR** (Security, Trust, Assurance and Risk) registry. **Level 1** is a self-assessment (typically a completed CAIQ). **Level 2** involves independent third-party assessment.
- **Real-world practice:** major cloud providers such as AWS, Google Cloud, and Oracle publish completed CAIQs.
- **Caveat:** always confirm which CAIQ version a buyer wants; an old spreadsheet labeled "CAIQ" may not match.

### 5.3 SIG Core and SIG Lite (Shared Assessments)

- **Full name:** Standardized Information Gathering questionnaire.
- **Publisher:** Shared Assessments.
- **Focus:** **broad third-party risk**, not only cloud. Covers information security, privacy, business continuity, incident management, access controls, software and infrastructure security, and subcontractor (outsourcing) risk.
- **Tiers (2025 edition):**

| Version | Questions | Typical use |
|---|---|---|
| **SIG Lite** | 128 | Initial screening, lower-risk vendors |
| **SIG Core** | 627 | Vendors handling sensitive or regulated data |
| **SIG Detail** | 1,936 | Comprehensive, control-level due diligence |

- **Customization:** buyers can generate scoped versions by regulation, control family, or risk domain.
- **Key principle:** assessment depth should be proportional to the **vendor's risk**, not the vendor's size.
- **Seller caution:** a SIG you completed for one customer may not apply to a different product, deployment, or time period. Reuse needs validation.

### 5.4 VSA (Vendor Security Alliance)

- **Publisher:** Vendor Security Alliance.
- **Versions:** **VSA-Core** (critical security questions plus privacy topics, including US requirements and GDPR) and **VSA-Full** (more extensive).
- **Updates:** annual; available at no purchase fee subject to licensing terms.
- **Question count:** a current, verified count could not be established from the official site. Download the latest workbook and inspect it rather than quoting a number.
- **Typical users:** technology companies seeking a standardized, security-focused assessment.

### 5.5 HECVAT (Higher Education)

- **Full name:** Higher Education Community Vendor Assessment Toolkit.
- **Origin:** created by higher-education leaders with EDUCAUSE, Internet2, and REN-ISAC.
- **Focus:** colleges and universities assessing technology vendors. Goes beyond security to include **privacy, IT accessibility, and compliance**.
- **Current version:** HECVAT 4.1.6 per EDUCAUSE. Version 4 expanded privacy and AI/ML coverage.
- **Question count:** about 321 reported for the unified HECVAT 4 workbook (secondary source). The number a vendor actually answers depends on conditional logic and the institution's scope.
- **Cost:** free for higher-ed institutions and their vendors; third-party platforms wanting to embed it need permission.
- **Who encounters it:** any vendor selling to universities, including non-education products.

### 5.6 Comparison

| Framework | Main purpose | Typical audience | Reported size | Style |
|---|---|---|---|---|
| CAIQ v4.1 | Cloud-service security | Cloud buyers and providers | ~283 (secondary source) | Control-aligned to CCM |
| CAIQ-Lite | Lighter cloud review | Lower-risk cloud reviews | 138 | Focused |
| SIG Lite | Broad initial screen | Many industries | 128 | Broad, shallow |
| SIG Core | Detailed third-party review | Sensitive/regulated vendors | 627 | Broad, deep |
| SIG Detail | Comprehensive | Heavy due diligence | 1,936 | Extensive |
| VSA-Core / Full | Security + privacy basics | Tech-sector buyers | Not verified | Focused / full |
| HECVAT 4 | Higher-ed tech risk | Universities | ~321 (reported) | Security, privacy, accessibility, compliance |

### 5.7 Related standards you will see referenced

These are not questionnaires, but they appear in answers and evidence:

- **SOC 2** (AICPA): an independent audit report on controls (see Section 7).
- **ISO/IEC 27001:2022:** an international standard for an information security management system, with third-party certification.
- **NIST Cybersecurity Framework 2.0:** a US risk-management framework with six functions: Govern, Identify, Protect, Detect, Respond, Recover.
- **NIST SP 800-161:** guidance on cybersecurity supply-chain risk management.
- **GDPR:** the EU's data protection regulation, which drives many privacy and data-transfer questions.
- **HIPAA:** US law for health information, which drives healthcare-specific questions.
- **PCI DSS:** payment-card security standard.

### 5.8 Why enterprises still send custom spreadsheets

If standards exist, why do large companies send their own? Legitimate reasons:

1. **Unique regulation.** A bank may need answers on outsourcing rules, audit rights, or regulator access that a generic standard does not cover.
2. **Unique architecture.** If a SaaS product will connect to the buyer's identity provider and production database, the buyer needs details on SAML/OIDC, SCIM provisioning, API authentication, network paths, and data segregation.
3. **Consistent vendor comparison.** Sending the same custom questionnaire to three competing vendors allows an apples-to-apples decision.
4. **Deeper probing.** Standard: "Do you use MFA?" Custom: "Is phishing-resistant MFA enforced for all privileged production access, including emergency accounts, and what exception process exists?"
5. **Platform workflow.** Many enterprises run assessments inside a TPRM platform (such as OneTrust or Whistic) that supports both standards-based and customer-built templates.

### 5.9 The layered model: standard plus supplement

Buyers rarely choose between standard and custom. A common pattern:

| Layer | Purpose | Example |
|---|---|---|
| Standard baseline | Common security controls | CAIQ or SIG Lite |
| Specialized supplement | Risks of a technology or industry | AI data handling, healthcare data |
| Customer-specific questions | One buyer's unique use case | Integration with their payment system |

The buyer maps its risks to the standard, finds gaps, and writes extra questions only for those gaps. Example: a bank sending documents to an AI service might add "Are prompts retained in model-provider logs after processing?" on top of a standard encryption question.

---

## 6. The anatomy of a questionnaire: 15 recurring domains

Most questionnaires revisit a consistent set of themes even when wording differs. The often-quoted "80% overlap" is a **practical shorthand, not a measured statistic**. The example questions below are realistic illustrations written for this guide, not quotes from any specific company.

For each domain: what the buyer wants to know, example questions, and typical evidence.

### Domain 1: Security governance and risk management
**Buyer's goal:** is security run through accountable, documented, repeatable processes rather than individual heroics?
- Is the information security policy approved and reviewed at least annually and after material change?
- Is a named executive or security leader accountable for the program, including risk acceptance?
- Is there a risk register with likelihood, impact, owners, and target remediation dates?

**Evidence:** security policy, responsibility matrix, risk register, management review records.

### Domain 2: Identity and access management (IAM)
**Buyer's goal:** who can reach systems and data, how is access granted, and how are stolen credentials contained?
- Is phishing-resistant MFA enforced for privileged production access, and are exceptions reviewed?
- Are access rights reviewed periodically, and revoked immediately on termination?
- Are production admin privileges individual, least-privilege, and free of shared admin accounts?

**Evidence:** IAM policy, MFA configuration, access review records, joiner/mover/leaver procedures.

### Domain 3: Encryption and key management
**Buyer's goal:** is data protected from disclosure, and who controls the keys?
- Is data in transit protected with current TLS and weak ciphers disabled?
- Is data at rest encrypted in databases, object storage, backups, and replicas, and what is excluded?
- Who administers the keys, how are they rotated, and can a database admin decrypt customer data alone?

**Evidence:** encryption policy, architecture diagrams, cloud configuration evidence, key rotation procedures.
**Trap:** "AES-256" is not a complete answer. Scope (what is covered and what is not) is what matters.

### Domain 4: Network security and infrastructure isolation
**Buyer's goal:** how exposed are the systems, and how are environments separated?
- Are production admin interfaces restricted by private connectivity or identity-aware access?
- How are production, development, test, and corporate environments segmented?
- Are firewall rules reviewed and public-facing services inventoried?

**Evidence:** network diagrams, security-group standards, environment separation docs, attack-surface scans.

### Domain 5: Vulnerability management and penetration testing
**Buyer's goal:** are weaknesses found and fixed before attackers exploit them?
- Are production and internet-facing assets scanned on a schedule, with SLAs for critical findings?
- Is an independent penetration test done at least annually and after major changes, with tracked remediation?
- How are actively exploited vulnerabilities prioritized, and can emergency patches bypass normal release cycles?

**Evidence:** policy, pen-test executive summary, scan cadence and scope, remediation tracking, retest results.

### Domain 6: Secure software development lifecycle (SSDLC)
**Buyer's goal:** is security built into how the product is made and shipped?
- Are code changes peer-reviewed with automated security checks before merging to protected branches?
- Are dependencies scanned for known vulnerabilities and malicious packages?
- Are releases traceable to approved changes and controlled build pipelines, and who can bypass them?

**Evidence:** secure development policy, branch protection settings, software composition analysis reports, CI/CD documentation.

### Domain 7: Logging, monitoring, and threat detection
**Buyer's goal:** can the vendor notice suspicious activity and reconstruct what happened?
- Are privileged actions and authentication events logged centrally and protected from tampering?
- Are alerts monitored continuously, and what is the after-hours escalation path?
- What are the log retention periods?

**Evidence:** logging policy, SIEM summaries, escalation procedures, retention settings.

### Domain 8: Incident response and breach notification
**Buyer's goal:** can the vendor contain an incident and tell customers in time?
- Does the plan define severity levels, authority, containment steps, and customer communication duties?
- Were incident-response exercises run in the last 12 months, with follow-up on weaknesses?
- How is the customer notified of an incident affecting its data, and how do notification deadlines reconcile with legal obligations?

**Evidence:** incident response plan, tabletop exercise report, escalation matrix, notification procedures.
**Note:** notification deadlines come from the contract, the incident, and applicable law. No single period fits every case.

### Domain 9: Business continuity and disaster recovery (BC/DR)
**Buyer's goal:** if the service goes down or data is lost, how fast and how completely can it return?
- What are the approved RTO and RPO, and do they cover all critical components?
- Are backups isolated from production admin credentials, protected from deletion, and restore-tested?
- When was the last DR exercise, what scenarios did it cover, and were targets met?

**Evidence:** BCP and DR plans, business impact analysis, restoration test results.
**Key terms:** **RTO** (Recovery Time Objective) is the target time to restore service; **RPO** (Recovery Point Objective) is the maximum acceptable data loss measured in time. These are *targets*, not guarantees, unless written into a contract or SLA.

### Domain 10: Data governance, retention, and deletion
**Buyer's goal:** what data is held, where, for how long, and how does it get deleted?
- Is there a data inventory showing categories, purposes, locations, and who can access them?
- How are retention rules enforced across databases, object storage, logs, exports, and backups?
- After termination or a deletion request, how long until data is deleted, and how is deletion verified, including at subprocessors?

**Evidence:** data inventory or data-flow diagram, retention and deletion policy, backup lifecycle documents.
**Nuance:** deleting active records is different from letting backups expire. An honest answer explains both.

### Domain 11: Subprocessor and supply-chain management
**Buyer's goal:** does the vendor know and control the companies it depends on?
- Is there a current subprocessor inventory with locations, data categories, and purposes?
- What due diligence precedes onboarding a new subprocessor?
- How are customers told about subprocessor changes, and can they object?

**Evidence:** subprocessor list, vendor risk policy, due-diligence records, flow-down contracts.

### Domain 12: Privacy and regulatory compliance
**Buyer's goal:** does data handling comply with law and contract?
- What personal data is processed, for what purposes, under what legal and contractual basis?
- Can data be accessed from outside the customer's designated jurisdiction (support staff, subprocessors), and with what safeguards?
- How are data-subject requests and regulatory inquiries supported?

**Evidence:** privacy policy, DPA, records of processing, transfer documentation, privacy impact assessments.

### Domain 13: Personnel security
**Buyer's goal:** are people screened, trained, and removed from access properly?
- Is background screening performed for personnel with data access, consistent with law?
- Is security awareness training required at onboarding and on a recurring cycle, with tracked completion?
- How quickly is access revoked when someone leaves?

**Evidence:** HR policies, training records, offboarding procedures, confidentiality agreements.

### Domain 14: Application security and multi-tenant isolation
**Buyer's goal:** can one customer see another customer's data through a flaw?
- How is tenant isolation enforced at the authorization and data-access layers, and how is cross-tenant access tested?
- Are object-level authorization checks enforced server-side for API requests?
- What prevents cross-tenant access via admin functions, exports, or support tooling?

**Evidence:** architecture and authorization design, application pen-test summaries, isolation test results.

### Domain 15: AI security and AI-specific data handling
**Buyer's goal:** do AI features create data flows the buyer cannot otherwise see?
- If an external LLM provider is used, what customer data is sent, who processes it, and what retention and training restrictions apply?
- Do embeddings, vector indexes, prompts, outputs, and conversation logs follow the same access, retention, deletion, and residency rules as source documents?
- What stops one tenant's retrieved content from leaking into another's context, and how are prompt injection and unauthorized tool use tested?

**Evidence:** AI system inventory, AI data-flow diagram, model-provider list, AI retention and training policy.
**Why it is rising:** HECVAT 4 added AI coverage, and custom buyer questionnaires increasingly include AI sections.

### Domain-to-owner map (seller side)

| Domain | Typical internal owner |
|---|---|
| Governance | Security / GRC |
| IAM | IAM / security engineering |
| Encryption | Security / platform engineering |
| Network | Infrastructure / platform engineering |
| Vulnerability management | Product security / engineering |
| SSDLC | Engineering / product security |
| Logging and monitoring | Security operations |
| Incident response | Security / legal |
| BC/DR | Platform engineering / business continuity |
| Data governance | Privacy / data governance / engineering |
| Subprocessors | Vendor management / privacy / security |
| Privacy | Privacy / legal |
| Personnel | HR / security |
| Application security | Product security / engineering |
| AI security | AI engineering / security / privacy |

### Question types and answer formats

Questionnaire questions come in several shapes, which matters for anyone processing them:

- **Yes / No / N/A** with an optional comment field.
- **Free-text** descriptive answers.
- **Multiple choice** or dropdown selections.
- **Evidence request** ("attach your most recent penetration test summary").
- **Conditional questions** that appear only if an earlier answer was "Yes" (common in HECVAT and SIG).
- **Compound questions** that bundle several asks into one cell.

They also arrive in many **containers**: Excel workbooks (the most common), Word documents, PDFs, web forms, and buyer-owned portals.

---

## 7. Proof: the evidence buyers ask for

A questionnaire is the vendor's own statement. Evidence lets the buyer check it. There is **no single universal evidence package**; what is requested depends on the service's risk, the buyer's industry, and the data involved. The usual candidates:

### 7.1 SOC 2 report

- An **attestation** by an independent CPA firm, under AICPA standards, on a service organization's controls against the **Trust Services Criteria**.
- **Five categories:** Security, Availability, Confidentiality, Processing Integrity, Privacy. Only the categories in scope are covered. (Security is always included.)

| | **Type I** | **Type II** |
|---|---|---|
| Question answered | Are controls suitably designed and in place at a point in time? | Did controls operate effectively over a period (often 6 to 12 months)? |
| Evidence strength | Lower | Higher |

- **What a reviewer checks:** scope (does it cover the product being bought?), period (is it recent?), the **auditor's opinion** (unmodified, qualified, adverse, disclaimer), **exceptions** found in testing and management's response, **complementary user entity controls (CUECs)** the customer must implement, and how **subservice organizations** (e.g., the cloud host) are treated (**inclusive** vs. **carve-out**).
- **What it does not prove:** that the vendor cannot be breached, that every product is in scope, or that it guarantees compliance with every law.
- A startup may only have Type I at first; buyers sometimes accept alternative evidence or impose conditions while the Type II is completed.

### 7.2 ISO/IEC 27001 certification

- A standard for an **Information Security Management System (ISMS)**: the policies, processes, and controls through which an organization manages security.
- Certification is issued by an accredited **certification body** after audit, with ongoing surveillance audits.
- **Check:** certificate validity, certification body, legal entity, **scope statement**, sites covered, exclusions. A certificate for one office or product does not automatically cover everything. The **Statement of Applicability (SoA)** lists which controls apply.

| | SOC 2 Type II | ISO 27001 |
|---|---|---|
| What is assessed | Controls within an engagement's scope | An ISMS against an international standard |
| Output | Detailed attestation report | Certificate and scope information |
| Detail on exceptions | Visible inside the report | Not visible from the certificate alone |

They are complementary, not interchangeable.

### 7.3 Penetration test report

- **Penetration test (pen test):** authorized testers attempt to find and validate exploitable weaknesses within an agreed scope.
- Buyers want: who tested, when, what was in scope (external/internal, authenticated/unauthenticated, APIs), findings and severity, remediation status, and whether fixes were retested.
- Full reports are sensitive. Vendors often share an **executive summary** openly and the detailed report under **NDA** or through a controlled portal.
- A pen test is evidence of testing at a point in time, not a certificate that the product is secure.

### 7.4 Vulnerability scanning and remediation evidence

Distinguish four steps: **scanning** (find potential weaknesses), **validation** (confirm they are real), **remediation** (fix or mitigate), **retesting** (verify the fix). A scan report alone does not prove vulnerabilities were fixed.

### 7.5 Business continuity and disaster recovery evidence

BCP, DR plan, business impact analysis, backup policy, **restore test results**, recovery objectives, and SLAs. A plan never exercised is weaker assurance than a documented restore test.

### 7.6 Policies and procedures

Typical set: information security, access control, encryption, incident response, vulnerability management, secure development, data retention and deletion, vendor management, acceptable use, and business continuity. Policies show **intent**; they do not prove **operation**. The strongest package pairs a policy, an operational record showing it happened, and independent assessment where appropriate.

### 7.7 Privacy and data-processing documents

DPA, subprocessor list, data-flow diagram, retention and deletion documents, data residency information, records of processing, international transfer documentation (such as **Standard Contractual Clauses**), and privacy impact assessments.

### 7.8 Other frequently requested items

| Evidence | Validates | Limitation |
|---|---|---|
| Cyber insurance certificate | Coverage exists | Says nothing about control effectiveness |
| Architecture diagram | Components, integrations, trust boundaries | May be high-level or stale |
| Data-flow diagram | Where data moves and who processes it | Must be current and service-specific |
| Security training records | Training completion | Does not prevent mistakes |
| Access review records | Reviews occurred | Check scope, frequency, remediation |
| Tabletop exercise report | Response was practiced | Does not replicate a real incident |
| **SBOM** (software bill of materials) | Component inventory | Does not show every component is secure |
| External security rating | Outside-in signal | Incomplete; not a substitute for direct evidence |
| Industry attestations (HIPAA, PCI, FedRAMP, etc.) | Specific regulatory compliance | Applicability depends on scope |

Buyers should not request everything from everyone; over-collection is itself a risk, which is why controlled sharing (NDAs, redaction, trust portals) is common.

### 7.9 The evidence ladder

The strength of support behind an answer, from weakest to strongest:

1. **Assumption:** "Yes, we use AWS."
2. **General knowledge:** "Yes, our databases are encrypted."
3. **Documented control:** "Our standard requires encryption of production databases, backups, and object storage."
4. **Verified answer:** the same claim, checked against actual configuration, with a named owner and date.
5. **Independently attested:** supported by an auditor's report covering that scope.

---

## 8. How a seller actually answers a questionnaire

### 8.1 What the engineer does

A senior engineer should not answer from memory or assumption. Depth varies by question type:

| Question type | Example | Where the answer comes from |
|---|---|---|
| Policy / governance | "Do you have an approved security policy?" | Policy repository or GRC system |
| Standard technical control | "Is MFA required for admin access?" | IdP configuration, IAM docs |
| Architecture-specific | "Is data encrypted in temporary processing storage?" | Architecture and data-flow diagrams, storage config, app design |
| Assurance | "Has production been independently pen tested?" | Security records and the report |

Questionnaire length does not predict difficulty; control complexity does. A procedural-sounding question can turn technical ("Can you detect unauthorized access to production customer data and notify affected customers within the contractual deadline?").

### 8.2 Typical internal sources

Security policies, architecture and data-flow diagrams, cloud configuration and asset inventory, IAM policies and access reviews, vulnerability management system, SIEM and monitoring docs, incident response docs, SOC 2 report, pen-test reports, subprocessor register, and the GRC control library.

### 8.3 Handling an undocumented answer

Three outcomes: **(A)** find existing evidence, **(B)** investigate the implementation with the relevant engineers, or **(C)** report the limitation honestly instead of answering "Yes" on assumption. A questionnaire sometimes surfaces a genuine control or documentation gap, and the company must then decide whether to remediate or disclose.

### 8.4 End-to-end workflow

1. **Intake:** receive the file or portal link; identify product, service, deployment, and scope.
2. **Extraction:** identify each question, answer field, instruction, and conditional.
3. **Classification:** tag by topic (encryption, IAM, DR, etc.).
4. **Reuse:** match to previously approved answers.
5. **Evidence mapping:** link answers to policies, diagrams, reports, or control owners.
6. **Routing:** assign unanswered or sensitive questions to the right experts.
7. **Gap investigation:** inspect architecture or operational evidence where documentation is thin.
8. **Record limitations:** document exceptions, assumptions, and partially implemented controls.
9. **Review and approval:** control owners verify; legal reviews contractual language; an approver signs off.
10. **Delivery:** return the completed file in its original format or enter answers into the buyer's portal.
11. **Knowledge update:** store verified answers and evidence for next time, with scope and review dates.

### 8.5 Time and effort (planning estimates, not industry averages)

| Questionnaire type | Approx. questions | Senior-engineer effort |
|---|---|---|
| Simple customer questionnaire | 20 to 50 | 1 to 4 hours |
| Standard enterprise assessment | 100 to 250 | 4 to 12 hours |
| Large assessment (e.g., SIG Core) | 500 to 700 | 1 to 3 working days |
| Complex with custom technical questions | 200 to 600+ | 3 to 7+ working days |

These are the engineer's own effort, not elapsed time; waiting on legal, privacy, or infrastructure teams stretches the calendar considerably. A Whistic industry survey reported 54% of respondents spent 1 to 4 hours per questionnaire and 26% spent 5 to 10 hours; a practitioner guide suggests at least a full day for a questionnaire with hundreds of questions. Definitions differ across sources, so treat the figures as indicative.

Illustrative effort for a 200-question questionnaire:

| Situation | Approx. effort |
|---|---|
| No central documentation or answer library | 12 to 25 hours |
| Maintained answer library and evidence | 2 to 6 hours |
| AI first draft grounded in approved documents, then human review | 1 to 4 hours (assumes prepared knowledge base and no major gaps) |

### 8.6 What a well-governed answer record contains

- The approved answer text
- The product or service it applies to
- The accountable owner
- The source document or evidence
- The date last verified
- Approval status
- Known limitations or exceptions
- The conditions that trigger re-review (new subprocessor, architecture change, new region, etc.)

**Weak answer:** "Yes, all data is encrypted."
**Stronger answer:** "Customer data in the production database and primary object storage is encrypted at rest using the cloud provider's managed encryption. Backup storage is covered by the documented backup-encryption configuration. Temporary export and diagnostic paths are reviewed separately. Scope verified by the platform engineering owner." (Only valid if those facts have actually been verified.)

---

## 9. Why "just publish it once" doesn't fully work

A natural question: if standard questionnaires exist, why can't cloud providers publish a completed one and let every buyer read it? In fact many do (AWS, Google Cloud, and Oracle publish CAIQs). It reduces work but does not eliminate reviews, for five reasons:

1. **Buyers differ.** An online retailer using a product for email marketing and a bank using it for financial data have different risk tolerances and legal obligations, even though the vendor's controls are identical.
2. **A statement is not proof.** A published self-assessment shows what the vendor claims. Independent assurance (SOC 2, STAR Level 2, ISO certification) is a different and stronger kind of evidence.
3. **Shared responsibility.** In cloud services, security duties are split between provider and customer. "Is MFA enforced for privileged access?" could mean the provider's staff, the SaaS vendor's admins, the customer's users, or service accounts. This is formalized as the **shared responsibility model**.
4. **Scope.** One vendor may sell many products with different architectures, data flows, and subprocessors. A certificate or report covers a defined scope, not "the company."
5. **Time.** New features, new subprocessors, hosting changes, incidents, and new regions can make last year's answers wrong.

Additional barriers: detailed evidence (audit reports, pen tests, architecture diagrams) is sensitive and gets gated behind NDAs; and buyers must show they did their own due diligence, which pushes them to ask even when answers are public.

**Idealized model often discussed:** a public security profile per product; a restricted evidence package for qualified customers; and customer-specific questions only for genuine gaps. In one line: *assess once, verify the evidence, publish the results, and let each buyer examine only the risks specific to its use.*

---

## 10. The tool landscape (categories and examples)

Companies use several categories of tools. They overlap, and vendors often span more than one. This section describes **what each category does and who uses it**, not detailed architecture or pricing.

### 10.1 Buyer-side: TPRM / vendor risk platforms

Used by the organization **asking** the questions. They keep a vendor inventory, tier vendors by risk, send questionnaires, collect evidence, record findings, and track reassessments.

- **OneTrust:** third-party risk management with both standards-based and custom assessment templates.
- **Whistic:** vendor assessments, security-document exchange, AI-assisted evidence review, and a Trust Center Exchange linking buyers and sellers.
- Others in the category include Prevalent, ProcessUnity, and similar TPRM suites.

### 10.2 Seller-side: security questionnaire automation

Used by the organization **answering**. They ingest questionnaires, draft answers from a knowledge base, route questions to experts, and export the completed file or fill a portal.

- **Security-focused:** Conveyor, HyperComply, SecurityPal, and similar.
- **RFP-response platforms that also handle security questionnaires:** Loopio, Responsive, Qvidian, and similar.
- **AI-first entrants:** AutoRFP.ai, Arphie, and others.
- **Compliance platforms with questionnaire modules:** Vanta, Drata.

Common underlying approaches (a conceptual classification, not a product ranking): a **curated Q&A library**, **retrieval over documents** (often called RAG, retrieval-augmented generation), **browser/portal automation** for questionnaires hosted on a buyer's site, and **hybrids** combining these with human review.

### 10.3 Trust Centers (trust portals)

A **Trust Center** is a branded web page where a vendor publishes security information: certifications, policies, subprocessor lists, FAQs, and gated documents such as SOC 2 reports (often released after an NDA click-through or approval). The goal is to answer buyer questions *before* a questionnaire is sent. Examples: SafeBase (now part of Drata), Conveyor, Vanta Trust Center, HyperComply Trust Pages, Whistic profiles.

### 10.4 Compliance automation / GRC platforms

Used by the vendor to **achieve and maintain** certifications. They connect to cloud accounts, HR systems, and code repositories to collect evidence continuously, track policies, and prepare for audits (SOC 2, ISO 27001, HIPAA, etc.). Examples: Vanta, Drata, Secureframe. Their evidence stores are a natural raw material for answering questionnaires.

### 10.5 Security ratings and attack-surface monitoring

Outside-in scoring of a company's internet-facing posture, used by buyers as an additional signal and increasingly by sellers to preempt questions. Examples: SecurityScorecard, BitSight. These ratings are incomplete and are not a substitute for direct evidence.

### 10.6 Supporting tools in the seller's own environment

| Tool type | Role in answering questionnaires |
|---|---|
| **IdP / SSO** (Okta, Entra ID, Google Workspace) | Evidence for MFA, access, offboarding |
| **Cloud security posture tools** (CSPM) | Evidence for encryption, network, configuration |
| **Vulnerability scanners and SCA tools** | Scan coverage, dependency risk |
| **SIEM / logging platforms** | Monitoring and retention evidence |
| **MDM / endpoint management** | Device encryption and patching evidence |
| **Ticketing systems** (Jira, ServiceNow) | Remediation and change records |
| **Document stores** (Confluence, Notion, Google Drive, SharePoint) | Policies and procedures |
| **Collaboration tools** (Slack, Teams) | Routing questions to experts |
| **CRM** (Salesforce, HubSpot) | Linking questionnaires to deals |

### 10.7 Shared standards bodies and communities

CSA (CAIQ, CCM, STAR), Shared Assessments (SIG), Vendor Security Alliance (VSA), EDUCAUSE (HECVAT), NIST, AICPA (SOC), ISO/IEC.

---

## 11. Where AI fits into this domain

AI enters at three points: **drafting** answers, **reviewing** incoming answers (buyer side), and **matching** questions to evidence. This section covers domain-level considerations only.

### 11.1 Why the task suits AI

- Questions repeat heavily across buyers.
- Answers largely exist in policies, prior questionnaires, and audit reports.
- The work is time-consuming text matching and drafting.
- A human review step already exists in the process.

### 11.2 Why it is harder than it looks

| Challenge | Why it matters here |
|---|---|
| **Hallucination** | A fabricated "Yes" is a false security representation with legal and commercial consequences |
| **Stale evidence** | Old policies or reports may contradict current reality |
| **Conflicting sources** | Two documents may disagree; the system needs a rule for which wins |
| **Scope confusion** | An answer true for Product A may be false for Product B |
| **Compound and ambiguous questions** | One cell may ask several things, or use terms differently from the vendor |
| **Abstention** | The correct output is sometimes "insufficient evidence; route to a human" |
| **Traceability** | Reviewers need to see *which source* supports each answer |
| **Confidentiality** | The knowledge base holds sensitive security details; sending it to external model providers raises its own privacy questions |
| **Format handling** | Excel, Word, PDF, and portals each need different extraction and write-back logic |
| **Accountability** | A human must still approve answers that carry commitments |

### 11.3 Privacy questions that buyers of AI tools ask

These distinctions come up constantly and are easy to conflate:

- **No training on customer data:** the vendor or model provider does not use your content to train models.
- **Zero data retention (ZDR):** the model provider does not keep prompts and outputs beyond the processing period.
- **Application retention and deletion:** how long the software vendor keeps your data, indexes, logs, and backups, and how deletion works.
- **Data residency / sovereignty:** where data is stored and processed, including model inference and support access.
- **Deployment model:** regional SaaS, single-tenant SaaS, private cloud, customer-managed (runs in your cloud account), or on-premises. These are not equivalent.

A vendor can satisfy one of these without satisfying the others.

---

## 12. Common mistakes

**Buyer-side**
1. Treating a completed questionnaire as proof of security.
2. Assuming SOC 2 means the vendor is secure (check scope, period, opinion, exceptions).
3. Assuming a certification covers every product or subsidiary.
4. Treating a questionnaire score as the final risk decision (a vendor can score well and still fail one mandatory requirement, such as data residency).
5. Requesting more evidence than necessary.
6. Sending the longest questionnaire to every vendor instead of matching depth to risk.

**Seller-side**
1. Letting sales answer technical questions.
2. Reusing old answers without validation.
3. Answering "Yes" when the truth is conditional.
4. Confusing policy with operational evidence.
5. Leaving no named owner or last-verified date on stored answers.
6. Claiming a control covers everything when exceptions exist (for example, a log store or export path outside the encryption boundary).

---

## 13. Glossary

**AICPA:** American Institute of Certified Public Accountants; publishes the SOC attestation standards.

**Attestation:** an independent professional's formal conclusion about a statement or control environment.

**Attack surface:** the sum of points where an attacker could try to enter or extract data.

**Audit rights:** contractual right of a customer to audit, or receive audit evidence from, a vendor.

**Backup:** a copy of data held for recovery. Restore-testing proves it works.

**BCP / DR:** Business Continuity Plan / Disaster Recovery plan.

**BIA:** Business Impact Analysis; assesses the effect of disruption on operations.

**CAIQ:** Consensus Assessments Initiative Questionnaire (CSA).

**CCM:** Cloud Controls Matrix (CSA); the control framework behind CAIQ.

**CIA triad:** Confidentiality, Integrity, Availability.

**CISO:** Chief Information Security Officer.

**Compensating control:** an alternative safeguard that reduces risk when a standard control is not implemented.

**Complementary user entity controls (CUECs):** controls a SOC 2 report says the *customer* must operate for the vendor's controls to be effective.

**Control:** a safeguard, process, or technical measure that reduces risk.

**Control owner:** the person responsible for a given control operating as described.

**CSA / STAR:** Cloud Security Alliance / Security, Trust, Assurance and Risk registry.

**CSPM:** Cloud Security Posture Management; tools that check cloud configuration against best practice.

**Data residency / data sovereignty:** requirements about where data may be stored or processed and which legal regime governs it.

**Data-flow diagram:** shows how data moves between systems, people, and third parties.

**DDQ:** Due Diligence Questionnaire.

**DPA:** Data Processing Agreement; contract terms for how a processor handles a controller's personal data.

**Due diligence:** investigation performed before committing to a relationship.

**Embedding / vector index:** numeric representation of text used for semantic search; relevant to AI features and their data-lifecycle questions.

**Encryption at rest / in transit:** protecting stored data / data moving across networks.

**Evidence:** documents or records that substantiate a claim.

**GDPR:** EU General Data Protection Regulation.

**GRC:** Governance, Risk, and Compliance.

**HECVAT:** Higher Education Community Vendor Assessment Toolkit.

**HIPAA:** US Health Insurance Portability and Accountability Act.

**IAM:** Identity and Access Management.

**IdP:** Identity Provider (Okta, Entra ID, etc.).

**Incident response (IR):** the process for detecting, containing, and recovering from security incidents.

**ISMS:** Information Security Management System (the subject of ISO 27001).

**ISO/IEC 27001:** international standard for an ISMS.

**Least privilege:** granting only the access needed for a role.

**LLM:** Large Language Model.

**MFA:** Multi-Factor Authentication. **Phishing-resistant MFA** (e.g., hardware keys, passkeys) resists credential-phishing attacks that defeat SMS or code-based MFA.

**Multi-tenant:** one application instance serving multiple customers (tenants) whose data must stay separated.

**NDA:** Non-Disclosure Agreement.

**NIST CSF:** NIST Cybersecurity Framework (Govern, Identify, Protect, Detect, Respond, Recover).

**Penetration test:** authorized simulated attack to find exploitable weaknesses.

**Portal (buyer portal):** a web system owned by the buyer where questionnaires are completed.

**Processor / controller:** under privacy law, the processor handles data on behalf of the controller (usually the customer).

**RAG:** Retrieval-Augmented Generation; an LLM drafts answers using passages retrieved from a document set.

**Residual risk:** risk remaining after controls are applied.

**Risk acceptance:** a documented decision by an authorized person to live with a given risk.

**Risk register:** a log of identified risks with ratings, owners, and treatment plans.

**RPO / RTO:** Recovery Point Objective / Recovery Time Objective.

**SBOM:** Software Bill of Materials.

**SCIM:** System for Cross-domain Identity Management; standard for automating user provisioning.

**SAML / OIDC:** standards for single sign-on and federated identity.

**SCC:** Standard Contractual Clauses; mechanism for lawful cross-border personal data transfers (EU).

**SCA:** Software Composition Analysis; scans open-source dependencies for known vulnerabilities.

**Shared responsibility model:** division of security duties between a cloud/service provider and its customer.

**SIEM:** Security Information and Event Management; centralized log analysis and alerting.

**SIG:** Standardized Information Gathering questionnaire (Shared Assessments).

**SLA:** Service Level Agreement.

**SOC 2:** AICPA attestation report on service-organization controls (Type I point-in-time; Type II over a period).

**SoA:** Statement of Applicability (ISO 27001).

**SSDLC / SDLC:** Secure Software Development Lifecycle.

**SSO:** Single Sign-On.

**Statement of scope / system description:** the part of an audit report or certificate that defines what was examined.

**Subprocessor:** a third party engaged by a vendor that processes the customer's data.

**Subservice organization:** an outsourced provider whose services are relevant to a SOC 2 report's controls (e.g., a cloud host).

**Tabletop exercise:** a discussion-based simulation of an incident to test response plans.

**Tenant isolation:** controls that keep each customer's data separate in a multi-tenant system.

**TPRM / VRM:** Third-Party Risk Management / Vendor Risk Management.

**Trust Center:** a vendor-hosted portal publishing security and compliance information.

**Trust Services Criteria:** the SOC 2 criteria: Security, Availability, Confidentiality, Processing Integrity, Privacy.

**VSA:** Vendor Security Alliance questionnaires (Core and Full).

**Zero data retention (ZDR):** a provider commitment not to retain prompts and outputs beyond processing.

---

## 14. Source list

Primary and official references for further reading. Verify current versions before relying on counts or details.

**Frameworks and questionnaires**
- Cloud Security Alliance: CAIQ and Cloud Controls Matrix, CSA STAR program
- Shared Assessments: SIG questionnaire (2025 update)
- Vendor Security Alliance: VSA-Core and VSA-Full downloads
- EDUCAUSE: Higher Education Community Vendor Assessment Toolkit (HECVAT)
- NIST: Cybersecurity Framework 2.0; SP 800-161 (supply-chain risk management); SP 1326 due-diligence quick-start guide (2026)

**Assurance and certification**
- AICPA: SOC 2 and the SOC 2 report review checklist
- ISO/IEC 27001:2022

**TPRM and trust platforms (for category understanding)**
- OneTrust third-party risk documentation
- Whistic vendor assessment documentation
- Vendor documentation for Conveyor, HyperComply, Vanta, Drata/SafeBase, Loopio, Responsive, AutoRFP.ai, Arphie, SecurityPal

**Industry data on effort**
- Whistic industry survey on questionnaire time; practitioner guides (e.g., Cobalt)

---

### Final mental model

1. A security questionnaire is a **procurement risk-control mechanism**: it helps a buyer decide whether a provider can be trusted with its data and operations.
2. It is **one input** among several: independent reports, technical evidence, contract terms, and actual service scope all matter.
3. **Different people own different parts** on both sides; the right answer comes from the person who knows the truth.
4. **Standards reduce duplication but do not remove custom needs**: baseline, specialized supplement, then customer-specific gaps.
5. The best answers explain **how a control actually operates, its scope, and how it is tested**, not just that it exists.
6. The goal is **risk-based approval**, not a perfect score. The buyer must be able to explain why it trusts a vendor, what evidence supports that, what risk remains, who accepted it, and what triggers reassessment.