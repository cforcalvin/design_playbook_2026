# UI Pattern Playbook for a Voice‑Agent Builder

Purpose: A standalone, deterministic Markdown playbook for AI agents to generate premium, consistent UI patterns for a voice‑agent builder. The UI must be easy enough for a 70‑year‑old retired grandma to build complex systems, and impressive enough to wow enterprise buyers.

This file is self‑contained. Links are optional references only; the rules here are sufficient.

## How an AI should apply this file

Execution checklist:
- Read all sections in order; do not skip.
- Apply Global Defaults before pattern specifics.
- For every pattern output, include all required pattern fields.
- Use plain language; define jargon inline the first time.
- If constraints conflict, apply the Conflict Resolution Rules.
- Provide at least one concrete example per pattern.
- Validate output against the Enterprise‑Demo Gate before finalizing.

## Global Defaults

### Language and clarity
- Use plain language. Define any jargon inline in parentheses.
- Explain before you ask: every input must include a short “why this matters” hint.
- Examples must sit directly next to inputs (same section or immediately below).
- Use short sentences. One idea per sentence.
- Avoid acronyms unless defined inline.

### Grandma‑usable defaults
- Simple → Advanced toggle always available. Simple remains fully capable.
- Clear “Next” paths for multi‑step flows; show visible progress.
- Forgiveness: undo, restore, and “nothing permanent until publish.”
- Prevent errors before they happen; recover gracefully when they do.
- Avoid hidden states. Always show what will happen next.

### Enterprise‑wow defaults (explicit and testable)
- Cohesive premium visual rules: grid, spacing rhythm, type scale, elevation, density.
- Polished interactions: hover/focus/press, skeleton loading, tasteful motion + reduced motion.
- Enterprise credibility: roles/permissions, audit log, versioning/rollback, publish gates.
- Ensure every primary screen supports auditability and safe publishing.

### Accessibility defaults
- Keyboard support for every action and control.
- Visible focus indicators, high contrast, and reduced motion support.
- Minimum touch target: 44x44 px.
- Provide labels, helper text, and error text in plain language.
- No color‑only meaning; include icons or text labels.

### Conflict Resolution Rules
- Specific pattern rules override Global Defaults only if explicitly stated.
- Safety > clarity > speed > visual flourish.
- If a constraint reduces grandma usability, default to the safer, clearer option.
- When in doubt, prefer reversible actions and explicit confirmation.

## Visual System (Premium, Cohesive, Testable)

### Grid and layout
- Grid: 12‑column for desktop, 6‑column for tablet, 4‑column for mobile.
- Max content width: 1200 px; minimum comfortable width: 320 px.
- Use consistent gutters: 24 px desktop, 16 px mobile.
- Keep primary actions in the same location per step.

### Spacing rhythm
- Base unit: 8 px.
- Allowed spacing: 4, 8, 12, 16, 24, 32, 48, 64.
- Vertical spacing must use the base unit only.

### Type scale
- Use a clear hierarchy: 32, 24, 20, 16, 14.
- Default body size: 16.
- Line height: 1.5 for body, 1.2 for headings.
- Large headers should not add extra top/bottom padding.

### Typography and sizing constraints (hard rules)
- Font family: "Atkinson Hyperlegible" for all text. Secondary: Avenir.
- Minimum font size: 14 px (no text smaller than 14 px anywhere, including
  placeholders, helper text, hints, captions, badges, and metadata).
- Maximum font weight: 500 (no text thicker than 500).
- All font weights must be numeric values only (no `bold`, `bolder`, etc.).
- Table header text must use font-weight 500.
- Table header rows must use a very light grey background instead of an underline.
- Table header rows must have rounded corners on all edges.
- Selectable table rows must highlight on hover.
- All interactive controls must explicitly set `font-size: 14px` or larger
  (buttons, inputs, selects, textareas, tags, pills, menu items).
- Input and button padding: 12 px on all sides, including default browser
  dropdown inputs and native button/input styles.
- Button groups must be flush right; secondary button sits immediately left of
  the primary button.
- Buttons must have greater left/right padding than top/bottom padding.
- All buttons must be fully rounded (pill shape) with a border radius of 50 px
  or more.
- Modals, content blocks, and pills must have greater left/right padding than
  top/bottom padding.
