# agent.md
> Agent rules for building the Pisys.Net “Free Cyber Risk Audit” landing page  
> This file defines how Codex should work: quality bar, constraints, and implementation standards.

## 1) Mission
Build a single-page, static, high-conversion landing page for **Pisys.Net** that persuades UK business decision-makers to book a **Free Cyber Risk Audit**.

The page must be:
- Reader-first (scannable, calm, practical)
- SEO-safe (HTML-first, clean metadata)
- AI-ready (explicit purpose + definitions + audience context in repo)
- Dev-friendly (components, clear structure, easy to change)

---

## 2) Non-negotiable constraints
- Use **Astro** and output static HTML (no SPA behavior).
- Use the Pisys.Net palette:
  - Primary Blue `#013753`
  - Accent Red `#C62A20`
- Follow the page flow: **Problem → Promise → Proof → Process → Prompt**.
- Keep friction low: form embedded on the page, minimal fields.
- No fear-mongering, no sensational claims, no “hacker” aesthetics.
- No fabricated certifications or claims beyond what is provided in copy.
- No third-party trackers by default (no GA, no Hotjar) unless explicitly requested.

---

## 3) Quality bar (definition of done)
### UX / Conversion
- Primary CTA visible above the fold on mobile and desktop.
- Repeated CTA appears again before the form and inside the form section.
- Micro-reassurance under CTA must be present.
- “What happens next” is clear after form submission.
- Copy is easy to skim: strong hierarchy, lists, short paragraphs.

### Technical
- Lighthouse best-effort targets:
  - Performance 90+
  - Accessibility 95+
  - Best Practices 95+
  - SEO 95+
- Minimal JS; only add what’s necessary (e.g., form success handling).
- Semantic HTML, proper heading order, labels tied to inputs.
- No console errors, no broken links, no placeholder lorem ipsum.

### SEO / AI
- Title/meta/OG tags present and driven from `src/content/seo.json`.
- Canonical URL is configurable.
- Include JSON-LD (LocalBusiness + Service) with conservative claims.
- Add AI context file `src/content/ai-context.json` (purpose, audience, definition, takeaways).
- No keyword stuffing; plain language.

---

## 4) Code standards
- Prefer clarity over cleverness.
- Componentize sections (Hero, Value, Proof, Process, Form, Footer).
- Keep styling consistent (Tailwind OR CSS, not both mixed randomly).
- Use CSS variables or Tailwind config for brand colors.
- Avoid magic numbers; use consistent spacing scale.
- Keep content copy centralized where possible so non-dev edits are easy.

---

## 5) Accessibility standards
- Every input must have a visible `<label>`.
- Provide `aria-live` for form success message.
- Provide error messaging structure (even if basic).
- Ensure focus states are clearly visible.
- Buttons must be at least ~44px tall on touch devices.
- Color contrast must meet WCAG AA.

---

## 6) Form handling rules (Web3Forms)
- Embed a standard HTML `<form>` that POSTs to Web3Forms.
- Treat the access key as a config value (easy to edit).
- Implement a clean, inline success state:
  - On success: hide form fields or disable submit and show confirmation text.
  - Message: “Thanks - we’ll email within 1 business day to arrange the short qualification call.”
- Add privacy micro-line:
  - “We’ll only use your details to arrange the audit.”
- Do NOT implement deprecated honeypot approach.
- Keep Turnstile integration optional; do not block launch on it.

---

## 7) Content integrity rules
- Use the provided copy as the source of truth.
- Small edits allowed only to improve grammar/flow; do not change meaning.
- Do not add new guarantees (e.g., “insurance approved”) or hard promises.
- Do not add invented case studies, stats, or client logos.
- Trust extensions must match exactly what’s provided:
  - ISO 27001, ISO 9001, Cyber Essentials Plus, UK-based cyber professionals, SME-focused delivery

---

## 8) File outputs required
The build must produce, at minimum:
- `src/pages/index.astro`
- `src/layouts/BaseLayout.astro`
- `src/components/*.astro` (section components)
- `src/content/seo.json`
- `src/content/ai-context.json`
- `public/robots.txt`
- GitHub Pages workflow file
- `README.md` with setup + deployment notes

---

## 9) Review checklist (run before declaring complete)
- [ ] Sections appear in correct order and match copy
- [ ] CTA button works (scrolls to form section)
- [ ] Form submits and success state works
- [ ] Mobile view looks premium and uncluttered
- [ ] Metadata present and correct
- [ ] JSON-LD valid (no spammy fields)
- [ ] No accessibility regressions (labels, focus, contrast)
- [ ] GitHub Pages deploy workflow present

---
End of `agent.md`
