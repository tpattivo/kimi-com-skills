---
name: kimi-com-skills
description: >
  A comprehensive skill collection covering document creation (Word/PDF/Excel), text humanization, deep research, and visual theming.
  ALWAYS use this skill when the user mentions or requests ANY of the following:
  - Creating or editing Word documents (.docx)
  - Creating or editing PDF documents (reports, papers, forms)
  - Creating or editing Excel spreadsheets (.xlsx), including financial models (DCF, three-statement, comps), data analysis, pivot tables, charts
  - Humanizing or rewriting AI-generated text to sound more natural
  - Conducting deep multi-iteration research and generating long-form reports
  - Applying visual themes (colors, fonts) to slides, documents, or artifacts

  ⚠️ Make sure to invoke this skill even if the user doesn't explicitly name the file format
  (e.g. "create a report with charts" → PDF or docx, "build a valuation model" → xlsx,
  "make this sound less robotic" → humanizer, "research quantum computing" → deep-research).
  If the user invokes it via slash command like `/kimi-com-skills humanizer <text>`, route to the
  sub-skill matching the first argument.
---

# Kimi Com Skills

This is a meta-skill that routes to specialized sub-skills. Each sub-skill contains complete, self-contained instructions for its domain.

## Routing

When this skill is triggered:

1. **Identify** which sub-skill matches the user's request
2. **Read** that sub-skill's `SKILL.md` **in full** before doing anything
3. **Follow** the sub-skill's instructions exactly — it takes full control

### Slash-command routing

If the user typed `/kimi-com-skills <name> ...`, the first word after the skill name is the sub-skill:

| Command | Route To |
|---|---|
| `/kimi-com-skills docx ...` | sub-skills/docx/SKILL.md |
| `/kimi-com-skills pdf ...` | sub-skills/pdf/SKILL.md |
| `/kimi-com-skills xlsx ...` | sub-skills/xlsx/SKILL.md |
| `/kimi-com-skills humanizer ...` | sub-skills/humanizer/SKILL.md |
| `/kimi-com-skills deep-research ...` | sub-skills/deep-research/SKILL.md |
| `/kimi-com-skills theme-factory ...` | sub-skills/theme-factory/SKILL.md |

### Natural-language routing

When the user describes the task in plain language, use these keywords:

| Keywords | Sub-Skill | Path |
|---|---|---|
| docx, Word, .docx, document, report (Word format) | **docx** | `./sub-skills/docx/SKILL.md` |
| PDF, report (PDF), paper, thesis, academic | **pdf** | `./sub-skills/pdf/SKILL.md` |
| xlsx, Excel, spreadsheet, financial model, DCF, valuation, pivot table, data analysis | **xlsx** | `./sub-skills/xlsx/SKILL.md` |
| humanize, rewrite, more natural, less robotic, AI-sounding | **humanizer** | `./sub-skills/humanizer/SKILL.md` |
| deep research, investigate, thorough research, comprehensive report | **deep-research** | `./sub-skills/deep-research/SKILL.md` |
| theme, styling, colors, fonts, slides, visual identity | **theme-factory** | `./sub-skills/theme-factory/SKILL.md` |

## Important Rules

- **Always read the entire sub-skill SKILL.md** before starting work. Do not skim.
- Sub-skill resources (scripts, references, assets) use paths **relative to the sub-skill's own directory** — they work as-is.
- If the request spans multiple sub-skills, handle them sequentially.
- If the request doesn't clearly match any sub-skill, ask the user which sub-skill they want.

## Sub-Skill Inventory

| Skill | Description | Contents |
|---|---|---|
| **docx** | Create/edit Word documents (.docx) — C# + OpenXML SDK | scripts, references, templates, validator |
| **pdf** | Create PDFs (HTML+Paged.js) and process existing PDFs | scripts, routes (html, latex, process) |
| **xlsx** | Excel spreadsheets, financial models, pivot tables, data analysis | scripts, references (DCF, comps, models) |
| **humanizer** | Remove AI writing patterns from text | instruction-only (no scripts) |
| **deep-research** | Exhaustive multi-iteration research + long-form reports | instruction-only |
| **theme-factory** | Apply/ generate visual themes (fonts, colors) for artifacts | themes/ directory, showcase PDF |