- Content wrapper padding that is usually 16 px must be 25 px instead.
- If a native browser dropdown cannot guarantee 12 px padding, replace it with a
  custom dropdown component that enforces 12 px padding and 14 px text.
- Dropdown menus must be temporary overlays that do not shift layout.

### Elevation and density
- Use 3 elevation levels: 0 (flat), 1 (card), 2 (modal).
- Density: comfortable by default; compact only for large data tables.
- Box shadows must be sharp and light, e.g. `box-shadow: 0 4px 0 rgba(0,0,0,0.04);`.
- Border weight must not exceed 1 px anywhere.

### Color and contrast
- Primary action color is `#9c5149`.
- Primary action color must meet AA contrast.
- Provide neutral backgrounds for readability.
- Default body background color is `#f2ede9`.
- Text links: no underline, no background, and use the primary color.
- Text links: simple color change on hover and active; no inset/press animation.
- Text links must not show any border.
- Profile/agent avatars use a small circular gradient (e.g., 44×44) with
  contrasting colors (blue to pink).
- Avatar and name blocks in profile rows must align to the top.

### Optional dark mode
- Dark mode is optional but supported via a single toggle.
- Dark mode must mirror the same spacing, type, and component rules.
- Use dark surfaces with readable contrast and keep the primary color unchanged.
- Example token swap (dark mode):
  - `--bg: #1b1b1b`
  - `--surface: #232323`
  - `--surface-muted: #2c2c2c`
  - `--text: #f2f2f2`
  - `--text-muted: #b0b0b0`
  - `--border: #3a3a3a`
  - `--border-focus: #6f6f6f`
- All components must have a dark mode equivalent, including inputs, dropdowns,
  menus, cards, badges, and active step indicators.
- Table headers must have a dark mode background that preserves contrast.
- Error, warning, success, and info colors must be distinct and labeled.
- Focused and selected state border colors must be grey (not black).
- Active steps and open dropdown menus must use grey borders.
- Scrollbars must use a lighter grey color.
- Scrollbar track/background must be transparent.
- On input focus, remove the outline and use a 1 px grey border.
- Focus styles must override default borders (use equal or higher specificity).
- Dropdown triggers and inputs must share a fixed height.
- Dropdown triggers must use a down arrow icon for the indicator.
- Dropdown indicator must be vertically centered within the trigger.

### Motion
- Motion is subtle and purposeful only.
- Provide “Reduce motion” option; honor system settings.
- Use 150–250 ms for standard transitions.
- Use skeleton loading for long waits (> 800 ms).
- Hover states must animate with a short transition (e.g., 120–180 ms).
- Dropdown menus must animate on open/close (e.g., opacity + small Y shift).
- Dropdown triggers must show a clear active highlight when opened.
- Dropdown menus must appear very close to the trigger; use `top: calc(80% + 1px)`
  for the overlay positioning to keep the gap minimal.
- Dropdown triggers must be the same height as inputs.
- Dropdown triggers must match input height and corner radius.
- Dropdown menus must use a slightly stronger outline and shadow than cards.
- Dropdown menu options must have hover and click highlighting.
- Dropdown menu options must use a 6 px corner radius.
- Dropdown menus must use equal padding on all sides (8 px).
- Clicking outside a dropdown must close the menu.
- Badges must use 16 px left/right padding.
- Badges must use the shared badge style used in examples (no pill-only variants).
- Status indicators like “Status: Ready” must use the badge style, not button styling.

## Interaction Foundations

- Every action has a clear affordance (button, link, or card).
- All destructive actions require undo‑first or explicit confirmation.
- Provide consistent hover, focus, and pressed states.
- Secondary buttons: add a grey border on hover and darken background on click.
- Primary buttons: on click, background switches to white, text switches to slightly
  darkened grey, and border becomes grey.
- Primary buttons must have a white border by default.
- After click, primary button color transition back to default must take 0.3 s.
- Button click animation: quick downward Y‑axis press with a faster transition
  than hover (e.g., 60–90 ms).
- Show immediate feedback for user actions.
- Use inline validation; avoid blocking users late in flows.

## Reusable Components (Required)

- Build reusable component primitives for buttons, inputs, dropdowns, menus,
  modals, badges, tabs, and toasts.
- Patterns must reference these primitives instead of redefining them.

