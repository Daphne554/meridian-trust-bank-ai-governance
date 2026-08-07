**Govern Gap Analysis**  


*Meridian Trust Bank · NIST AI RMF, Govern function*
__________________________________________________________________________________________________

**Finding 1: No documented, risk-tiered deployment policy**

**System:** CreditScore-ML (consumer credit decisioning)

**Finding:** Meridian has no evidence of a documented policy that risk-tiers AI systems before deployment and sets required scrutiny levels accordingly. CreditScore-ML went through a one-time model validation at launch (2023), but nothing indicates that validation was triggered by a formal risk-tiering policy. It appears to be standard practice rather than a governed requirement tied to the system's risk classification.

**Why it matters (Govern 1):** Govern 1 calls for organizational policies that determine the level of risk management activity a system requires based on its risk category, before development and deployment not validation that happens to occur afterward. Without a documented tiering policy, there's no defensible basis for why CreditScore-ML got the scrutiny it did and there's no guarantee future high-risk systems get equivalent treatment, also there's no audit trail showing risk-based decision-making.

**Compounding gap:** No revalidation cadence exists post-launch, meaning even the one-time validation that did occur isn't sustained. This is a separate but related finding under Measure/Manage the model can drift or degrade with no scheduled check.

**Recommended fix:** Draft a risk-tiering policy that classifies AI systems (high/medium/low) based on factors like consumer impact, regulatory exposure, and decision automation level with defined minimum requirements, validation frequency, required sign-offs and documentation standards per tier. Consumer credit decisioning models should sit in the highest tier given ECOA/Reg B and FCRA exposure.



**Finding 2: No clear ownership of AI risk**

**System:** CreditScore-ML (consumer credit decisioning)

**Finding:** Several roles touch CreditScore-ML's risk in some way. Data & Analytics builds it, MRM validates it, Compliance monitors fair lending exposure but no single role or person is accountable for the system's AI risk end-to-end. Even without a formal AI governance committee, Govern 2 asks whether existing roles include clear, specific AI risk ownership. They don't, each function owns a piece of the system, but none owns the whole risk picture.

**Why it matters (Govern 2):** Govern 2 calls for clear roles, responsibilities, and lines of authority for AI risk to be defined and understood across the organization, with accountability reaching leadership. Diffused responsibility means no one can be held to account if a risk is missed between functions.  gap in adverse-action mapping, for instance, could fall through the cracks between Data & Analytics (built the model), MRM (validated it once), and Compliance (monitors fair lending) without any of them being positioned to catch it, because none of them owns the full picture. Leadership visibility is also unclear: the CRO receives general model risk reporting, but nothing indicates AI-specific risks are surfaced to leadership distinctly.

**Recommended fix:** Assign a named AI risk owner per system not necessarily a new hire, but a clear responsibility added to an existing role with authority to escalate findings across Data & Analytics, Compliance, and up to the CRO. Pair this with a defined reporting line so AI-specific risks reach leadership distinctly from general model risk reporting.
