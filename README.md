# Idea to Product

A Codex skill for turning a software idea into a practical commercial product plan. It helps users evaluate customer value, feasibility, costs, business models, and responsible use of other people's work.

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

## Use in Codex

Place this repository's folder in your personal Codex skills directory, usually `~/.codex/skills/idea-to-product`. Keep `SKILL.md`, `agents/`, and `references/` together. If a version is already installed, preserve any changes before replacing it.

Start a new task and invoke the skill, for example:

```text
$idea-to-product I want to build a scheduling tool for independent tutors.
Help me evaluate the idea, estimate costs, and plan a first version.
```

You can also continue an existing evaluation:

```text
$idea-to-product Update my plan using a one-time purchase model instead
of a subscription, and explain how that changes the economics.
```

A repository checkout outside the skills directory and an installed skill are separate copies. Updating one does not automatically update the other.

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