## Pattern Output Template (Required)

For every pattern, output using this structure:
- Intent + when to use/avoid
- Anatomy
- Layout rules + responsive behavior
- Interaction rules + motion
- States (loading/empty/error/success/disabled)
- Microcopy rules
- Accessibility
- Variants + anti‑patterns
- Example(s)

## Governance, Versioning, and Safe Publishing

### Versioning rules
- Every entity (pattern, rule, instruction) has version id and status.
- Statuses: draft, review, approved, published, deprecated.
- Publishing is gated: review required for high‑risk changes.

### Auditability
- Log all changes with who, when, and why.
- Provide a change summary and rollback option.
- Keep a read‑only history view.

### Safe publishing
- Provide a preview‑before‑publish step.
- Highlight breaking changes and impacted agents.
- Offer staged rollout and immediate rollback.

### AI instructions and system prompts
- Treat system prompts as governed assets.
- Show diff before publish.
- Require explicit confirmation for high‑risk updates.

## AI Instructions + Global Rules (Patterns)

### 1) Global Rules Console
- Intent + when to use/avoid:
  - Use for system‑wide rules and policies.
  - Avoid for single‑agent tweaks (use Agent Instructions).
- Anatomy:
  - Rule list, version selector, diff view, status badge, audit log.
- Layout rules + responsive behavior:
  - Two‑pane layout: list left, details right.
  - Stack on mobile with tabs.
- Interaction rules + motion:
  - Inline edit with change summary required.
  - Diff view opens in a side panel.
- States:
  - Loading: skeleton list.
  - Empty: “No global rules yet.”
  - Error: show retry and support link.
  - Success: toast with rollback link.
  - Disabled: read‑only if permissions lack.
- Microcopy rules:
  - Use “This applies to all agents” in header.
- Accessibility:
  - Keyboard navigation for list and detail panes.
- Variants + anti‑patterns:
  - Variant: compact list for small teams.
  - Anti‑pattern: hidden auto‑publish.
- Example(s):
```yaml
global_rules:
  version: "v3"
  status: "review"
  policies:
    - name: "PII Redaction"
      rule: "Never store SSN or full card numbers."
```

### 2) Agent‑Specific Instructions
- Intent + when to use/avoid:
  - Use for overrides and agent‑scoped instructions.
  - Avoid for global policies.
- Anatomy:
  - Inheritance tree, override chips, conflict banner.
- Layout rules + responsive behavior:
  - Inheritance tree collapses on mobile.
- Interaction rules + motion:
  - Show “inherited from Global Rules” badges.
- States:
  - Standard states from template.
- Microcopy rules:
  - “Overrides apply only to this agent.”
- Accessibility:
  - Tree view accessible with keyboard.
- Variants + anti‑patterns:
  - Anti‑pattern: silent overrides without audit log.
- Example(s):
```yaml
agent_instructions:
  agent: "Billing Bot"
  inherits_from: "global"
  overrides:
    - name: "Tone"
      value: "Formal, concise"
```

### 3) Rule Builder (Plain‑Language + Structured)
- Intent + when to use/avoid:
  - Use to create complex conditional rules.
  - Avoid direct text input without structure.
- Anatomy:
  - Plain‑language cards + structured fields.
- Layout rules + responsive behavior:
  - Split view: natural language on left, structured on right.
  - Mobile shows a toggle between views.
- Interaction rules + motion:
  - Live sync between views.
  - Inline validation and examples next to inputs.
- States:
  - Standard states from template.
- Microcopy rules:
  - “Write it in plain English; we’ll build the rule.”
- Accessibility:
  - Full keyboard support, clearly labeled fields.
- Variants + anti‑patterns:
  - Anti‑pattern: one‑way sync that loses data.
- Example(s):
```yaml
rule_name: "Dr. Jane complex cases cap on Wednesdays"
scope: { provider: "Dr. Jane" }
when:
  weekday: "Wednesday"
  appointment_reason: { any_of: ["Complex disease condition"] }
then:
  limit: { max_appointments_per_day: 3 }
exceptions:
  - if: { patient_status: "urgent" }
    then: { allow: true }
priority: 80
```

### 4) Conflict Detection + Resolution
- Intent + when to use/avoid:
  - Use to detect conflicts across rules and scopes.
