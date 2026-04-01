# Legal Frameworks

Mental models and structured tools for legal reasoning. Reference when thinking through risk, contracts, compliance, or corporate structure.

> Jurisdiction focus: Australia (primary), US (secondary for fundraising and tech).
> Not legal advice. Use for orientation and first-principles thinking.

---

## Legal Reasoning

**IRAC**
Issue → Rule → Application → Conclusion. The universal structure for legal analysis.
- Issue: What is the specific legal question?
- Rule: What law, statute, contract clause, or principle governs it?
- Application: How does the rule apply to these specific facts?
- Conclusion: What outcome does this reasoning produce?
Use when: thinking through any legal question, briefing a lawyer, drafting a memo.

**The Reasonable Person Standard**
Many legal tests ask what a "reasonable person" would do in the circumstances. When assessing risk: would a reasonable person think this was a problem? Would a reasonable business do this? This test governs negligence, contract interpretation, and many other areas.

**Substance Over Form**
Courts look at the economic reality of an arrangement, not just its label. Calling someone a contractor doesn't make them one. Calling something a loan doesn't make it one. Structure transactions for what they are, not what you want them to be.

---

## Corporate Structure

**Pty Ltd (Australia)**
- Proprietary Limited company — the standard structure for operating businesses.
- Limited liability for shareholders.
- Can have share classes (ordinary, preference).
- Governed by the Corporations Act 2001.
- Key documents: Constitution, Shareholders' Agreement, Share Register.

**Cap Table Management**
Record of who owns what, including: ordinary shares, preference shares, options, convertible notes/SAFEs. Keep this clean from day one. Messy cap tables are a due diligence red flag and slow fundraising.

**Delaware C-Corp (US)**
Required (or strongly preferred) by most US VC funds. If you plan to raise US institutional capital: consider incorporating in Delaware with an Australian subsidiary, or structuring for a future flip. Do this before the fundraise, not during.

---

## Contracts

**Key Contract Provisions (must negotiate)**
- Limitation of Liability: caps your exposure to direct damages or a multiple of fees paid. Always include.
- Indemnification: who covers what losses. Read these carefully — broad indemnities can exceed the contract value.
- IP Ownership: who owns what is created under the contract. Especially critical for development contracts.
- Termination for Convenience: can either party exit without cause? What is the notice period?
- Governing Law & Jurisdiction: which country/state's law applies, and where disputes are resolved.

**NDA (Non-Disclosure Agreement)**
Use for: conversations with potential partners, employees before offer, contractors before seeing product. Key terms: definition of confidential information, exclusions (publicly known info, independently developed), duration, permitted disclosure. Mutual vs. one-way depending on context.

**MSA + SOW Structure**
Master Services Agreement (MSA): covers the general terms of the relationship. Statement of Work (SOW): covers the specific project, deliverables, timeline, fees. This structure allows you to do multiple projects under one set of legal terms. Preferred for ongoing vendor relationships.

---

## IP

**The Four Types of IP**
- Copyright: protects original creative works (code, writing, design). Automatic — no registration required. In Australia, owned by the creator unless assigned.
- Trademark: protects brand names, logos, slogans in connection with specific goods/services. Registration gives stronger protection. Apply early.
- Patent: protects inventions. Expensive, long process, rarely relevant to software startups in Australia.
- Trade Secret: protects confidential information (algorithms, customer lists, processes). Requires active confidentiality measures (NDAs, access controls).

**Work for Hire / IP Assignment**
Without a written IP assignment: code written by a contractor belongs to the contractor, not you. Design created by a freelancer belongs to the freelancer. Fix this before any significant work is done. The IP assignment clause should state: all work product, in all forms, is assigned to the company upon creation.

---

## Employment (Australia)

**Fair Work Act 2009**
Governs employment in Australia. Key provisions: National Employment Standards (NES — 10 minimum entitlements), Modern Awards (industry-specific minimum pay and conditions), Unfair Dismissal (employees with 12 months+ service have protections).

**Contractor vs Employee Test (Multi-Factor)**
No single test — courts look at the totality. Factors pointing to employment: works exclusively for you, uses your tools, integrated into your operations, no ability to subcontract, paid by time not outcome. Risk: if you get this wrong, you owe back-pay, super, and entitlements.

**Superannuation (2026)**
Rate: 11.5% of Ordinary Time Earnings. Due quarterly (or more frequently on modern payroll systems). Applies to employees and some contractors (if they work solely for you). Paid to the employee's nominated super fund. ATO enforces this aggressively.

---

## Privacy & Data (Australia)

**Australian Privacy Act 1988 (amended)**
Applies to businesses with >$3M annual turnover (and some others). 13 Australian Privacy Principles (APPs) govern collection, use, disclosure, storage, and access to personal information. Key obligations: have a Privacy Policy, only collect what you need, don't disclose without consent, secure the data.

**Notifiable Data Breaches (NDB) Scheme**
If you suffer a data breach that is likely to cause serious harm to affected individuals, you must notify both the OAIC and the affected individuals. Threshold: "likely serious harm." Timeline: as soon as practicable after becoming aware.

**AI and Privacy**
Training AI models on personal data has heightened privacy implications. Key risks: using customer data to train models without consent, generating output that re-identifies individuals, retaining data longer than needed. Assess privacy impact before any AI feature that touches personal data.
