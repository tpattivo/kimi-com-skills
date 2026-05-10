# Kimi.com Agent Skills

Collection of Agent Skills from [Kimi.com](https://kimi.com), packaged for use with Qwen Code, Claude Code, and other compatible AI coding assistants.

Installed as a **single skill** — use `/kimi-com-skills <sub-skill>` to invoke any sub-skill.

## Skills included

| Sub-Skill | Description |
|---|---|
| **[docx](./kimi-com-skills/sub-skills/docx/)** | Create and edit Word documents (.docx) — C# + OpenXML SDK for creation, WIR engine for editing, comments, tracked changes |
| **[pdf](./kimi-com-skills/sub-skills/pdf/)** | Professional PDF creation (HTML+Paged.js) and processing (extract, merge, fill forms) |
| **[xlsx](./kimi-com-skills/sub-skills/xlsx/)** | Advanced Excel file manipulation — formulas, formatting, pivot tables, financial modeling |
| **[humanizer](./kimi-com-skills/sub-skills/humanizer/)** | Remove signs of AI-generated writing — make text sound natural and human |
| **[deep-research](./kimi-com-skills/sub-skills/deep-research/)** | Exhaustive, evidence-based deep research and long-form report engineering |
| **[theme-factory](./kimi-com-skills/sub-skills/theme-factory/)** | Apply pre-set visual themes (fonts/colors) to slides, docs, and other artifacts |

## Installation

```bash
# Install the single unified skill
npx skills add https://github.com/tpattivo/kimi-com-skills
```

This installs **one skill** named `kimi-com-skills`. All sub-skills are accessed through it.

## Usage

### Slash command

```
/kimi-com-skills humanizer Fix this paragraph
/kimi-com-skills docx Create a quarterly report
/kimi-com-skills pdf Write a research paper on climate change
/kimi-com-skills xlsx Build a DCF valuation model
/kimi-com-skills deep-research Investigate quantum computing breakthroughs
/kimi-com-skills theme-factory Apply a modern theme to this slide deck
```

### Natural language

Describe what you need naturally — the umbrella skill routes to the right sub-skill:

- "Create a Word report about quarterly earnings" → routes to **docx**
- "Humanize this text" → routes to **humanizer**
- "Build a DCF valuation model" → routes to **xlsx**
- "Research the latest advances in fusion energy" → routes to **deep-research**

## Requirements per sub-skill

| Sub-Skill | Dependencies |
|---|---|
| **docx** | .NET SDK (for C# + OpenXML), or Python 3 + python-docx (for WIR editing) |
| **pdf** | Node.js, Playwright + Chromium (for HTML→PDF), or Python 3 + pikepdf (for processing) |
| **xlsx** | Python 3 + openpyxl, pandas |
| **humanizer** | None (instruction-only) |
| **deep-research** | None (research + report generation) |
| **theme-factory** | None (instruction-only) |

## License

Each sub-skill directory contains its own license file. See the respective `LICENSE` or `LICENSE.txt` files for details.

- `docx/` — MIT License
- `pdf/` — MIT License
- `xlsx/` — MIT License
- `humanizer/` — MIT License
- `theme-factory/` — Apache-2.0 License
- `deep-research/` — MIT License