- Anatomy:
  - Conflict list, priority, scope, and resolution suggestions.
- Layout rules + responsive behavior:
  - Table on desktop, cards on mobile.
- Interaction rules + motion:
  - One‑click “Resolve” with preview.
- States:
  - Standard states from template.
- Microcopy rules:
  - “This rule conflicts with X at priority Y.”
- Accessibility:
  - Ensure conflict list is screen‑reader friendly.
- Variants + anti‑patterns:
  - Anti‑pattern: hidden conflicts with no warning.
- Example(s):
```yaml
conflict:
  rule_a: "Max 3 complex cases on Wednesday"
  rule_b: "Allow all urgent cases"
  resolution: "Rule B overrides when urgent"
```

### 5) Rule Simulator / Dry Run
- Intent + when to use/avoid:
  - Use to show why rules allow or block.
- Anatomy:
  - Input scenario, output decision, rationale.
- Layout rules + responsive behavior:
  - Scenario inputs above result; mobile stacked.
- Interaction rules + motion:
  - “Explain why” expands rationale.
- States:
  - Standard states from template.
- Microcopy rules:
  - “Allowed because…” or “Blocked because…”
- Accessibility:
  - Results must be announced to screen readers.
- Variants + anti‑patterns:
  - Anti‑pattern: opaque result without rationale.
- Example(s):
```json
{
  "scenario": {
    "provider": "Dr. Jane",
    "weekday": "Wednesday",
    "appointment_reason": "Complex disease condition",
    "patient_status": "urgent"
  },
  "decision": "allowed",
  "because": ["Exception: urgent patient"]
}
```

### 6) Change Review + Publish Gate
- Intent + when to use/avoid:
  - Use for high‑risk updates and governed changes.
- Anatomy:
  - Risk summary, diff, impacted agents, rollback toggle.
- Layout rules + responsive behavior:
  - Two‑column with summary and diff.
- Interaction rules + motion:
  - Require explicit confirmation and typed “Publish.”
- States:
  - Standard states from template.
- Microcopy rules:
  - “Publishing applies immediately unless staged.”
- Accessibility:
  - Confirmations must be keyboard accessible.
- Variants + anti‑patterns:
  - Anti‑pattern: publish without confirmation.
- Example(s):
```yaml
publish_gate:
  risk: "high"
  impacted_agents: 12
  rollback_available: true
```

## Core UI Patterns

### Navigation
- Intent + when to use/avoid:
  - Use for primary sections and flows.
- Anatomy:
  - Top bar, left nav, breadcrumb.
- Layout rules + responsive behavior:
  - Collapsible left nav; bottom nav on mobile.
- Interaction rules + motion:
  - Active state for current location.
- States:
  - Standard states from template.
- Microcopy rules:
  - Use short, familiar labels.
- Accessibility:
  - Skip‑to‑content link.
- Variants + anti‑patterns:
  - Anti‑pattern: hidden navigation with no label.
- Example(s):
```yaml
nav:
  items: ["Dashboard", "Agents", "Rules", "Publish"]
```

### Forms (single + multi‑step)
- Intent + when to use/avoid:
  - Use for data capture and configuration.
- Anatomy:
  - Labels, helper text, validation, progress.
- Layout rules + responsive behavior:
  - One column on mobile; two on desktop if simple.
- Interaction rules + motion:
  - Inline validation; progress steps visible.
- States:
  - Standard states from template.
- Microcopy rules:
  - “Why we need this” helper text.
- Accessibility:
  - Proper label association.
- Variants + anti‑patterns:
  - Anti‑pattern: validation only on submit.
- Example(s):
```yaml
form:
  step: 2
  total_steps: 4
  fields:
    - label: "Agent name"
      helper: "This appears in reports."
```

### Validation
- Intent + when to use/avoid:
  - Use to prevent errors early.
- Anatomy:
  - Inline error message, field highlight.
- Layout rules + responsive behavior:
  - Place errors directly below fields.
- Interaction rules + motion:
  - Show errors after first blur.
- States:
  - Error state required.
- Microcopy rules:
  - Explain how to fix.
- Accessibility:
  - Announce errors to screen readers.
- Variants + anti‑patterns:
  - Anti‑pattern: red text without explanation.
- Example(s):
```yaml
validation:
  field: "Email"
  error: "Enter a valid email like name@example.com."
```

