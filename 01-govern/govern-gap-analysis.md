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



**Finding 3:Risk assessment conducted by a single discipline**

**System:** CreditScore-ML (consumer credit decisioning)

**Finding:** CreditScore-ML's one-time validation was performed by Model Risk Management alone, a four-person team, technically-focused function already noted as stretched thin across the bank's model portfolio. There's no indication that the assessment deliberately included other disciplines or perspectives, such as Compliance (with fair-lending expertise), legal, or customer-facing staff, in evaluating the model's risk.

**Why it matters (Govern 3):** Govern 3 calls for diverse perspectives, expertise, and demographics to be included in the AI risk management process, since a single-discipline group is more likely to miss risks that would be visible to people with different roles or vantage points. For a consumer credit model specifically, a technical-only review is well-positioned to catch statistical or model-performance issues, but less positioned to catch how a denial reason code lands with an actual applicant, or whether a pattern in outcomes tracks a protected class in a way that isn't obvious from model metrics alone. A single-discipline validation increases the chance that fairness or consumer-impact risks go unflagged simply because no one in the room was positioned to notice them.

**Recommended fix:** Require cross-functional participation in risk assessments for high-tier systems (per the Finding 1 tiering policy) at minimum, MRM plus Compliance/fair-lending expertise, with input from a customer-facing or consumer-advocacy role where relevant. This doesn't require a permanent new team; it can be a defined review-panel requirement triggered by a system's risk tier.
