# 6f STYLE GUIDE

**Single source of truth for LLMs & vibe-coded apps**

Keep every 6f project looking identical. Always default to the hosted CSS.

## 1. Core Philosophy

High-density, dark-mode-first. Precision, mathematical contrast, “clean desk” aesthetic.\
**Semantic HTML + existing component classes first.**\
Utility wins, but **never hard-code colors, spacing, or fonts** — always use `--6f-*` tokens.

## 2. Foundation (Hosted – Import in This Exact Order)

```html
<html lang="en" data-theme="dark">
<head>
  <!-- 6f Foundation – DO NOT CHANGE ORDER -->
  <link rel="stylesheet" href="https://static.6f.md/tokens.css">
  <link rel="stylesheet" href="https://static.6f.md/base.css">
  <link rel="stylesheet" href="https://static.6f.md/components.css">
  
  <!-- Project-specific overrides (optional) -->
  <style>
    :root { --6f-color-accent: #60c8d8; }
  </style>
</head>
```

### data-theme="dark" on &lt;html&gt; is required.

## 3. Tokens (Use These Only)

Grayscale --6f-gray-0 (#000000) → --6f-gray-1000 (#ffffff)

Semantic --6f-color-bg, --6f-color-bg-raised, --6f-color-bg-elevated --6f-color-text, --6f-color-text-secondary, --6f-color-text-muted --6f-color-accent (override in project.css), --6f-color-border, status colors

Typography & Spacing --6f-font-sans / serif / mono --6f-text-xs → --6f-text-4xl --6f-space-1 → --6f-space-24 (use exclusively)

Rule: No raw px, rem, #hex, or rgb() outside of tokens.

## 4. Components (Use These Aggressively)

Prefer component classes over any custom CSS. Start here — do not invent new classes unless the existing ones cannot solve the problem.

```
Layout: .site-nav, .section, .section-label, .card
Buttons: button, .btn, .btn-primary, .btn-secondary, .btn-ghost, .btn-sm
Forms: .form-stack, .form-field, native input/textarea/select
Content: .callout, .tag, .badge, .kv-list, .tag-list
Feedback: .toast, .skeleton, .avatar
```

Best practice: Reach for .card or .form-stack first.

## 5. Best Practices (Critical)

Classes first — Use existing 6f component classes aggressively. Avoid inline style= attributes and custom classes whenever possible. Tokens only — All spacing, typography, and colors must come from --6f-\* variables. High-density mindset — use smaller space tokens. Clean desk: minimal borders, clear hierarchy, no fluff. Dark mode only (data-theme="dark" required). If you must write custom CSS, keep it minimal, scoped, and 100% token-based.
