# Legal Briefing

> Last synthesized: 2026-04-16
> Insight count: 3
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
Mandatory 11.5% superannuation on eligible earnings (2026). Applies to employees, some contractors. Non-payment triggers ATO penalties. Set up payroll correctly from the first paid hire.

---

## Active Insights

**Shareholders' Agreement before you need it.** The time to write a SHA is before there's a dispute. It should cover: decision-making thresholds, drag-along and tag-along rights, pre-emptive rights, what happens if a founder leaves. Without one, you're governed by the Corporations Act defaults, which may not be what anyone wants.

**Your Terms of Service are your contract with users.** A weak ToS exposes you to IP claims, consumer law issues, and unlimited liability. The key provisions: IP ownership of user content, limitation of liability, dispute resolution, governing law. Get this reviewed before launch.

**Privacy policy is a legal document, not a formality.** Under the Australian Privacy Act, if you collect personal information, you must have a compliant Privacy Policy. The consequences of non-compliance include OAIC investigations and reputational damage. AI products have heightened scrutiny here.

**SAFE notes are not yet standard in Australia.** Australian investors often prefer convertible notes or direct equity. Know the instrument before negotiating. SAFE notes are used but less common than in the US — legal counsel familiar with local market is essential.

**Domain names and trademarks are different.** Owning a .com.au does not give you trademark rights. Register your brand as a trademark in your primary markets (Australia: IP Australia, US: USPTO) before you're big enough to be worth copying.

**Children's Online Privacy Code is coming — directly relevant to [[Projects/MY-DIDIT/_Briefing-my-didit|Did·It]].** The OAIC published an exposure draft (April 2026) applying a "best interests of the child" standard to services likely accessed by children — including educational apps. Strict data minimisation, explicit consent for marketing, children's right to deletion. Consultation closes 5 June 2026; law expected December 2026. MY-DIDIT (toddler games) must be designed for compliance before this goes live.

**Automated decision-making transparency obligations take effect 10 December 2026.** Any APP entity using personal information in automated or semi-automated decision-making with significant individual impact must describe the data used and decision types in its privacy policy. Broadly captures AI-enabled systems. Relevant to any project using AI for personalisation or recommendations (e.g., [[Projects/MY-ANIM/_Briefing-my-anim|Anima Pet]]'s LLM-powered interactions).

**Australia chose voluntary AI guidance over mandatory regulation — but enforcement is real.** The December 2025 National AI Plan confirmed reliance on existing laws + sector regulators + voluntary AI Safety Institute guidance, not a standalone AI Act. However, the OAIC launched its first-ever compliance sweep in January 2026 (~60 organisations). The regime is "soft regulation, hard enforcement." Don't mistake the absence of an AI Act for absence of liability.

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
