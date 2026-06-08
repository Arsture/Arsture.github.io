# Design

## Source of truth
- Status: Active
- Last refreshed: 2026-06-08
- Primary product surfaces: `index.html` personal CV/portfolio site on GitHub Pages.
- Evidence reviewed:
  - `Lab12 Vibe Coding with GitHub Pages.pdf`
  - `assets/profile.jpg`, `assets/cv.pdf`
  - Public Notion CV source provided by user
  - Minimal portfolio inspiration search: Gallereee minimal portfolio collection, A1 minimal portfolio examples, Cole personal site, Minimalio graphic designer portfolio examples.

## Brand
- Personality: editorial, restrained, sharp, curious, founder-builder, not startup-template glossy.
- Trust signals: real portrait, downloadable CV PDF, public Notion CV, precise dates/roles, clean contact links.
- Avoid: AI SaaS gradients, glassmorphism cards, emoji-heavy marketing sections, generic “hero landing page” look, excessive shadows, inflated copy.

## Product goals
- Goals:
  - Pass Lab12/HW6 requirements.
  - Feel like a sober CV/portfolio rather than an AI-generated template.
  - Make resume facts scannable for TA/reviewer and future professional readers.
- Non-goals:
  - No framework, JS app, animations, backend, or paid API.
  - No fake awards/projects or over-designed brand system.
- Success signals:
  - URL works on GitHub Pages.
  - Required sections are obvious.
  - Visual impression: calm, intentional, human, CV-ready.

## Personas and jobs
- Primary personas:
  - Lab TA checking required contents quickly.
  - Recruiter/collaborator scanning background and links.
  - Peer/classmate viewing the website on mobile.
- User jobs:
  - Verify identity/contact/CV quickly.
  - Understand projects and interests.
  - Download CV PDF or open Notion CV.
- Key contexts of use: mobile browser, desktop browser, external review after eTL submission.

## Information architecture
- Primary navigation: About, CV, Work, Courses, Contact, AI Usage.
- Core routes/screens: single-page anchored sections.
- Content hierarchy:
  1. Name, role line, portrait, core contact/actions.
  2. About/profile facts.
  3. CV timeline and download.
  4. Selected work/activity entries.
  5. Planned/interested courses.
  6. Contact and AI usage.

## Design principles
- Principle 1: Content first; decoration must not compete with CV facts.
- Principle 2: Editorial restraint; use whitespace, rules, and typography instead of gradients.
- Principle 3: Scannability; section labels, dates, and roles should be easy to parse.
- Tradeoffs: Less visually “flashy,” but more credible and less AI-template-like.

## Visual language
- Color: warm paper background, ink text, muted gray, one restrained blue accent.
- Typography: system sans for body; serif display for name/headings to create editorial feel without external font dependency.
- Spacing/layout rhythm: wide desktop grid, narrow readable text columns, strong horizontal rules.
- Shape/radius/elevation: almost flat; small radius only on photo/buttons; no glass cards.
- Motion: none beyond native anchor navigation; preserve reduced-motion override.
- Imagery/iconography: real portrait as the primary visual anchor; no stock icons.

## Components
- Existing components to reuse: single `index.html`, local `assets/profile.jpg`, `assets/cv.pdf`.
- New/changed components: editorial masthead, resume rows, work rows, quiet link buttons.
- Variants and states: focus-visible outlines; hover as underline/background only.
- Token/component ownership: CSS custom properties inside `index.html`.

## Accessibility
- Target standard: WCAG AA-oriented basics.
- Keyboard/focus behavior: skip link to focusable `main`, visible focus outlines.
- Contrast/readability: high contrast ink-on-paper palette.
- Screen-reader semantics: landmarks, headings, descriptive links, photo alt.
- Reduced motion and sensory considerations: reduced-motion media query retained.

## Responsive behavior
- Supported breakpoints/devices: mobile, tablet, desktop.
- Layout adaptations: desktop two-column masthead and content grids collapse to one column.
- Touch/hover differences: links/buttons remain tappable; hover effects are non-essential.

## Interaction states
- Loading: static HTML, no loading states.
- Empty: no empty sections.
- Error: external links open independently; downloadable CV is local asset.
- Success: visible URL, functioning links/download.
- Disabled: none.
- Offline/slow network: core page loads without external fonts/scripts.

## Content voice
- Tone: concise, factual, bilingual where useful, human but not cute.
- Terminology: use “CV”, “Selected Work”, “Planned / Interested Courses”.
- Microcopy rules: avoid generic superlatives; label inferred courses as planned/interested.

## Implementation constraints
- Framework/styling system: static `index.html` with embedded CSS.
- Design-token constraints: use local CSS variables only.
- Performance constraints: no JS, no external font requests; image/PDF local assets.
- Compatibility constraints: GitHub Pages root deployment.
- Test/screenshot expectations: basic content/link checks before push; no heavy QA unless requested.

## Open questions
- [ ] Whether to later split CSS into `assets/style.css` if this portfolio grows beyond Lab12 / owner: user / impact: maintainability.