### Data display (table/list/cards)
- Intent + when to use/avoid:
  - Use table for structured data, list for simple items, cards for summaries.
- Anatomy:
  - Header, row, action menu.
- Layout rules + responsive behavior:
  - Tables become cards on mobile.
- Interaction rules + motion:
  - Row hover and quick actions.
- States:
  - Standard states from template.
- Microcopy rules:
  - Column labels must be plain language.
- Accessibility:
  - Table headers with scope.
- Variants + anti‑patterns:
  - Anti‑pattern: horizontal scroll without cues.
- Example(s):
```yaml
table:
  columns: ["Agent", "Status", "Last run"]
  rows: 12
```

### Search / filter / sort
- Intent + when to use/avoid:
  - Use for data sets > 10 items.
- Anatomy:
  - Search input, filters, sort menu.
- Layout rules + responsive behavior:
  - Filter chips wrap on mobile.
- Interaction rules + motion:
  - Debounced search with clear button.
- States:
  - Standard states from template.
- Microcopy rules:
  - “Search by name, ID, or tag.”
- Accessibility:
  - Input label and ARIA for filters.
- Variants + anti‑patterns:
  - Anti‑pattern: filters with no reset.
- Example(s):
```yaml
search:
  placeholder: "Search agents"
```

### Empty / loading / error / success
- Intent + when to use/avoid:
  - Use to guide users when no data or errors.
- Anatomy:
  - Icon, message, next step.
- Layout rules + responsive behavior:
  - Centered message with clear next action.
- Interaction rules + motion:
  - Skeleton for loading.
- States:
  - Standard states from template.
- Microcopy rules:
  - Provide next step and reassurance.
- Accessibility:
  - Readable text and button focus.
- Variants + anti‑patterns:
  - Anti‑pattern: empty state with no action.
- Example(s):
```yaml
empty_state:
  message: "No agents yet."
  action: "Create your first agent"
```

### Confirmations / destructive actions (undo‑first)
- Intent + when to use/avoid:
  - Use for deletions or irreversible changes.
- Anatomy:
  - Confirmation dialog, undo toast.
- Layout rules + responsive behavior:
  - Use modal on desktop; full‑screen sheet on mobile.
- Interaction rules + motion:
  - Provide undo within 10 seconds.
- States:
  - Standard states from template.
- Microcopy rules:
  - “You can undo this.”
- Accessibility:
  - Focus trapped within modal.
- Variants + anti‑patterns:
  - Anti‑pattern: immediate deletion with no undo.
- Example(s):
```yaml
delete:
  action: "Archive agent"
  undo: true
```

### Permissions / roles
- Intent + when to use/avoid:
  - Use for enterprise access control.
- Anatomy:
  - Role list, permission matrix.
- Layout rules + responsive behavior:
  - Matrix scrolls horizontally with cues.
- Interaction rules + motion:
  - Confirm before role changes.
- States:
  - Standard states from template.
- Microcopy rules:
  - “Only admins can publish.”
- Accessibility:
  - Table headers and readable labels.
- Variants + anti‑patterns:
  - Anti‑pattern: permissions hidden behind admin only.
- Example(s):
```yaml
roles:
  - name: "Admin"
    can_publish: true
```

### Onboarding / education
- Intent + when to use/avoid:
  - Use for first‑time guidance and feature discovery.
- Anatomy:
  - Checklist, guided tour, quick wins.
- Layout rules + responsive behavior:
  - Checklist docked on desktop, stacked on mobile.
- Interaction rules + motion:
  - Progress updates after each action.
- States:
  - Standard states from template.
- Microcopy rules:
  - Encourage: “You’re almost done.”
- Accessibility:
  - Skip option always visible.
- Variants + anti‑patterns:
  - Anti‑pattern: forced tour with no skip.
- Example(s):
```yaml
onboarding:
  steps: ["Choose template", "Connect tools", "Test"]
```

## Modal Patterns (8 minimum)

Each modal must specify title/body formulas, action rules, escape rules, focus/keyboard, mobile behavior, anti‑patterns.

### 1) Confirm/Cancel (High Impact)
- Title formula: “Confirm [action]”
- Body formula: “This will [impact]. You can undo within [time].”
- Action rules: primary “Confirm,” secondary “Cancel.”
- Escape rules: ESC closes; overlay click cancels.
- Focus/keyboard: focus on Cancel by default.
- Mobile behavior: full‑screen sheet.
- Anti‑patterns: preselect Confirm.

