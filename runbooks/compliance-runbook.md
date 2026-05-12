# Compliance Runbook — HIPAA, HITECH, NIST CSF, and Beyond

> A practical, plain-English compliance reference for IT and security practitioners who need to operate inside multiple frameworks at once. Built from real-world healthcare IT and SMB consulting work — not legal advice, not a substitute for a Risk Analysis, but the document I wish I'd had on day one.
>
> **Use this when:** preparing for an audit, setting up a new tenant or environment, scoping a Risk Analysis, mapping one framework to another, or answering "do we need to do X for compliance?"
>
> **This is not legal advice.** Compliance requirements depend on your specific circumstances, jurisdiction, and contracts. Work with qualified counsel for binding decisions.

---

## Contents

- [How to Use This Runbook](#how-to-use-this-runbook)
- [Framework Quick Reference](#framework-quick-reference)
- [HIPAA Security Rule](#hipaa-security-rule)
- [HIPAA Privacy Rule](#hipaa-privacy-rule)
- [HIPAA Breach Notification Rule (HITECH)](#hipaa-breach-notification-rule-hitech)
- [HITECH Act](#hitech-act)
- [NIST Cybersecurity Framework 2.0](#nist-cybersecurity-framework-20)
- [NIST SP 800-53](#nist-sp-800-53)
- [NIST SP 800-171 & CMMC](#nist-sp-800-171--cmmc)
- [SOC 2](#soc-2)
- [PCI DSS](#pci-dss)
- [GDPR](#gdpr)
- [CCPA / CPRA](#ccpa--cpra)
- [State Breach Notification Laws](#state-breach-notification-laws)
- [Cross-Framework Control Mappings](#cross-framework-control-mappings)
- [Annual Compliance Calendar](#annual-compliance-calendar)
- [Audit Prep Checklists](#audit-prep-checklists)
- [Common Findings to Avoid](#common-findings-to-avoid)
- [Tools & Templates](#tools--templates)
- [References](#references)

---

## How to Use This Runbook

**Three ways to enter:**

1. **By framework** — jump to the section for the rule you're working with
2. **By question** — use the Cross-Framework Mappings to find equivalent controls across frameworks
3. **By calendar** — use the Annual Compliance Calendar to plan what's due when

**Two operating principles:**

- **Most controls overlap.** If you implement NIST CSF 2.0 well, you cover ~70% of HIPAA Security Rule, ~60% of SOC 2 Common Criteria, and most of PCI DSS technical requirements. Don't build separate stacks for each.
- **Documentation IS the control.** "We do X" without written policy + evidence = audit finding. The activity is necessary but not sufficient.

---

## Framework Quick Reference

| Framework | Who must comply | Enforcer | Penalty | Renewal |
|---|---|---|---|---|
| **HIPAA Security Rule** | Covered Entities (CEs), Business Associates (BAs) | HHS OCR | $137–$2.07M per violation/year (2024) | Continuous; ARisk Analysis at least annually |
| **HIPAA Privacy Rule** | CEs, BAs | HHS OCR | Same tier as Security Rule | Continuous |
| **HIPAA Breach Notification** | CEs, BAs | HHS OCR + state AGs | Same tier + state penalties | Event-driven (60-day notification) |
| **HITECH** | CEs, BAs, EHR vendors | HHS OCR + ONC | Up to $2.07M per violation/year | Continuous |
| **NIST CSF 2.0** | Voluntary (often contractually required) | None directly; auditors verify | None directly | Continuous; subcategory assessment annually |
| **NIST 800-53** | Federal agencies, contractors | OMB, agency CIO/CISO | Contract loss | Continuous; ATO every 1-3 years |
| **NIST 800-171 / CMMC** | DoD contractors handling CUI | DoD CIO, CMMC AB | Contract loss; False Claims Act liability | Self-assessment annually; CMMC certification every 3 years |
| **SOC 2** | Service providers (voluntary, customer-driven) | AICPA-licensed CPAs | Customer loss | Type I once; Type II annually |
| **PCI DSS** | Anyone handling cardholder data | Card brands, acquiring banks | $5k–$100k/month + card brand fines | Annual (SAQ or ROC); quarterly ASV scans |
| **GDPR** | Any org processing EU resident data | EU Data Protection Authorities | Up to €20M or 4% global revenue | Continuous |
| **CCPA / CPRA** | Businesses meeting thresholds with CA resident data | California AG, CPPA | $2,500–$7,500 per intentional violation | Continuous |

---

## HIPAA Security Rule

**Citation:** 45 CFR Parts 160 and 164, Subparts A and C
**Scope:** Electronic Protected Health Information (ePHI) — any individually identifiable health information in electronic form
**Last major update:** Proposed update January 2025 (final rule expected 2026)

### The three safeguard categories

The Security Rule organizes requirements into three categories. Each contains "standards" (mandatory) and "implementation specifications" (either Required or Addressable).

> **"Addressable" does NOT mean optional.** It means you must either implement it, implement an equivalent alternative, or document why neither is reasonable. Most OCR findings cite Addressable specs that were treated as optional.

### Administrative Safeguards (§164.308)

| Standard | Implementation Specs | Required/Addressable |
|---|---|---|
| Security Management Process | Risk Analysis | **Required** |
| | Risk Management | **Required** |
| | Sanction Policy | **Required** |
| | Information System Activity Review | **Required** |
| Assigned Security Responsibility | (Single standard) | **Required** — name a Security Officer |
| Workforce Security | Authorization/supervision | Addressable |
| | Workforce clearance | Addressable |
| | Termination procedures | Addressable |
| Information Access Management | Isolating healthcare clearinghouse | **Required** (if applicable) |
| | Access authorization | Addressable |
| | Access establishment/modification | Addressable |
| Security Awareness & Training | Security reminders | Addressable |
| | Protection from malicious software | Addressable |
| | Log-in monitoring | Addressable |
| | Password management | Addressable |
| Security Incident Procedures | Response and reporting | **Required** |
| Contingency Plan | Data backup plan | **Required** |
| | Disaster recovery plan | **Required** |
| | Emergency mode operation plan | **Required** |
| | Testing and revision | Addressable |
| | Apps/data criticality analysis | Addressable |
| Evaluation | (Periodic technical/nontechnical evaluation) | **Required** |
| Business Associate Contracts | Written contract | **Required** |

### Physical Safeguards (§164.310)

| Standard | Implementation Specs | Required/Addressable |
|---|---|---|
| Facility Access Controls | Contingency operations | Addressable |
| | Facility security plan | Addressable |
| | Access control & validation | Addressable |
| | Maintenance records | Addressable |
| Workstation Use | (Single standard) | **Required** |
| Workstation Security | (Single standard) | **Required** |
| Device & Media Controls | Disposal | **Required** |
| | Media re-use | **Required** |
| | Accountability | Addressable |
| | Data backup & storage | Addressable |

### Technical Safeguards (§164.312)

| Standard | Implementation Specs | Required/Addressable |
|---|---|---|
| Access Control | Unique user identification | **Required** |
| | Emergency access procedure | **Required** |
| | Automatic logoff | Addressable |
| | Encryption and decryption | Addressable |
| Audit Controls | (Single standard) | **Required** |
| Integrity | Mechanism to authenticate ePHI | Addressable |
| Person/Entity Authentication | (Single standard) | **Required** |
| Transmission Security | Integrity controls | Addressable |
| | Encryption | Addressable |

### What "encryption is addressable" really means

If you don't encrypt ePHI at rest and in transit, you must:

1. **Document why** in your Risk Analysis (e.g., "device incompatibility" — rarely defensible in 2026)
2. Implement an equivalent alternative
3. Be prepared to defend this to OCR

In practice: **encrypt everything.** AES-256 at rest, TLS 1.2+ in transit. Encrypted ePHI on lost devices may avoid breach notification under the [Safe Harbor provision](https://www.hhs.gov/hipaa/for-professionals/breach-notification/guidance/index.html).

### The Risk Analysis (§164.308(a)(1)(ii)(A))

The single most-cited deficiency in OCR enforcement actions. Required, not addressable. Must be:

- **Comprehensive** — covers every system that creates, receives, maintains, or transmits ePHI
- **Documented** — written analysis identifying threats, vulnerabilities, current controls, likelihood, impact
- **Updated** — at least annually and after material changes (new systems, mergers, breaches)
- **Acted upon** — drives a Risk Management Plan with prioritized remediation

**Free tool:** [HHS/ONC Security Risk Assessment Tool](https://www.healthit.gov/topic/privacy-security-and-hipaa/security-risk-assessment-tool) — works for small practices; large orgs need more

### Healthcare-IT specifics I've seen bite people

- **EMR access logs must be reviewed**, not just collected (§164.308(a)(1)(ii)(D))
- **Workstation timeout** in clinical areas — set to under 5 minutes in shared workstations; document compensating controls if you can't
- **MFP/printer hard drives** contain ePHI — wipe before disposal, document the wipe (§164.310(d)(2))
- **Medical-device segmentation** — IoMT belongs on its own VLAN; document the segmentation
- **BAA before access** — no PHI passes to a vendor until BAA is signed. Yes, including Microsoft (Office 365 BAA is free but you have to request it)
- **Mobile device policy** — required even if you only allow corporate phones. Especially if you allow BYOD.

### HIPAA Risk Analysis vs. Risk Assessment

They're often used interchangeably but OCR uses "Risk Analysis" for the formal §164.308(a)(1)(ii)(A) document. A Security Risk Assessment (SRA) tool produces the analysis. Don't get tripped up by the terminology in audit responses — use HHS's language.

---

## HIPAA Privacy Rule

**Citation:** 45 CFR Part 164, Subparts A and E
**Scope:** All Protected Health Information (PHI) — electronic, paper, oral
**Last major update:** Proposed update April 2024 (reproductive-health protections)

### Core requirements

- **Notice of Privacy Practices (NPP)** — given to every patient, posted publicly
- **Minimum Necessary Standard** — disclose only the minimum PHI needed for the task
- **Patient rights:**
  - Access (must respond within 30 days, extendable once by 30 days; OCR is aggressive on this)
  - Amendment (correct errors in record)
  - Accounting of Disclosures (who got the PHI, for what)
  - Restriction (patient can request limits — must grant if paying out of pocket for the service)
  - Confidential Communications (alternative addresses/phones)
- **Authorizations** — required for any use beyond TPO (Treatment, Payment, Operations)
- **Business Associate Agreements** — required with any vendor who creates, receives, maintains, or transmits PHI on the CE's behalf

### Common pitfalls

- **Right of Access timeline** — 30 days is a hard cap. Per-page fees capped (often $6.50 flat for electronic copies). OCR runs a [Right of Access initiative](https://www.hhs.gov/hipaa/for-professionals/compliance-enforcement/agreements/index.html) — many recent enforcements.
- **De-identification** — the [Safe Harbor method](https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/index.html) requires removing 18 specific identifiers. Hash-of-MRN is NOT de-identified.
- **Marketing vs. healthcare operations** — sponsored messages need an authorization. Reminders for refills usually don't.

---

## HIPAA Breach Notification Rule (HITECH)

**Citation:** 45 CFR §§164.400-414
**Trigger:** Any acquisition, access, use, or disclosure of PHI not permitted by the Privacy Rule, that compromises security/privacy

### Breach Risk Assessment — the four-factor test

When you suspect a breach, document the analysis of these four factors:

1. **Nature and extent of PHI** — what data, how identifying, how sensitive (mental health? STIs? SSNs?)
2. **Unauthorized person** — who received it, do they have an obligation to protect it (another covered entity vs. random recipient)
3. **Whether PHI was actually acquired or viewed** — vs. just exposed (was the email opened?)
4. **Extent of mitigation** — what did you do to reduce risk (assurances of destruction, recovery of devices)

**Presumption:** Any impermissible use/disclosure IS a breach UNLESS you can demonstrate low probability of compromise via this four-factor test, OR it falls under an exception (good-faith access by workforce, inadvertent intra-org disclosure, or recipient could not reasonably have retained the info).

### Notification timeline

| Breach size | Who to notify | When |
|---|---|---|
| **Any size** | Affected individuals | Within 60 calendar days of discovery |
| **500+ in a state** | Major media in state | Within 60 days |
| **500+ total** | HHS OCR | Within 60 days (and OCR posts publicly on [Wall of Shame](https://ocrportal.hhs.gov/ocr/breach/breach_report.jsf)) |
| **Under 500** | HHS OCR | Annually, within 60 days of end of calendar year |
| **BA breach** | Affected CE | Without unreasonable delay; within 60 days |

### Encryption Safe Harbor

If the PHI was encrypted per NIST guidance ([FIPS 140-2 validated](https://csrc.nist.gov/projects/cryptographic-module-validation-program)) AND the decryption key was not also compromised, you may not need to notify. **Document the encryption at time of incident** — claim doesn't work retroactively.

### What goes in the notification

- Brief description of what happened
- Types of PHI involved (no actual PHI in the notice itself)
- Steps individuals should take to protect themselves
- What the CE/BA is doing to investigate, mitigate, and prevent recurrence
- Contact information

---

## HITECH Act

The 2009 HITECH Act dramatically strengthened HIPAA. Key impacts:

- **Made BAs directly liable** for HIPAA Security Rule and parts of Privacy Rule (previously only the CE was directly liable)
- **Tiered penalty structure** with civil penalties up to $2M per violation per year
- **Breach Notification Rule** (above) was created by HITECH
- **EHR Meaningful Use / Promoting Interoperability** programs — incentives for EHR adoption
- **2021 amendment ("Cures Act safe harbor"):** OCR must consider an entity's "recognized security practices" from the previous 12 months when assessing fines — so implementing NIST CSF/HITRUST/CIS can mitigate penalties
- **Information Blocking rules** (ONC) — providers and developers can't unreasonably block access to electronic health information; civil penalties up to $1M per violation

---

## NIST Cybersecurity Framework 2.0

**Citation:** [NIST CSF 2.0](https://www.nist.gov/cyberframework), published February 2024
**Type:** Voluntary framework (often contractually required)
**Best for:** Universal baseline; common language across business, IT, security, leadership

### The six Functions

CSF 2.0 added **Govern** to the original five (Identify, Protect, Detect, Respond, Recover):

| Function | Plain English | What you do |
|---|---|---|
| **GOVERN (GV)** | "Who's in charge and why does this matter?" | Policies, risk strategy, roles, supply chain, oversight |
| **IDENTIFY (ID)** | "What do we have?" | Asset inventory, business environment, risk assessment |
| **PROTECT (PR)** | "How do we keep it safe?" | Access control, awareness, data security, IT processes |
| **DETECT (DE)** | "How do we know when something's wrong?" | Logging, monitoring, detection processes |
| **RESPOND (RS)** | "What do we do about it?" | Response plan, comms, analysis, mitigation |
| **RECOVER (RC)** | "How do we get back to normal?" | Recovery plan, improvements, communications |

### Tiers (maturity, NOT compliance levels)

- **Tier 1 — Partial**: Ad hoc, reactive
- **Tier 2 — Risk Informed**: Risk-aware processes exist but inconsistent
- **Tier 3 — Repeatable**: Formal policies, regular updates
- **Tier 4 — Adaptive**: Continuous improvement, threat-informed

Most SMBs operate at Tier 1–2. Tier 3 is a reasonable target for a midmarket org. Tier 4 is appropriate for critical infrastructure and large enterprises.

### Profiles (the actual planning artifact)

A **Profile** is your custom selection of CSF Subcategories tailored to your business. Standard practice:

1. Build a **Current Profile** — where you are today
2. Build a **Target Profile** — where you need to be
3. Gap analysis → roadmap
4. Re-baseline annually

Templates: [NIST CSF 2.0 Profile templates](https://www.nist.gov/cyberframework/profiles)

### Why CSF is everywhere

Even when not formally required, CSF is the cheapest path to defensible security because:

- Maps cleanly to HIPAA, PCI DSS, SOC 2, ISO 27001, CIS Controls
- Free, no licensing
- Recognized by HHS OCR as a "Recognized Security Practice" under the 2021 HITECH amendment (reduces penalties)
- Cyber insurers increasingly require CSF alignment

---

## NIST SP 800-53

**Citation:** [NIST SP 800-53 Rev. 5](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)
**Type:** Mandatory for federal agencies; widely adopted as gold-standard control catalog
**Best for:** Detailed control specifications when CSF is too high-level

### Structure

- **20 control families** (Access Control, Audit & Accountability, Configuration Management, etc.)
- **~1,000+ controls and control enhancements**
- **Three baselines:** Low, Moderate, High impact (per [FIPS 199](https://csrc.nist.gov/publications/detail/fips/199/final))

### When you'll see it

- Federal contracts (FISMA, FedRAMP)
- State/local governments that adopted it
- Healthcare orgs that chose 800-53 over more abstract frameworks
- HITRUST and other certifications map to it
- As the "deep dictionary" when CSF subcategories need elaboration

---

## NIST SP 800-171 & CMMC

**Citation:** [NIST SP 800-171 Rev. 3](https://csrc.nist.gov/publications/detail/sp/800-171/rev-3/final) (May 2024)
**Scope:** Controlled Unclassified Information (CUI) in non-federal systems
**Best for:** DoD contractors and subcontractors

### Quick facts

- **110 controls** across 14 families (Rev. 3 reduced from prior; reorganized)
- Required by [DFARS clause 252.204-7012](https://www.acquisition.gov/dfars/252.204-7012) for any DoD contractor handling CUI
- **CMMC 2.0** is the certification scheme on top of 800-171:
  - **Level 1**: Basic (17 controls, FCI only) — annual self-assessment
  - **Level 2**: Advanced (110 controls, CUI) — third-party assessment (C3PAO) every 3 years
  - **Level 3**: Expert (110 controls + subset of 800-172) — government-led assessment
- CMMC final rule published October 2024; implementation phased through 2028

### If you're considering CMMC

- Hire a [Registered Practitioner Organization (RPO)](https://cyberab.org/) or experienced consultant
- Budget 6–12 months and $50k–$500k+ depending on size and current state
- Start with [DoD's Cyber AB Marketplace](https://cyberab.org/)

---

## SOC 2

**Citation:** AICPA Trust Services Criteria
**Type:** Voluntary, customer-demanded
**Best for:** SaaS / service providers selling to enterprises

### Trust Services Criteria

You pick which of the five categories apply (Security is mandatory):

1. **Security** — protection against unauthorized access (Common Criteria — required)
2. **Availability** — system uptime
3. **Processing Integrity** — system processes complete, valid, accurate, timely
4. **Confidentiality** — protection of confidential info
5. **Privacy** — collection, use, retention, disclosure, disposal of personal info

### Type I vs. Type II

- **Type I**: Point-in-time assessment of design. Faster, cheaper. Often a stepping stone.
- **Type II**: Operational effectiveness over a period (usually 6–12 months). What enterprise customers actually want.

### Typical timeline & cost

- **Readiness assessment + remediation**: 3–6 months
- **Type I audit**: 4–8 weeks
- **Type II observation period**: 6–12 months
- **Cost**: $20k–$100k+ for the audit alone

### The hardest controls for first-timers

- **Vendor management** — list every vendor, classify by risk, get SOC 2 reports from critical ones
- **Change management** — every code/infra change tracked, approved, tested
- **Access reviews** — quarterly minimum, documented, with evidence
- **Incident response** — must have a documented process AND test it
- **Background checks** — for employees with access to customer data

---

## PCI DSS

**Citation:** [PCI DSS v4.0.1](https://www.pcisecuritystandards.org/document_library/) (June 2024)
**Scope:** Anyone who stores, processes, or transmits cardholder data
**Best for:** Merchants, payment processors, any business taking credit cards

### Levels (Visa example — others similar)

| Level | Annual transactions | Validation |
|---|---|---|
| 1 | 6M+ | Annual on-site audit by QSA |
| 2 | 1M–6M | Annual SAQ + ASV scans |
| 3 | 20k–1M e-com | Annual SAQ + ASV scans |
| 4 | <20k e-com or <1M total | Annual SAQ + ASV scans |

### The 12 Requirements (v4.0.1)

1. Install and maintain network security controls
2. Apply secure configurations to all system components
3. Protect stored account data
4. Protect cardholder data with strong cryptography during transmission over open public networks
5. Protect all systems and networks from malicious software
6. Develop and maintain secure systems and software
7. Restrict access to system components and cardholder data by business need to know
8. Identify users and authenticate access to system components
9. Restrict physical access to cardholder data
10. Log and monitor all access to system components and cardholder data
11. Test security of systems and networks regularly
12. Support information security with organizational policies and programs

### v4.0.1 changes you should know

- **MFA required for ALL access to CDE** (not just remote/admin)
- **Custom approach** option — define your own controls if they meet the objective (harder to validate)
- **Targeted Risk Analysis** — required for any "periodic" frequency you choose
- **Phishing protections** — required (was guidance before)
- **Best to use a payment processor that "outsources" most of PCI scope** (Stripe, Square, etc.) — radically reduces your SAQ burden

---

## GDPR

**Citation:** EU [Regulation 2016/679](https://eur-lex.europa.eu/eli/reg/2016/679/oj)
**Scope:** Any organization processing personal data of EU residents (regardless of where the org is)
**Best for:** Anyone with EU users, employees, or customers

### Six lawful bases for processing

You need ONE of these for every processing activity:

1. **Consent** (must be freely given, specific, informed, unambiguous)
2. **Contract** (necessary for a contract with the data subject)
3. **Legal obligation** (required by law)
4. **Vital interests** (life-or-death)
5. **Public task** (official authority)
6. **Legitimate interests** (balance test against data subject's rights)

### Data subject rights

- Right of access
- Right to rectification
- Right to erasure ("right to be forgotten")
- Right to restriction
- Right to data portability
- Right to object
- Rights related to automated decision-making

You must respond within **30 days** (extendable to 60 with reason).

### Breach notification

- **To supervisory authority**: within **72 hours** of becoming aware
- **To individuals**: "without undue delay" if high risk to rights

### What trips US companies up

- **Standard Contractual Clauses (SCCs)** — required for transferring EU personal data to non-adequacy countries (US among them until/unless DPF replaces this)
- **Data Protection Officer (DPO)** — required if you process special categories at scale or large-scale systematic monitoring
- **Records of Processing Activities (Article 30)** — required for orgs over 250 employees, or smaller if processing is regular/high-risk
- **Data Protection Impact Assessment (DPIA)** — required for high-risk processing (biometrics, large-scale special categories, systematic monitoring)

---

## CCPA / CPRA

**Citation:** California Civil Code §§ 1798.100 et seq. (as amended by CPRA, enforced by CPPA)
**Scope:** Businesses meeting any of: $25M+ revenue, 100k+ CA residents' data, 50%+ revenue from selling/sharing personal info
**Best for:** Any business with California customers

### Consumer rights

- Right to know
- Right to delete
- Right to correct (CPRA addition)
- Right to opt-out of sale/share
- Right to limit use of sensitive personal info (CPRA addition)
- Right to non-discrimination for exercising rights

### Operational requirements

- "Do Not Sell or Share My Personal Information" link on homepage
- Privacy policy updated at least every 12 months
- Honor Global Privacy Control (GPC) signal as opt-out
- Service provider agreements (similar function to BAAs)
- 12-month look-back on data requests
- Verification process for consumer requests

### State expansion

20+ states have passed similar laws (Virginia VCDPA, Colorado CPA, Connecticut, Utah, Texas, Oregon, Montana, Iowa, Tennessee, Indiana, Delaware, New Jersey, New Hampshire, Kentucky, Maryland, Minnesota, Rhode Island, more in 2026). Most piggyback on CCPA structure. A single program designed for CCPA usually satisfies most others.

---

## State Breach Notification Laws

All 50 states + DC + PR + VI have breach notification laws. Common elements:

- Notify affected residents
- Notify state AG (in most states)
- Notify consumer reporting agencies (if 500–1,000+ residents affected, varies)
- Specific timelines (most 30–90 days; some "without unreasonable delay")
- Encryption safe harbor (in most states)

**Resource:** [NCSL state breach notification law summary](https://www.ncsl.org/technology-and-communication/security-breach-notification-laws)

For multi-state breaches: build a notification matrix early. A single breach can require coordinated notifications across dozens of jurisdictions. Specialized breach-notification counsel and services (Mullen Coughlin, BakerHostetler, etc.) exist for this.

---

## Cross-Framework Control Mappings

These are common controls everyone implements. Pick once, document once, satisfy many.

| Control | HIPAA | NIST CSF 2.0 | NIST 800-53 | SOC 2 | PCI DSS | GDPR |
|---|---|---|---|---|---|---|
| **MFA** | §164.312(d) | PR.AA-03 | IA-2 | CC6.1 | 8.4–8.5 | Art. 32 |
| **Encryption at rest** | §164.312(a)(2)(iv) | PR.DS-01 | SC-28 | CC6.7 | 3.5–3.7 | Art. 32 |
| **Encryption in transit** | §164.312(e)(2)(ii) | PR.DS-02 | SC-8 | CC6.7 | 4.1–4.2 | Art. 32 |
| **Access reviews** | §164.308(a)(4) | PR.AA-05 | AC-2 | CC6.2 | 7.2 | Art. 32 |
| **Logging & monitoring** | §164.312(b) | DE.CM-01/03 | AU-2, AU-12 | CC7.2 | 10.2 | Art. 32 |
| **Incident response** | §164.308(a)(6) | RS.MA-01 | IR-4 | CC7.4 | 12.10 | Art. 33–34 |
| **Risk assessment** | §164.308(a)(1)(ii)(A) | ID.RA-01 | RA-3 | CC3.2 | 12.3.1 | Art. 35 |
| **Vendor management** | §164.308(b) | GV.SC-01..10 | SA-9 | CC9.2 | 12.8 | Art. 28 |
| **Security awareness training** | §164.308(a)(5) | PR.AT-01 | AT-2 | CC1.4 | 12.6 | Art. 39 |
| **Backups & recovery** | §164.308(a)(7) | RC.RP-01 | CP-9 | A1.2 | (12.10.5) | Art. 32 |
| **Asset inventory** | §164.310(d) | ID.AM-01/02 | CM-8 | CC6.1 | 9.5, 12.5 | (implicit) |
| **Patch management** | §164.308(a)(5) | PR.PS-02 | SI-2 | CC6.8 | 6.3 | Art. 32 |

---

## Annual Compliance Calendar

A sample annual cadence — tune to your environment.

### Monthly

- Vulnerability scans (internal)
- Patch review and deployment
- Access log review
- New-hire onboarding (training, access provisioning, BAA if applicable)
- Off-boarding (access removal, equipment return) within agreed SLA (HIPAA expects "as soon as possible")

### Quarterly

- User access reviews
- Vulnerability scans (external authenticated)
- PCI ASV scan (if applicable — required quarterly)
- Vendor risk review for high-risk vendors
- Tabletop exercise (rotate scenarios)
- Phishing simulation

### Semi-Annual

- Disaster recovery test
- Backup restoration test
- Policy review (split policies across the year so something is being reviewed each month)

### Annual

- HIPAA Risk Analysis update
- NIST CSF Profile re-baseline
- SOC 2 Type II audit (if applicable)
- PCI SAQ or ROC (if applicable)
- Penetration test
- Business Impact Analysis
- Insurance renewal (and policy re-read)
- Full security awareness training for all workforce
- Code of conduct / acknowledgment sign-off
- Business continuity plan review
- Asset inventory reconciliation

### Event-driven

- Breach notification clock starts at discovery (not at confirmation)
- BAA before any vendor PHI access
- DPIA before high-risk processing (GDPR)
- Update Risk Analysis after material change (M&A, new EHR, new line of business)

---

## Audit Prep Checklists

### Before an OCR audit (HIPAA)

- [ ] Risk Analysis current (last 12 months) and signed
- [ ] Risk Management Plan with remediation status
- [ ] All required policies in writing (security, privacy, breach notification, sanctions)
- [ ] Workforce training records (current year + previous 6 years retained)
- [ ] All BAAs current and on file
- [ ] Audit logs available and reviewed
- [ ] Breach notification log (even if no breaches: documented review)
- [ ] Designated Privacy Officer and Security Officer (can be same person)
- [ ] Notice of Privacy Practices current
- [ ] Access logs for the auditor's sample of patients/records
- [ ] Sanctions actually issued for violations (a "zero sanctions" history with known incidents is a finding)

### Before a SOC 2 audit

- [ ] Trust Services Criteria selected and documented
- [ ] System Description drafted
- [ ] All controls mapped and evidence collected
- [ ] Access reviews completed for the audit period
- [ ] Change tickets for every production change
- [ ] Vendor SOC 2 reports for critical vendors
- [ ] Risk assessment completed
- [ ] Penetration test report
- [ ] Incident log with response evidence
- [ ] Training completion records

### Before a PCI assessment

- [ ] Cardholder Data Environment (CDE) scoped and documented
- [ ] Network diagrams accurate and current
- [ ] Data flow diagrams for cardholder data
- [ ] ASV scans clean for the last 4 quarters
- [ ] Penetration test (internal + external) current
- [ ] All twelve requirements mapped to evidence
- [ ] Compensating controls documented (if any)
- [ ] Vendor PCI compliance status verified

### Before any audit (universal)

- [ ] Audit liaison appointed
- [ ] Document repository organized (one folder per control)
- [ ] Evidence is **dated** — auditors reject "live" screenshots; need historical evidence
- [ ] Leadership briefed
- [ ] Auditor scope confirmed in writing
- [ ] War room / dedicated comms channel set up
- [ ] Daily debriefs scheduled with auditor

---

## Common Findings to Avoid

These show up in nearly every audit. Fix them before someone tells you to.

### HIPAA
- **Incomplete Risk Analysis** (#1 OCR finding for a decade running)
- **Missing or stale BAAs** with vendors
- **No documented sanctions** despite known violations
- **Right of Access timeline violations** (current OCR initiative)
- **Lack of audit log review** (collecting logs ≠ reviewing them)

### SOC 2
- Access reviews not completed or not evidenced
- Terminated employees retaining access past the audit cutoff
- Change management exceptions ("emergency change" without ticket)
- Vendor SOC 2 reports older than 12 months
- Inadequate evidence of training completion

### PCI DSS
- Default vendor passwords still in place
- Storage of full PAN, SAD (sensitive authentication data), or CVV
- Quarterly ASV scans failing
- Cardholder data found outside the scoped CDE (scope creep)
- MFA gaps under v4.0.1

### NIST CSF
- "Implemented" controls without evidence
- Profile not updated when business changes
- No clear ownership for Govern function (CSF 2.0 specific)

### GDPR
- Cookie consent banner that doesn't actually block cookies until consent
- No DPIA for AI/automated decisioning
- No Article 30 records of processing
- Data transfers without SCCs

---

## Tools & Templates

From the [main tools list](../README.md):

**Compliance Scanning**
- [Prowler](https://github.com/prowler-cloud/prowler) — AWS/Azure/GCP/K8s compliance checks (CIS, HIPAA, PCI, ISO, etc.)
- [ScoutSuite](https://github.com/nccgroup/ScoutSuite) — Multi-cloud security auditing
- [OpenSCAP](https://github.com/OpenSCAP/openscap) — NIST-validated config compliance scanner
- [CIS-CAT Lite](https://www.cisecurity.org/cybersecurity-tools/cis-cat-lite) — CIS Benchmark assessments
- [Lynis](https://github.com/CISOfy/lynis) — Unix system audits

**Compliance-as-Code**
- [Chef InSpec](https://github.com/inspec/inspec) — Compliance as code
- [Open Policy Agent](https://github.com/open-policy-agent/opa) — Policy enforcement engine
- [Steampipe](https://github.com/turbot/steampipe) — Query cloud APIs with SQL

**Risk Assessment**
- [HHS SRA Tool](https://www.healthit.gov/topic/privacy-security-and-hipaa/security-risk-assessment-tool) — Free HIPAA Risk Analysis tool
- [NIST CSF 2.0 Reference Tool](https://csrc.nist.gov/Projects/cybersecurity-framework/csf-tools) — Profile templates and informative references
- [OpenFAIR](https://www.fairinstitute.org/) — Quantitative risk analysis methodology

**Documentation**
- [SecureFrame open templates](https://secureframe.com/) — free policy templates
- [Vanta open templates](https://github.com/VantaInc) — reference policies
- [SOC 2 starter policy kit (Trail of Bits)](https://github.com/trailofbits/publications) — community policies

---

## References

- [HHS — HIPAA for Professionals](https://www.hhs.gov/hipaa/for-professionals/index.html)
- [HHS — HIPAA Audit Protocol](https://www.hhs.gov/hipaa/for-professionals/compliance-enforcement/audit/protocol/index.html)
- [HHS — Recognized Security Practices](https://www.hhs.gov/sites/default/files/recognized-security-practices-video-presentation-transcript.pdf)
- [NIST CSF 2.0](https://www.nist.gov/cyberframework)
- [NIST SP 800-66r2 — HIPAA Security Rule Implementation Guide](https://csrc.nist.gov/publications/detail/sp/800-66/rev-2/final)
- [NIST SP 800-53 Rev. 5](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)
- [NIST SP 800-171 Rev. 3](https://csrc.nist.gov/publications/detail/sp/800-171/rev-3/final)
- [CMMC Program](https://dodcio.defense.gov/CMMC/)
- [AICPA Trust Services Criteria](https://www.aicpa-cima.com/topic/audit-assurance/audit-and-assurance-greater-than-soc-2)
- [PCI Security Standards Council](https://www.pcisecuritystandards.org/)
- [EU GDPR — Full text](https://gdpr-info.eu/)
- [California Privacy Protection Agency](https://cppa.ca.gov/)
- [OCR Resolution Agreements & Civil Money Penalties](https://www.hhs.gov/hipaa/for-professionals/compliance-enforcement/agreements/index.html)
- [HHS Breach Portal ("Wall of Shame")](https://ocrportal.hhs.gov/ocr/breach/breach_report.jsf)

---

**Last reviewed:** 2026-05-12 · **Maintained by:** [@jshepjr](https://github.com/jshepjr) · Part of [mvp-sudojohnny-tools](../README.md)

**Reminder:** This runbook is informational. Compliance is fact-specific. Engage qualified counsel and certified assessors for binding decisions.
