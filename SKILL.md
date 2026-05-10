---
name: kimi
description: "Umbrella skill for Kimi.com tools (docx, pdf, humanizer, xlsx, deep-research, theme-factory). Usage: `/kimi <sub-skill> <task>` — routes to the appropriate sub-skill for document creation, PDF processing, text humanization, spreadsheet work, deep research, or theme styling."
---

# Kimi Skills Router

This is a meta-skill that provides access to Kimi.com's specialized skills under a single `/kimi` umbrella. When invoked with a sub-skill name as the first argument, route to that sub-skill by reading its `SKILL.md` and following its instructions.

## Available Sub-Skills

| Sub-command | Description | Directory |
|---|---|---|
| `docx` | Create and edit Word documents (.docx) using C# + OpenXML SDK or WIR engine | `./docx` |
| `pdf` | Create PDFs using HTML+Paged.js, LaTeX, or process existing PDFs | `./pdf` |
| `humanizer` | Remove signs of AI-generated writing — make text sound natural and human | `./humanizer` |
| `xlsx` | Create, analyze, and manipulate Excel files using Python + openpyxl/pandas | `./xlsx` |
| `deep-research` | Exhaustive, evidence-based deep research and long-form report engineering | `./deep-research` |
| `theme-factory` | Apply pre-set visual themes (fonts/colors) to slides, docs, or other artifacts | `./theme-factory` |

## Routing Instructions

When the user invokes `/kimi <sub-skill> [task description]`:

1. **Identify the sub-skill** from the first argument (e.g., `docx`, `pdf`, `humanizer`, etc.)
2. **Read that sub-skill's `SKILL.md`** from its sub-directory (located at `{skill_base_dir}/<sub-skill>/SKILL.md`, where `{skill_base_dir}` is the directory containing this file)
3. **Follow ALL instructions in that sub-skill's SKILL.md** to complete the task, including:
   - Route selection logic (e.g., for PDF: HTML vs LaTeX vs Process)
   - Reference file requirements (read referenced files before writing any code)
   - Script execution instructions
   - Validation procedures (run validation before delivering results)
4. **Resolve all paths against this skill's base directory** (the folder containing this `SKILL.md`):
   - Construct the full absolute path by combining `{skill_base_dir}` with the relative path (e.g., for docx scripts: `{skill_base_dir}\docx\scripts\docx build`).
   - When running scripts: use the full absolute path:
     - `bash {skill_base_dir}/docx/scripts/docx build`
     - `bash {skill_base_dir}/pdf/scripts/pdf.sh check`
     - `bash {skill_base_dir}/xlsx/scripts/Xlsx validate`
   - When reading reference files: use the full absolute path:
     - `read_file {skill_base_dir}/docx/references/wir-reference.md`
     - `read_file {skill_base_dir}/pdf/routes/html.md`
   - When reading template/assets files: use the full absolute path similarly

## Important Notes

- **Do not copy or inline sub-skill instructions into this file.** Read the sub-skill's SKILL.md at routing time.
- **Do not skip validation steps.** Each sub-skill has specific validation/checking procedures — run them before delivering results.
- **Output files should be delivered in the user's working directory**, not inside the sub-skill directories.
- Some sub-skills (like `humanizer`, `theme-factory`) are instruction-only and have no scripts. Route to them by reading their SKILL.md and following those instructions.
- The `deep-research` sub-skill references `/mnt/agents/output/` paths — these are Linux container paths. On Windows, adapt the output path to the user's working directory.