### 2) Destructive (Undo‑First)
- Title formula: “Archive [item]?”
- Body formula: “This hides it from users. Undo available.”
- Action rules: primary “Archive,” secondary “Cancel.”
- Escape rules: ESC cancels.
- Focus/keyboard: focus on Cancel.
- Mobile behavior: full‑screen sheet.
- Anti‑patterns: irreversible delete without undo.

### 3) Error Recovery
- Title formula: “We couldn’t [action].”
- Body formula: “Here’s what happened. Try again or contact support.”
- Action rules: primary “Retry,” secondary “View details.”
- Escape rules: ESC closes.
- Focus/keyboard: focus on Retry.
- Mobile behavior: stacked actions.
- Anti‑patterns: vague error with no next step.

### 4) Permissions Request
- Title formula: “Allow access to [resource]”
- Body formula: “We need this to [benefit].”
- Action rules: primary “Allow,” secondary “Not now.”
- Escape rules: ESC cancels.
- Focus/keyboard: focus on Allow if non‑destructive.
- Mobile behavior: full‑screen sheet.
- Anti‑patterns: auto‑request without context.

### 5) Tool Connection / OAuth
- Title formula: “Connect to [tool]”
- Body formula: “We’ll open a secure sign‑in.”
- Action rules: primary “Connect,” secondary “Cancel.”
- Escape rules: ESC cancels.
- Focus/keyboard: focus on Connect.
- Mobile behavior: full‑screen sheet.
- Anti‑patterns: no explanation of permissions.

### 6) Preview‑Before‑Publish
- Title formula: “Preview before publish”
- Body formula: “Review changes and confirm.”
- Action rules: primary “Publish,” secondary “Back.”
- Escape rules: ESC cancels.
- Focus/keyboard: focus on Back.
- Mobile behavior: full‑screen sheet.
- Anti‑patterns: publish without preview.

### 7) Unsaved Changes
- Title formula: “You have unsaved changes”
- Body formula: “Save to keep your work.”
- Action rules: primary “Save,” secondary “Discard.”
- Escape rules: ESC cancels.
- Focus/keyboard: focus on Save.
- Mobile behavior: full‑screen sheet.
- Anti‑patterns: silent discard.

### 8) Contextual Help / Glossary
- Title formula: “[Term] explained”
- Body formula: “Plain‑language definition and example.”
- Action rules: primary “Got it,” secondary “Learn more.”
- Escape rules: ESC closes.
- Focus/keyboard: focus on Got it.
- Mobile behavior: full‑screen sheet.
- Anti‑patterns: jargon without definition.

## Voice‑Agent‑Builder Patterns (10 minimum)

### 1) Template Gallery
- Intent + when to use/avoid:
  - Use for starting points and speed.
- Anatomy:
  - Cards with title, goal, risk level, time to publish.
- Layout rules + responsive behavior:
  - 3‑up grid desktop, 1‑up mobile.
- Interaction rules + motion:
  - Hover reveals key highlights.
- States:
  - Standard states from template.
- Microcopy rules:
  - “Best for: …”
- Accessibility:
  - Card focus and selection.
- Variants + anti‑patterns:
  - Anti‑pattern: templates without outcomes.
- Example(s):
```yaml
template:
  name: "Appointment Scheduler"
  time_to_publish: "15 minutes"
```

### 2) Guided Wizard (progress + safe defaults)
- Intent + when to use/avoid:
  - Use for complex setup with safe defaults.
- Anatomy:
  - Steps, progress bar, summary panel.
- Layout rules + responsive behavior:
  - Stepper left, content right; stacked on mobile.
- Interaction rules + motion:
  - Save‑as‑draft after each step.
- States:
  - Standard states from template.
- Microcopy rules:
  - “You can change this later.”
- Accessibility:
  - Keyboard navigation across steps.
- Variants + anti‑patterns:
  - Anti‑pattern: no progress indicator.
- Example(s):
```yaml
wizard:
  steps: ["Choose template", "Connect tools", "Test", "Publish"]
```

### 3) Simple → Advanced Toggle
- Intent + when to use/avoid:
  - Use to reveal complexity without blocking simple users.
