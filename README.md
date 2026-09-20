# Idea to Product

A skill for Codex and Claude Code that turns a software idea into a practical commercial product plan. It helps users evaluate customer value, feasibility, costs, business models, and responsible use of other people's work.

## Install

These commands install **this skill**, assuming Git and your chosen app are already installed. Copy the appropriate block into a **macOS, Linux, or WSL terminal**. The examples use the default personal skills directories.

### Codex

```bash
mkdir -p "$HOME/.agents/skills"
git clone https://github.com/HuskyCanCode/idea-to-product.git "$HOME/.agents/skills/idea-to-product"
```

This installs the skill for use across your projects. Open a new Codex session and type `$idea-to-product` in the prompt. If it does not appear, restart Codex. The personal path and invocation follow the [official Codex skills documentation](https://learn.chatgpt.com/docs/build-skills).

### Claude Code

```bash
mkdir -p "$HOME/.claude/skills"
git clone https://github.com/HuskyCanCode/idea-to-product.git "$HOME/.claude/skills/idea-to-product"
```

Start a new Claude Code session and type `/idea-to-product` in the prompt. Restart Claude Code if it was running before the skills directory was created. See the [official Claude Code skills documentation](https://code.claude.com/docs/en/skills) for personal skills and slash commands.

The same `SKILL.md` and reference files are used in both apps. `agents/openai.yaml` provides optional Codex metadata; it is not required for the Claude Code workflow. Forms, browsing, charts, and PDF generation depend on the tools available in each app.

### Update an existing installation

Run only the command for the app you installed:

**Codex**

```bash
git -C "$HOME/.agents/skills/idea-to-product" pull --ff-only
```

**Claude Code**

```bash
git -C "$HOME/.claude/skills/idea-to-product" pull --ff-only
```

These update commands apply to Git clones made with the instructions above. If you installed a copied folder or used another skills location, update that existing copy instead. Preserve your edits before replacing files. A clone command will stop if its destination is already nonempty; do not delete an existing installation just to rerun it.

A repository checkout outside the skills directory and an installed skill are separate copies. Updating one does not automatically update the other. Avoid installing a second copy of the same skill in another folder for the same app.

## What it does

- Collects the important details through short, focused questions.
- Researches relevant products, prices, terms, and official rules.
- Rates relevant aspects from 0–10, with evidence and confidence. Unknowns stay unscored.
- Estimates development effort, operating costs, and business economics.
- Explains the business model with a chart showing users, value, payments, and costs.
- Checks ownership, permissions, licenses, attribution, and relevant legal questions.
- Provides prioritized actions with owners, effort, dependencies, and completion criteria.
- Offers an optional PDF slide deck after the report is complete.

Scores are planning judgments, not probabilities of success. Rights and legal checks identify issues and practical next steps; they do not guarantee legal safety.

## Conversation flow

**Idea → focused questions → research and provisional findings → final follow-up questions → report → optional PDF slides → implementation when requested**

The skill uses the latest answers and avoids repeating completed stages. Users can answer “undecided” when they need help making a choice. Question forms are used when supported by the host; chat is the fallback.

## Sample usage

Paste these examples into the **app's conversation**, not your terminal.

### Evaluate a new idea

**In Codex:**

```text
$idea-to-product I want to build a scheduling tool for independent tutors.
Help me evaluate demand, compare business models, estimate costs, and plan
a first version. Check the rights and attribution requirements for any
third-party tools or materials. Ask follow-up questions before the final report.
```

**In Claude Code:**

```text
/idea-to-product I want to build a scheduling tool for independent tutors.
Help me evaluate demand, compare business models, estimate costs, and plan
a first version. Check the rights and attribution requirements for any
third-party tools or materials. Ask follow-up questions before the final report.
```

### What the conversation looks like

An illustrative exchange; the questions adapt to what you have already shared:

> **You:** I want to build a scheduling tool for independent tutors.
>
> **Assistant:** Where would you launch first? What is the biggest scheduling problem for these tutors? Who would pay for the service?
>
> **You:** Start with adult language tutors in my city. They spend too much time arranging lessons through messages. Tutors would pay monthly; my budget is undecided.
>
> **Assistant:** I'll compare existing options and estimate a first version. Before finalizing the report, should it only schedule lessons, or also collect payments? Would tutors connect their own calendars with permission?
>
> **You:** Scheduling only, with permission to connect their calendars.

After researching the relevant facts and resolving material questions, the skill provides a scored assessment, cost ranges, a business-model map, an achievable first version, rights checks, and prioritized next actions. Missing evidence stays visible; it is not turned into a made-up score.

### Revise the plan or request slides

Continue in the same conversation in either app:

```text
Update my plan using a one-time purchase model instead of a subscription.
Explain how that changes the costs, business model, and next actions.
```

After the final report, the skill offers an optional PDF deck. To accept:

```text
Yes, create PDF slides from the final report. Start with the idea and cost
estimate, then show the business-model map, plan, financial details,
legal and rights research, next actions, and a linked sources appendix.
```

PDF creation requires suitable document-generation tools in your environment; installing this skill alone does not install those tools.

## Tools and optional outputs

The skill contains instructions and reference guides, with no runtime package dependencies. It uses the tools available in the host:

- **Research:** browsing is needed to verify current prices, terms, and rules. Without it, the skill identifies what remains unverified.
- **Questions:** an available question tool can provide forms; ordinary chat also works.
- **Business-model charts:** Mermaid is the default for static diagrams. An available visualization skill can support useful interactive models.
- **PDF slides:** created only when requested or accepted, using available presentation and PDF capabilities, with visual verification.

The default PDF has nine main slides plus a resources appendix. It starts with an idea and cost snapshot, then explains the business model, evaluation, plan, financial details, legal and rights research, and next actions. See the [slide guide](references/pdf-slides.md) for the full format.

## Repository contents

| File | Purpose |
| --- | --- |
| [SKILL.md](SKILL.md) | Main workflow and conversation instructions |
| [agents/openai.yaml](agents/openai.yaml) | Display name and suggested invocation |
| [Scorecard and report](references/scorecard-and-report.md) | Scoring criteria, confidence, and report structure |
| [Rights review](references/rights-review.md) | Ownership, reuse, permissions, and attribution checks |
| [Estimates and business model](references/estimates-and-business-model.md) | Cost assumptions, economics, and model charts |
| [PDF slides](references/pdf-slides.md) | Optional deck structure and quality checks |

## Maintaining the skill

Keep the main instructions concise and place detailed guidance in the reference files. Preserve relative links so the skill remains portable. When changing the workflow, check a fresh idea, a follow-up to an existing report, and the optional PDF decision to ensure the conversation still follows the user's choices.

Keep user reports, private documents, credentials, and generated artifacts outside this repository. A distribution license has not yet been selected.
