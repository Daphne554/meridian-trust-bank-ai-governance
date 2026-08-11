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



**Finding 4: Risk documentation exists only as a one-time snapshot, with no mechanism ensuring follow-through**

**System:** Cross-system (CreditScore-ML, Watchtower)

**Finding:** Where risk documentation exists, it reflects a single point in time rather than an ongoing lifecycle record. CreditScore-ML's validation was performed once at launch (2023) with no revalidation scheduled after that. Watchtower's alert-tuning has degraded since a 2024 pass with no owner responsible for re-tuning. Nothing in the profile suggests a punitive culture that would discourage staff from raising concerns but nothing suggests concerns are addressed either. The likely mechanism isn't culture in the sense of hostility toward raising issues, it's structural. MRM is a four-person function already stretched thin across the model portfolio, and per Finding 2, no single role is accountable for ensuring an identified AI risk actually gets addressed once flagged. A concern can be raised and still stall, not because anyone blocked it, but because no one owns following it through and the team that would act on it lacks the capacity to.

**Why it matters (Govern 4):** Govern 4 calls for risk management to be embedded as an ongoing organizational practice, with risks, benefits, and impacts documented and tracked across a system's full lifecycle not treated as a launch-day formality. A one-time snapshot gives a false sense of assurance: CreditScore-ML looks "validated" on paper, but that status hasn't been re-confirmed in three years, and there's no structural guarantee it ever will be. Documentation without a mechanism to keep it current or to ensure flagged risks get resolved doesn't meaningfully reduce risk, it just creates a record that a check happened once.

**Recommended fix:** Pair the risk-tiering policy (Finding 1) and named risk ownership (Finding 2) with a defined follow-through requirement, every identified risk gets logged with an owner, a target resolution date, and a status that's reviewed on a set cadence (e.g., quarterly, aligned to existing Board Risk Committee reporting). This doesn't require new headcount immediately it requires a tracking mechanism and an accountable reviewer, which can be assigned as part of the Finding 2 fix.



**Finding 5: Individual complaints aren't aggregated into a model-level feedback signal**

**System:** CreditScore-ML (consumer credit decisioning)

**Finding:** A customer who believes CreditScore-ML denied them unfairly would likely raise it through customer service or in response to the required FCRA adverse action notice, and that complaint would reasonably reach Compliance given their fair-lending role. So individual complaints don't disappear entirely but nothing in the profile suggests those complaints are tracked as a pattern that could signal a problem with the model itself. Each complaint appears to be handled as a one-off case resolution, not as a data point feeding back into AI governance or triggering a model-level review.

**Why it matters (Govern 5):** Govern 5 calls for mechanisms that allow external, real-world feedback from customers or other affected parties to actually inform AI risk management, not just get resolved individually. A pattern of complaints (e.g. a spike in denials or a demographic skew in who's complaining) can be an early warning sign of model drift or bias that internal validation alone might miss, since internal teams aren't the ones experiencing the model's real-world impact firsthand. Without aggregation, that signal is lost even when the underlying complaints are being handled reasonably well on a case-by-case basis.

**Recommended fix:** Establish a lightweight process for Compliance to log AI-related complaints in a way that it is queried by the system (not just by individual case), with a periodic review (e.g. quarterly, aligned with the Finding 4 tracking) to check for patterns that would warrant flagging CreditScore-ML for out-of-cycle review. This connects naturally to the named AI risk owner role proposed in Finding 2. The owner would be the natural recipient of an aggregated complaint-pattern report.

**Finding 6: No third-party due diligence or contingency plan for vendor fraud model**

**System:** SentryAI (fraud detection)

**Finding:** SentryAI's core model is vendor-licensed, with Meridian's own tuning layer built on top for in-house customization. The vendor provides a model card, but Meridian has never independently validated the vendor's training data, bias testing, or underlying model quality claims. Due diligence has effectively stopped at accepting the vendor's own documentation. There's also no contingency plan for what happens if the vendor relationship or the base model itself fails (e.g., contract non-renewal, vendor outage, or a bias/quality issue surfacing after the fact). Meridian's in-house tuning layer is not a fallback in this scenario it's built on top of the vendor model, so a failure at the vendor level would likely compromise the tuning layer too, making it an additional point of fragility rather than a safety net.

**Why it matters (Govern 6):** Govern 6 calls for documented policies addressing AI risks arising from third-party software and data, including due diligence before adoption and contingency processes for third-party failures. This matters especially here because SentryAI's contract is up for renewal this year which means Meridian is about to make a renewal decision without ever having independently verified what it's renewing. Fraud detection is also an area where a vendor model failure has immediate financial consequences (missed fraud, or customer-impacting false positives), so the lack of a contingency plan is a live operational risk, not just a documentation gap.

**Recommended fix:** Before the contract renewal decision, commission an independent review of the vendor's training data practices and bias testing methodology, this doesn't need to be exhaustive but should go beyond accepting the vendor's own model card at face value. Separately, document a contingency plan for a scenario where the vendor model becomes unavailable or is found to have an undisclosed issue.