- Anatomy:
  - Toggle, advanced panel, explanation.
- Layout rules + responsive behavior:
  - Toggle at top of section.
- Interaction rules + motion:
  - Smooth expand with reduced motion support.
- States:
  - Standard states from template.
- Microcopy rules:
  - “Advanced shows optional controls.”
- Accessibility:
  - Toggle labels and focus.
- Variants + anti‑patterns:
  - Anti‑pattern: advanced required to finish.
- Example(s):
```yaml
toggle:
  simple: true
  advanced: false
```

### 4) Inline Glossary
- Intent + when to use/avoid:
  - Use to define jargon inline.
- Anatomy:
  - Underlined term, hover/click tooltip.
- Layout rules + responsive behavior:
  - Tooltip becomes drawer on mobile.
- Interaction rules + motion:
  - Tap to open, tap outside to close.
- States:
  - Standard states from template.
- Microcopy rules:
  - One‑sentence definition.
- Accessibility:
  - Keyboard and screen reader support.
- Variants + anti‑patterns:
  - Anti‑pattern: hidden definitions only in docs.
- Example(s):
```yaml
glossary:
  term: "Fallback"
  definition: "What the agent does when it is unsure."
```

### 5) Tool Picker Cards (with risks)
- Intent + when to use/avoid:
  - Use to connect tools safely.
- Anatomy:
  - Tool card, permission summary, risk badge.
- Layout rules + responsive behavior:
  - Cards in a grid; single column on mobile.
- Interaction rules + motion:
  - Clear “What data is shared” panel.
- States:
  - Standard states from template.
- Microcopy rules:
  - “This tool can access: …”
- Accessibility:
  - Card selection via keyboard.
- Variants + anti‑patterns:
  - Anti‑pattern: hidden risk details.
- Example(s):
```yaml
tool:
  name: "Calendar API"
  risk: "Accesses appointment data"
```

### 6) Conversation Flow (happy + fallback)
- Intent + when to use/avoid:
  - Use to define flows and fallback behavior.
- Anatomy:
  - Nodes, edges, fallback node.
- Layout rules + responsive behavior:
  - Canvas with list view fallback for mobile.
  - Chat interfaces place the input below the conversation window.
  - Optional typed input must be hidden behind a “Type Instead” link that reveals
  the input on click. When revealed, the input replaces the link.
  - When scheduling via chat, show a calendar preview panel with the proposed slot.
- When optional inputs are revealed, focus them automatically.
- Interaction rules + motion:
  - Drag to connect, click to edit.
- States:
  - Standard states from template.
- Microcopy rules:
  - “If user is unsure, say…”
  - Transcript formatting: message title in medium grey, speaker label in light
    grey, dialog in black. Title is italic.
- Accessibility:
  - Provide list view and keyboard editing.
- Variants + anti‑patterns:
  - Anti‑pattern: no fallback node.
- Example(s):
```yaml
flow:
  happy_path: ["Greet", "Collect info", "Confirm"]
  fallback: "Ask for clarification"
```

### 7) Test Simulator (transcripts + debugging)
- Intent + when to use/avoid:
  - Use to test before publish.
- Anatomy:
  - Transcript panel, debug logs, replay controls.
- Layout rules + responsive behavior:
  - Split view; stack on mobile.
- Interaction rules + motion:
  - Highlight errors inline.
- States:
  - Standard states from template.
- Microcopy rules:
  - “Replay with last settings.”
- Accessibility:
  - Screen reader friendly transcript.
- Variants + anti‑patterns:
  - Anti‑pattern: tests without logs.
- Example(s):
```yaml
simulator:
  transcript: ["User: I need help", "Agent: Sure, tell me more"]
```

### 8) Error Translation (plain language + fix)
- Intent + when to use/avoid:
  - Use to explain system errors in plain language.
- Anatomy:
  - Error summary, cause, fix steps.
- Layout rules + responsive behavior:
  - Inline banner with expandable details.
- Interaction rules + motion:
  - “Try again” primary action.
- States:
  - Standard states from template.
- Microcopy rules:
  - No jargon; include fix.
- Accessibility:
  - Announce errors to screen readers.
- Variants + anti‑patterns:
  - Anti‑pattern: raw error codes.
