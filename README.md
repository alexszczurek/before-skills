# before skills

Agent skills from [before.click](https://before.click), the App Store design gallery.

A skill is a set of instructions your coding agent loads when it recognises the task. Instead of improvising an answer about App Store listings, it follows a fixed process, with rules and reasoning written down in advance.

## Install

```bash
npx skills add alexszczurek/before-skills
```

Works with Claude Code, Cursor, and any agent that reads `SKILL.md` files. The installer asks where to put the skill: globally, so it is available in every project, or in the current project only.

To install one skill from this repo:

```bash
npx skills add alexszczurek/before-skills --skill aso
```

## Skills

### aso

Writes and audits iOS App Store listings: app name, subtitle, keyword field, screenshots, icon, preview video, tags, ratings, localisation, and featuring nominations.

Distilled from [the before.click ASO guide](https://before.click/insights/app-store-seo) and checked against Apple's 2025–2026 documentation, so it covers what changed since most ASO advice was written: Apple-confirmed screenshot indexing, AI-generated App Store tags, Liquid Glass icons, the shift toward semantic search, and the App Store Review Guideline that prohibits competitor names in the keyword field.

## How to use it

Ask for what you want in plain language. The skill loads on its own when your request mentions App Store metadata, keywords, screenshots, ratings, or ASO:

- "Audit my App Store listing" — walks the audit checklist in order, cheapest fix first
- "Write a title and subtitle for my caffeine tracking app" — runs the keyword research procedure, then distributes terms across fields
- "Is my keyword field any good?" — checks character count, formatting, duplicate words, and prohibited terms
- "Plan my next metadata update" — separates what needs an app release from what you can change today

In Claude Code you can also invoke it directly with `/aso`.

## What it does differently

Ask an agent about ASO without a skill and you get a different answer each time, some of it out of date. The skill fixes the process, not the answer.

**It follows a procedure instead of guessing.** Keyword research runs in six steps: brainstorm, check App Store autocomplete, extract competitor terms, score for volume and relevance and difficulty, group by search intent, then distribute across fields. It cannot skip to writing metadata from intuition.

**Every rule carries its reason.** "Singular forms only, because Apple matches plurals automatically, so the plural wastes characters." The reasoning lets the agent extend a rule to situations the skill never described.

**Constraints are numbers, not adjectives.** Fill at least 95 of 100 keyword characters. Three system rating prompts per year, total. Submit featuring nominations three weeks ahead. Judge a metadata change at two to four weeks, never the next day.

**It knows what it cannot prove.** Claims are marked as Apple-confirmed or industry inference, so the agent does not present a guess as documentation.

## Contributing

Open an issue with the source, and the rule and its reasoning. Rules need evidence: Apple documentation, or data from a reputable ASO source.

## License

MIT
