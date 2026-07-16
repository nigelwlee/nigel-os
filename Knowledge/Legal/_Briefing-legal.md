# Legal Briefing

> Last synthesized: 2026-07-16
> Insight count: 11 (refreshed: 1 updated)
> Jurisdiction focus: Australia (primary), US (secondary for tech/fundraising)

> **Disclaimer:** This is a knowledge base for orientation and first-principles thinking, not legal advice. Always engage a qualified lawyer for material decisions.

---

## Core Thesis

Most legal risk in startups comes from not having the basics in place, not from sophisticated adversarial situations. Get the fundamentals right early (entity, IP assignment, employment, terms of service) and the vast majority of legal exposure goes away. Legal is a cost of doing business — optimise for speed and clarity, not perfection.

---

## Key Frameworks

**IRAC (Issue → Rule → Application → Conclusion)**
The structure of all legal reasoning. Issue: what is the legal question? Rule: what law or principle applies? Application: how does the rule apply to the facts? Conclusion: what is the result? Use for: thinking through any legal question, structuring a memo, communicating with lawyers.

**Risk Tiering**
- Tier 1 (fix now): regulatory violations, IP not owned, founders without equity agreements. These can kill the company.
- Tier 2 (fix before fundraise): clean cap table, IP assignments, employment contracts, NDAs with contractors.
- Tier 3 (fix when you have scale): full privacy policy review, tax structuring, international compliance.

**The Paper Trail Principle**
If it's not in writing, it didn't happen. Verbal agreements, handshake deals, and "we had an understanding" are expensive mistakes. Every material decision, agreement, or commitment should be documented.

**Privacy by Default**
Collect the minimum data you need. Don't store what you don't need. Have a clear retention and deletion policy. This is both good practice and increasingly a regulatory requirement (GDPR, Australian Privacy Act, CCPA). The cheapest compliance strategy is not collecting data in the first place.

---

## Startup Legal Foundations (Australia)

**Entity Structure**
- Pty Ltd is the standard operating entity in Australia. Low cost, limited liability, equity-friendly.
- Trust structures (unit trusts, discretionary trusts) are common for tax planning but add complexity — generally avoid for operating companies until you have revenue and an accountant.
- If raising VC (especially US VC): a Delaware C-Corp or a Cayman holdco may be expected. Structure the Australian entity to flip or hold the IP accordingly.

**IP Assignment**
Every founder, employee, and contractor must sign an IP assignment agreement before doing any work. Without this, IP they create may belong to them, not the company. This is the single most common legal landmine in early-stage startups. Fix before anything else.

**Equity & Vesting**
Standard founder vesting: 4-year vest, 1-year cliff. No exceptions without deliberate reason. Vesting protects the remaining founders if one leaves early. A founder with unvested equity who leaves early is a cap table problem that follows the company forever.

**Employment vs. Contractor**
Australia has strict rules on employee vs. contractor classification. Getting this wrong creates tax liability (PAYG, super), unfair dismissal risk, and entitlement back-pay. Key test: is the person integrated into the business, or running their own business? When in doubt, employ.

**Superannuation (Australia)**
Mandatory 12% superannuation on eligible earnings (rising to 12.5% from 1 July 2026). Applies to employees, some contractors. Non-payment triggers ATO penalties. From 1 July 2026, "Payday Super" requires contributions within 7 business days of each pay cycle — quarterly batching ends. See [[Knowledge/People/_Briefing-people|People Briefing]] for contractor compliance details.

---

## Active Insights

**Shareholders' Agreement before you need it.** The time to write a SHA is before there's a dispute. It should cover: decision-making thresholds, drag-along and tag-along rights, pre-emptive rights, what happens if a founder leaves. Without one, you're governed by the Corporations Act defaults, which may not be what anyone wants.

**Your Terms of Service are your contract with users.** A weak ToS exposes you to IP claims, consumer law issues, and unlimited liability. The key provisions: IP ownership of user content, limitation of liability, dispute resolution, governing law. Get this reviewed before launch.

**Privacy policy is a legal document, not a formality.** Under the Australian Privacy Act, if you collect personal information, you must have a compliant Privacy Policy. The consequences of non-compliance include OAIC investigations and reputational damage. AI products have heightened scrutiny here.

**SAFE notes are not yet standard in Australia.** Australian investors often prefer convertible notes or direct equity. Know the instrument before negotiating. SAFE notes are used but less common than in the US — legal counsel familiar with local market is essential.

**Domain names and trademarks are different.** Owning a .com.au does not give you trademark rights. Register your brand as a trademark in your primary markets (Australia: IP Australia, US: USPTO) before you're big enough to be worth copying.

**Children's Online Privacy Code consultation closed — final code expected by 10 December 2026, with mandatory PIAs.** The OAIC exposure draft applies a "best interests of the child" standard to services likely accessed by children — including educational apps. Strict data minimisation, parental consent for under-15s, children's right to deletion. Critically, the Code will require mandatory Privacy Impact Assessments and a PIA register for any service "likely to be accessed by children" — applies broadly, not just child-targeted services. If an AI product has Australian users and no effective age gate, the PIA obligation will likely apply. [[Projects/MY-DIDIT/_Briefing-my-didit|Did·It]] must be designed for compliance before this goes live. Apple's September 2026 App Store rule requires all apps to declare social media capabilities — any feed-like sharing triggers a 13+ age floor.