- Example(s):
```yaml
error_translation:
  error: "Tool connection failed"
  fix: "Reconnect and approve permissions."
```

### 9) Publish Checklist (blocked items)
- Intent + when to use/avoid:
  - Use to ensure readiness before publishing.
- Anatomy:
  - Checklist with blockers and owner.
- Layout rules + responsive behavior:
  - Checklist on side panel; mobile stacked.
- Interaction rules + motion:
  - Blockers cannot be overridden without admin.
- States:
  - Standard states from template.
- Microcopy rules:
  - “Blocked because…”
- Accessibility:
  - Clear labels and status.
- Variants + anti‑patterns:
  - Anti‑pattern: publish without checklist.
- Example(s):
```yaml
publish_checklist:
  items:
    - name: "Tool connected"
      status: "blocked"
```

### 10) Versioning / Undo / Restore
- Intent + when to use/avoid:
  - Use to maintain change safety.
- Anatomy:
  - Version list, diff view, restore action.
- Layout rules + responsive behavior:
  - List + details; stack on mobile.
- Interaction rules + motion:
  - Confirm restore with preview.
- States:
  - Standard states from template.
- Microcopy rules:
  - “Restore creates a new version.”
- Accessibility:
  - Keyboard navigation in history list.
- Variants + anti‑patterns:
  - Anti‑pattern: restore without confirmation.
- Example(s):
```yaml
versioning:
  current: "v12"
  previous: "v11"
```

### 11) Human Handoff
- Intent + when to use/avoid:
  - Use when agent confidence is low.
- Anatomy:
  - Trigger rules, escalation path, summary handoff.
- Layout rules + responsive behavior:
  - Summary card pinned on top.
- Interaction rules + motion:
  - Confirm handoff; log details.
- States:
  - Standard states from template.
- Microcopy rules:
  - “Connecting you to a human now.”
- Accessibility:
  - Clear status updates.
- Variants + anti‑patterns:
  - Anti‑pattern: hidden handoff.
- Example(s):
```yaml
handoff:
  trigger: "Low confidence"
  destination: "Support queue"
```

### 12) Safety Rails (PII + confirmations)
- Intent + when to use/avoid:
  - Use to protect sensitive data and actions.
- Anatomy:
  - PII warning, confirmation prompt.
- Layout rules + responsive behavior:
  - Inline warnings near sensitive fields.
- Interaction rules + motion:
  - Require explicit confirmation.
- States:
  - Standard states from template.
- Microcopy rules:
  - “Do not enter SSNs.”
- Accessibility:
  - Readable warnings and focus.
- Variants + anti‑patterns:
  - Anti‑pattern: no warning for sensitive data.
- Example(s):
```yaml
safety:
  pii_warning: true
```

## Demo Wow Moments (minimum 3)

Include these in demos and pattern guidance:
1) Live Rule Simulator: type a scenario and get a clear “Allowed/Blocked” with explanation and fix suggestions.
2) One‑click Rollback Preview: show diff, restore, and confirm in under 10 seconds.
3) Guided Publish Readiness: checklist with blockers, auto‑fix suggestions, and confidence score.

## Enterprise‑Demo Readiness Gate (Hard Gate)

Before output is final, verify:
- Premium visual rules are applied (grid, spacing, type, elevation).
- Interactions include hover/focus/press and motion + reduced motion.
- States include loading, empty, error, success, disabled.
- Roles, audit log, versioning, and publish gates exist where relevant.
- Grandma‑usable defaults are present and explicit.

## Example Full Pattern Output (Short Form)

```yaml
pattern: "Tool Connection Modal"
intent: "Connect a tool with clear permissions"
when_to_use: "When OAuth or API access is required"
avoid: "For simple toggles or local settings"
anatomy: ["Title", "Permission summary", "Primary action", "Secondary action"]
layout: "Modal desktop, full‑screen sheet mobile"
responsive: "Stacked actions on mobile"
interaction: "Primary Connect, secondary Cancel, ESC closes"
motion: "150 ms fade"
states: ["loading", "error", "success", "disabled"]
microcopy: "Explain what data is shared"
accessibility: "Focus trap, keyboard support"
variants: ["Read‑only access", "Admin‑only"]
anti_patterns: ["No permission summary"]
examples:
  - "Connect Calendar: shares event names only"
```
