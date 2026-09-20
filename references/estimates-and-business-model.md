# Estimates and business-model explanations

## Development effort and cash

Estimate the user's requested scope, then show a smaller validation option where useful. Do not silently replace broad requested coverage with a narrow prototype.

Use project-specific workstreams, such as product/report design; accounts/billing; data access/normalization; uploads; core logic; source-linked explanations; quality evaluation; security/accessibility; administration; deployment and documentation. Sum the low and high effort estimates using arithmetic tools.

For each stage show:

- Included scope and meaningful exclusions.
- Person-hours by role or workstream, with low/high estimates.
- Labor rate and whether it is a verified quote or a hypothetical planning assumption.
- Labor subtotal; contingency percentage and amount; additional one-time allowances or quotes.
- Calendar range, available hours per person per week, dependencies, and external lead times. More people do not divide every task's elapsed time evenly.
- Whether the figure is **incremental** or **cumulative**, and what earlier work is reusable. Do not double-count the pilot or contingency.

Distinguish a manual validation pilot, a self-service first version, and wider coverage/scale. Avoid implying a pretty demo includes production-quality rights handling, security, reliable data, or validation.

Compare hired development with founder-built cash costs when relevant. Founder work and AI-assisted work are not economically free. Assistance may reduce effort, but do not promise a fixed acceleration or assume it removes domain review, testing, and maintenance.

Do not reuse the rates, timelines, prices, or budgets from a past example as defaults. If resources are undecided, give explicit scenarios and identify what would most narrow the estimate. Never present a broad planning estimate as a fixed bid.

## Operating costs

Separate recurring fixed, usage-based, and irregular costs. Consider only applicable items:

- Hosting, database, storage, backups, email, monitoring, and domain.
- Data licenses, minimum commitments, redistribution rights, and usage charges.
- Document extraction, model inference, requests per account, retries, and support time.
- Payment percentage, per-transaction fee, subscription tooling, and relevant extra charges.
- Maintenance, content/data updates, independent quality review, support, and owner labor.
- Acquisition spending, refunds/chargebacks, insurance, professional services, taxes, and business administration where material.

Verify published current prices on provider pages when citing them. State billing region, plan, limits, and date. Mark undisclosed terms **quote required**, never zero. Usage-cost assumptions require a usage assumption (reports/requests/document size per account) or must be labeled an unmeasured allowance.

Show costs excluded from a total next to that total. A low hosting bill is not the whole cost of running a business. Check applicable taxes rather than assuming the sticker price is fully retained revenue.

## Scenario arithmetic

For a subscription model, define:

- `P`: revenue per paid month, excluding taxes collected for remittance.
- `N`: paying subscribers, not signups or visitors.
- `q`: combined applicable percentage payment/billing fees.
- `b`: per-charge fee, assuming one charge per paid month.
- `v`: other variable cost per subscriber-month.
- `F`: stated fixed monthly costs.

Then:

- Gross monthly revenue: `P × N`.
- Payment cost per subscriber: `P × q + b`.
- Contribution per subscriber-month: `c = P − (P × q + b) − v`.
- Modeled operating result: `N × c − F`.
- Subscribers needed to cover those modeled costs: `ceil(F / c)`, only if `c > 0`. If `c <= 0`, more subscribers do not solve that scenario.
- Recovering a one-time build `B` over `T` months adds `B / T` to the monthly recovery target; distinguish that target from an accounting expense or guaranteed payback.

Adjust for the actual model: annual prepayments, usage fees, one-off purchases, advertising, marketplace take rates, provider payouts, or service labor. Do not force every idea into subscription arithmetic.

For customer acquisition/retention, use measured cohorts when possible. A scenario with `L` paid months produces `P × L` gross customer revenue and approximately `c × L` contribution before acquisition and fixed costs under these simplifying assumptions. Label hypothetical lifetimes; do not assume 12 months for an episodic task. Distinguish planned cancellation after a completed task from dissatisfaction. Include acquisition and replacement of departing customers in a fuller model.

Use two or three useful scenarios rather than a false precision forecast. Explain sensitivity to the uncertain drivers. Verify arithmetic and round break-even customer counts upward. Label partial cost coverage honestly; never call a scenario “net profit” when material expenses are excluded.

## Business-model chart

Use a compact Mermaid flowchart when static labeled nodes and edges explain the model. Use the available visualization skill if adjustable costs or retention would materially help. Keep chart and report assumptions consistent. Do not create a standalone website merely to show a chart.

Show relevant relationships, not every implementation component:

- How the intended customer discovers the product (hypothesis if untested).
- Who uses it, who pays, how much, and when.
- Authorized data/material/service inputs.
- The work the product performs and the value delivered.
- What generates repeat use, renewal, or completion/cancellation.
- Revenue, supplier/service costs, acquisition and maintenance, and remaining result.

Label money flows separately from information and customer-value flows. Do not draw profit as inevitable, invent acquisition channels as proven, or imply that a third-party source grants access merely because it appears in the diagram.

A diagram should explain the current model. If the user switches from agent advertising to buyer subscriptions, the diagram and calculations must switch too. Domain details belong in the evaluated product, not in this reusable skill's default behavior.