**Automated decision-making transparency obligations take effect 10 December 2026.** Any APP entity using personal information in automated or semi-automated decision-making with significant individual impact must describe the data used and decision types in its privacy policy. Broadly captures AI-enabled systems. Relevant to any project using AI for personalisation or recommendations (e.g., [[Projects/MY-ANIM/_Briefing-my-anim|Anima Pet]]'s LLM-powered interactions).

**Australia chose voluntary AI guidance over mandatory regulation — but enforcement is real.** The December 2025 National AI Plan confirmed reliance on existing laws + sector regulators + voluntary AI Safety Institute guidance, not a standalone AI Act. However, the OAIC launched its first-ever compliance sweep in January 2026 (~60 organisations). The regime is "soft regulation, hard enforcement." Don't mistake the absence of an AI Act for absence of liability.

**The CGT reform bill is law — IBCC startup carve-out consultation closed 10 July, legislation pending.** The 50% CGT discount is replaced by CPI indexation + 30% minimum tax from 1 July 2027. The Innovative Business CGT Concession (IBCC) preserves 50% discount for companies under $50M turnover, under 10 years old, with 5-year minimum hold — critically covers founders and ESS participants, not just external investors. A lifetime cap on the concession will apply (quantum TBD in legislation). Biotech/medtech may get extended 15-year age limit. Implementation via subsequent tax reform tranche — timing dependent on parliamentary schedule. Small business CGT threshold raised from $2M to $10M. Equity structuring decisions (issuing shares, vesting, SAFE conversions) should factor in the carve-out criteria. See [[Knowledge/Finance/_Briefing-finance|Finance Briefing]].

**The Digital Assets Framework Act received Royal Assent (8 April 2026) — crypto platforms now need AFSLs by April 2027.** Two new regulated product categories: Digital Asset Platforms (DAPs) and Tokenised Custody Platforms (TCPs), subject to client asset safeguarding, disclosure, dispute resolution, and compensation obligations. ASIC's class no-action position (INFO 225) expires June 2026. Directly relevant to [[Projects/SD-OPAL/_Briefing-sd-opal|SD-OPAL]] and any iGaming clients with crypto payment rails — the licensing clock is ticking.

**US children's AI safety regulation is accelerating — New York banned AI companion chatbots for minors (June 2026), House KIDS Act consolidates 12+ bills.** New York S9051B passed unanimously, prohibiting AI "companion" chatbots for under-18s (fines up to $25K/violation). The House KIDS Act (June 23) consolidates KOSA + COPPA 2.0 into one package. The amended COPPA Rule (effective April 22, 2026) now requires even solo operators to maintain written data-retention and information-security policies — not just parental consent. Operators must document retention timeframes, designate a security-policy owner, and delete data when its purpose expires. Civil penalties up to $53,088 per violation per child per day. If [[Projects/MY-ANIM/_Briefing-my-anim|Anima Pet]] or [[Projects/MY-DIDIT/_Briefing-my-didit|Did·It]] add AI-powered interactions and have US users, build compliance hooks into the architecture now.

**OAIC tracking pixel determinations (June 11) establish that analytics collecting health/sensitive data = privacy breach.** Medmate and Monash IVF found to have breached the Privacy Act by using TikTok and Meta tracking pixels on health websites — transmitting sensitive information without consent. Novel application: any product using analytics SDKs that collect data touching sensitive categories (health, children, financial) needs explicit consent architecture.

**Sham contracting enforcement intensified — the "real substance" test under the Closing Loopholes Act is fully operational.** Courts now look at the practical reality of the relationship, not the contract label. Per-pay-period penalties can stack to six figures quickly. For anyone engaging contractors: actually assess the arrangement before labelling it, and document that assessment. See [[Knowledge/People/_Briefing-people|People Briefing]].

**Trump's June 2 AI Executive Order locks in "ship first, no permission needed" at federal level.** Explicitly prohibits mandatory federal licensing or pre-clearance for AI model deployment, while creating a voluntary pre-release review framework. A DOJ task force will challenge state AI laws that burden interstate commerce (child-safety state laws are exempt from preemption). 109 state AI laws enacted, but the federal posture is clear: no gatekeeping for indie builders. This breathing room is administration-dependent.

**Bipartisan AI Labeling Act (S.4915) signals content provenance labeling converging across jurisdictions.** Introduced June 25, would require all generative AI providers to attach visible and machine-readable provenance labels to AI-generated images, audio, and video, plus disclose chatbot identity. Aligns with EU AI Act Article 50 transparency obligations (see [[Knowledge/Creative/_Briefing-creative|Creative Briefing]]). Solo builders shipping generative AI tools should plan for labeling infrastructure now rather than retrofitting later.

---

## Open Questions / Active Debates

- What is the right entity structure if I want to raise from Australian and US investors?
- When does a privacy policy need to be reviewed by counsel vs. templated?
- What are the AI-specific legal risks (copyright training data, AI-generated output ownership)?
- When does a contractor relationship tip over into employment under Australian law?

---

## Reading / Watching Queue

- Australian Privacy Act 1988 (summary via OAIC website)
- ASIC guidance on equity crowdfunding and SAFE-equivalent instruments
- IP Australia trademark search and registration process
- *Venture Deals* — Brad Feld & Jason Mendelson (US-focused but foundational for VC mechanics)
- Slater and Gordon or Lander & Rogers startup legal guides (AU-specific)

---

> See also: [[Knowledge/Legal/Frameworks|Legal Frameworks]] | [[Knowledge/_Map-knowledge|Knowledge]] | [[Projects/MY-DIDIT/_Briefing-my-didit|MY-DIDIT]] | [[Projects/MY-ANIM/_Briefing-my-anim|MY-ANIM]] | [[SOUL]]
