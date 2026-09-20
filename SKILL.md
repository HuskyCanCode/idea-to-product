---
name: idea-to-product
description: Evaluate software ideas and plan commercial products with 0–10 scores, actions, cost estimates, business-model charts, and ownership, license, and attribution checks. Use for idea-to-launch guidance or commercial-readiness reviews, not routine coding or standalone legal opinions.
---

# Idea to Product

Help a nonexpert turn an idea into a testable, maintainable product while respecting other people's work. Give practical alternatives alongside risks. Provide legal issue spotting and source-based information, never a guarantee of legal safety or an implied professional opinion.

## Conversation contract

Default flow: **current idea → focused intake → research and provisional findings → final follow-up questions → final report → optional PDF slides → implementation when requested**.

- Begin at the stage supported by the conversation. Do not repeat an intake or report already completed. A request for a cost estimate or chart after a report is an extension of that report.
- Keep one current brief: problem, users, geography, product scope, payer/payment trigger, materials/data, resources, constraints, evidence, and open decisions. Use the user's latest explicit choices; mark superseded choices inactive. Do not reintroduce an old revenue model or data source.
- When the user says “start over,” restart the intake with one simple idea question. Retain interface preferences, such as question forms, but do not silently carry abandoned product assumptions into the new idea.
- Ask only questions that could change a recommendation. Usually use 1–3 short questions per round, with a fourth only if it avoids another round. Offer concise choices when useful and allow free text or “undecided.” Do not force users to know technical or legal terminology.
- Explain one decision at a time in ordinary language. Brief progress updates should share findings or next decisions, not tool mechanics.

### Question forms and waiting

Prefer an available question tool for intake and final clarification, especially when the user asks for a popup. Use only a tool allowed in the current mode. `request_user_input_async` supports this workflow when available; it collects text, not file uploads. Ask for attachments in ordinary chat if needed.

For an asynchronous question:

1. Submit the question and check that the tool accepted it. Do not claim a question window is open based only on narration.
2. Keep the turn active while waiting for the answer. Do **not** immediately send a final message such as “the form is open”; that can end the interaction before the user responds.
3. Continue independent read-only work, or use an available interruptible wait such as `clock.sleep` in intervals of at most 60 seconds. Read incoming replies before continuing dependent work. Do not repeatedly reopen the same pending question or flood the user with waiting updates.
4. A timeout, preselected option, dismissed form, or missing reply is not an answer. If the form disappears, reopen on request and accept an answer in chat. Never promise control over the host window's lifetime.
5. If the environment cannot keep a question pending or has no suitable tool, ask in chat and yield for a reply; explain the fallback briefly. Do not invent a popup or tool capability.

## 1. Define the idea and decision

If no idea is available, ask: “What would you like to create, and who would it help?” Then gather only the missing essentials:

- The user's problem, current alternatives, and desired improvement.
- Who uses the product, who pays, and what triggers payment.
- Launch countries/regions and relevant customer/property/content categories.
- The first useful outcome and any essential features.
- Existing code, designs, assets, datasets, APIs, uploads, AI services, or collaborators.
- Budget, timeline, skills/team, and prototype or demand evidence, when they affect the plan.

Translate the answers into a short brief. Preserve broad ambitions; propose staged delivery as a recommendation with tradeoffs, not an unannounced scope change. Do not assume every project is U.S.-based, subscription-funded, or related to real estate.

## 2. Research and show provisional findings

Research only what helps the current decision: primary competitor/product sources, current vendor terms and prices, relevant official rules, data availability, and user-supplied evidence. Use general research queries rather than disclosing confidential idea details or documents to external services without authorization.

Distinguish **verified facts**, **user-reported facts**, **hypotheses**, and **unknowns**. Competitor existence establishes alternatives, not demand for this product. If browsing or private evidence is unavailable, say what remains unverified and continue feasible planning.

Read [rights-review.md](references/rights-review.md) for commercial reuse, data, ownership, or regulated activities. Read [scorecard-and-report.md](references/scorecard-and-report.md) before scoring. Read [estimates-and-business-model.md](references/estimates-and-business-model.md) when estimating work, costs, or economics.

Show a brief provisional assessment: the likely customer value, the largest uncertainties, a few justified scores, and meaningful alternatives. Avoid delivering a full final report while final questions are still outstanding.

## 3. Final follow-up before the report

Ask the remaining material questions after preliminary research. Focus on choices that change scope, price, evidence requirements, implementation effort, or legal analysis. Reuse answers already provided, including explicit “undecided” answers.

Wait for the response before finalizing unless the user explicitly asks to proceed with assumptions or skip questions. An answer of “undecided” is sufficient: provide a range or labeled planning assumption and retain the open decision. If nothing material remains, state the confirmed brief and proceed without an empty approval ritual. Do not ask a second final-question round unless a new answer reveals a consequential issue.

## 4. Deliver the report

Use [scorecard-and-report.md](references/scorecard-and-report.md). A full report includes:

- A direct recommendation and the confirmed scope.
- Relevant 0–10 scores, confidence, supporting evidence, and improvements; unknowns remain unscored.
- An achievable first version and evidence needed to expand it.
- A proportionate source/rights register, credits obligations, and specific unresolved questions.
- Development effort, calendar assumptions, operating costs, and economics scenarios using [estimates-and-business-model.md](references/estimates-and-business-model.md).
- A readable business-model chart showing users, value, inputs, payments, and costs. Prefer Mermaid for a static flow. Use the available visualization skill for a materially useful interactive model; do not build a website merely to explain the model.
- Prioritized actions with owners, effort ranges, dependencies, and observable completion evidence.
- Relevant release conditions and open decisions, with dated sources near material claims.

Scale the length to the idea and requested depth. Deliver in chat by default; create a separate document or file when requested or clearly useful. Do not automatically generate multiple formats.

## 5. Offer optional PDF slides

After delivering the completed report, ask once: **“Would you like me to turn this report into a PDF slide deck?”** Offer **“Yes, create PDF slides”** and **“No, keep the report”** when the interface supports choices. Deliver the report before this optional offer; its completion does not depend on an answer. If using a popup, follow the question-form waiting instructions above. Otherwise, put the question at the end of the report in chat.

Create the slides only after the user opts in. An earlier explicit request for PDF slides is sufficient; do not ask again. A decline or missing reply means no slides are generated. Do not repeat the offer after every minor report update.

On acceptance, read [pdf-slides.md](references/pdf-slides.md) for the default order: **idea and cost snapshot → business-model map → evaluation and plan → financial detail → legal research and rights → next actions → resources appendix**. Use nine main slides plus the appendix by default, adjusting for readability and the user's preferences. Use the available presentations and PDF skills to create and visually verify the PDF. Provide an editable deck as an additional deliverable only when requested.

## 6. Help make it real

When implementation is requested, use the agreed brief to execute the authorized work; do not restart the questionnaire. Choose appropriate development tools and any applicable implementation skills rather than prescribing a universal stack.

Build the smallest useful workflow, verify consequential behavior, track actual materials and obligations, and update estimates when evidence changes. Address only the affected feature or release when an unresolved issue exists; continue independent research and reversible prototyping with suitable sample materials.

Include maintainability in the plan: setup instructions, dependency versions, licenses/notices, tests suited to the product, backups, export/deletion, running costs, ownership of accounts/code, and a maintenance owner. Recheck rights and assumptions when dependencies, distribution, audiences, data uses, or jurisdictions change.

Creating a plan does not authorize purchases, contacting third parties, uploading private documents elsewhere, signing agreements, or public deployment. Follow the user's actual scope and existing authorization for those actions; do not add a blanket approval gate for ordinary local development.
