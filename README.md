# UI Pattern Playbook

A single-file, AI‑ready UI pattern playbook for generating premium, consistent UI patterns for a voice‑agent builder.

## TL;DR
- Use `ui-pattern-playbook.md` as system context.
- Ask for patterns using the required template.
- Include YAML/JSON examples in every response.

## What’s included
- `ui-pattern-playbook.md` — standalone playbook with deterministic rules, checklists, and examples.
- `example.html` — setup wizard prototype with dark mode toggle.
- `example2.html` — modal + table example (selectable rows) with transitions.
- `example3.html` — “Talk to an AI agent” interface with revealable input.
- `example4.html` — patient chat history + scheduling preview with calendar.

## Quick start
- Provide `ui-pattern-playbook.md` as the system context to an AI model.
- Ask for outputs using the required pattern template.
- Use the prompts below to get consistent results.

## Prompting best practices
- Be explicit about which patterns you want and in what order.
- Require the full pattern template per pattern.
- Mention any layout composition (e.g., two‑pane, sidebar + main, stacked).
- Ask for examples in YAML/JSON/pseudocode in every response.
- Keep prompts short and deterministic; avoid vague “make it nice.”

## Prompt templates

### 1) Single component
```
Using ui-pattern-playbook.md, output the “Tool Connection / OAuth” modal pattern
in full required format, including example(s).
```

### 2) Multiple components on one screen
```
Using ui-pattern-playbook.md, design a screen that combines:
- Global Rules Console (left)
- Rule Detail + Diff (right)
- Publish Gate (bottom)
Output each pattern in full required format and explain the layout composition.
```

### 3) Full flow (wizard)
```
Using ui-pattern-playbook.md, design the end‑to‑end voice agent setup wizard
from template selection to publish. Include tool connection, test simulator,
error recovery, and publish checklist. Use the full required template.
```

### 4) Complex rule (Dr. Jane)
```
Using ui-pattern-playbook.md, design the Rule Builder UI for:
“Dr. Jane does not want to see more than three patients on Wednesday
that are coming in for complex disease conditions.”
Include structured YAML, conflict detection, and simulator output.
```

## Design semantics (from the playbook)

### Typography
- Font family: `Atkinson Hyperlegible` (secondary: `Avenir`).
- Font sizes: 32 / 24 / 20 / 16 / 14 (minimum 14 everywhere).
- Max font weight: 500 (numeric values only).

### Color
- Primary action color: `#9c5149`.
- Default body background: `#f2ede9`.
- Focus/selected borders: grey (not black).

### Spacing & layout
- Base spacing unit: 8px; allowed: 4, 8, 12, 16, 24, 32, 48, 64.
- Content wrapper padding: 25px (where 16px is typical).
- Boxes/modals: more left/right padding than top/bottom.

### Components
- Buttons: fully rounded (50px+ radius), 12px padding, right‑aligned groups.
- Dropdowns: overlay menus, close on outside click, gap ≤ 2px.
- Badges: use shared badge style with 16px left/right padding.
- Inputs: 12px padding, focus uses 1px grey border (no outline).

### Motion
- Standard transitions: 150–250ms.
- Buttons: press animation faster than hover.
- Modals: open/close via CSS `transition: all` with opacity changes.

### Optional dark mode
- Supported via a single toggle, mirrored spacing/type rules.
- Example token swap:
  - `--bg: #1b1b1b`
  - `--surface: #232323`
  - `--surface-muted: #2c2c2c`
  - `--text: #f2f2f2`
  - `--text-muted: #b0b0b0`
  - `--border: #3a3a3a`
  - `--border-focus: #6f6f6f`

## Testing rubric (quick)
Use these checks to validate outputs:
- **Template completeness**: all required pattern fields present.
- **Grandma usability**: explain‑before‑ask, clear Next paths, undo/restore.
- **Enterprise polish**: grid/spacing/type/elevation + audit/version/publish gates.
- **States coverage**: loading/empty/error/success/disabled present.
- **Examples**: YAML/JSON/pseudocode included for each pattern.

## Compatibility
Designed to work with Cursor, Codex, and Claude using plain Markdown only.
