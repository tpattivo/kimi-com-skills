# Kimi.com Agent Skills

Collection of Agent Skills from [Kimi.com](https://kimi.com), packaged for use with Qwen Code, Claude Code, and other compatible AI coding assistants.

## Skills

| Skill | Description |
|---|---|
| **[docx](./docx/)** | Create and edit Word documents (.docx) — C# + OpenXML SDK for creation, WIR engine for editing, comments, tracked changes |
| **[pdf](./pdf/)** | Professional PDF creation (HTML+Paged.js) and processing (extract, merge, fill forms) |
| **[xlsx](./xlsx/)** | Advanced Excel file manipulation — formulas, formatting, pivot tables, financial modeling |
| **[humanizer](./humanizer/)** | Remove signs of AI-generated writing — make text sound natural and human |
| **[deep-research](./deep-research/)** | Exhaustive, evidence-based deep research and long-form report engineering |
| **[theme-factory](./theme-factory/)** | Apply pre-set visual themes (fonts/colors) to slides, docs, and other artifacts |

## Installation

### Install all skills

```bash
npx skills add https://github.com/tpattivo/kimi-com-skills --all
```

### Install individual skills

```bash
# List available skills
npx skills add https://github.com/tpattivo/kimi-com-skills --list

# Install specific skill(s)
npx skills add https://github.com/tpattivo/kimi-com-skills --skill docx
npx skills add https://github.com/tpattivo/kimi-com-skills --skill pdf --skill xlsx
```

### Global installation

```bash
npx skills add https://github.com/tpattivo/kimi-com-skills --all -g
```

## Requirements per skill

| Skill | Dependencies |
|---|---|
| **docx** | .NET SDK (for C# + OpenXML), or Python 3 + python-docx (for WIR editing) |
| **pdf** | Node.js, Playwright + Chromium (for HTML→PDF), or Python 3 + pikepdf (for processing) |
| **xlsx** | Python 3 + openpyxl, pandas |
| **humanizer** | None (instruction-only) |
| **deep-research** | None (research + report generation) |
| **theme-factory** | None (instruction-only) |

## Usage

Once installed, invoke a skill in your assistant by referencing it by name:

- `Create a Word report about quarterly earnings` → triggers the **docx** skill
- `Humanize this text` → triggers the **humanizer** skill
- `Build a DCF valuation model` → triggers the **xlsx** skill

## License

Each skill directory contains its own license file. See the respective `LICENSE` or `LICENSE.txt` files for details.

- `docx/` — MIT License
- `pdf/` — MIT License
- `xlsx/` — MIT License
- `humanizer/` — MIT License
- `theme-factory/` — Apache-2.0 License
- `deep-research/` — MIT License
