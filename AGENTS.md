# Agent instructions

This repository is a small Hebrew educational Jekyll site published by GitHub Pages.

## Content locations

- Top-level pages belong at the repository root, for example `index.md` and `about.md`.
- Lesson pages belong in `lessons/`.
- The lessons landing page is `lessons/index.md`.
- Small local style overrides belong in `_sass/custom/custom.scss`.
- Deployment is controlled by `.github/workflows/pages.yml`.

## Required front matter

Every page must include Jekyll front matter. Use this shape for regular pages:

```yaml
---
layout: default
title: Page title
nav_order: 4
---
```

Use this shape for lesson pages:

```yaml
---
layout: default
title: Lesson title
parent: שיעורים
nav_order: 3
permalink: /lessons/example/
---
```

## Hebrew and directionality

- The site is primarily Hebrew and right-to-left.
- Body copy, headings, navigation and tables should be written for RTL reading.
- Code blocks, terminal commands, filenames, paths, URLs, YAML keys and inline code stay left-to-right.
- Preserve the local RTL/LTR handling in `_sass/custom/custom.scss`.

## Theme policy

- The site uses the pinned remote theme `just-the-docs/just-the-docs@v0.12.0`.
- Do not fork, clone or copy the complete theme into this repository.
- Do not copy theme source files unless a small, specific override is genuinely required.
- Keep local customizations minimal and easy for a teacher to maintain.

## Privacy and publishing

- Do not commit private student, family, staff or school data.
- Do not commit secrets, tokens, passwords, private keys or internal documents.
- Every meaningful change must leave the GitHub Pages build passing.
- If a deployment fails, fix the repository content or configuration rather than only describing the failure.

## Workflow boundaries

- Local WSL, Bundler and Jekyll serving are not part of this workshop repository's required workflow.
- Do not run `wsl`, `bundle`, `jekyll`, `ruby`, `gem` or `bundle exec jekyll serve` as part of normal work here.
- After this initial setup, future agents can read the repository but must not commit, pull or push unless explicitly asked.
