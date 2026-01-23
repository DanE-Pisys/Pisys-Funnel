# prompt.md
> Entry-point prompt for Codex CLI  
> Purpose: tell Codex what to build, where the rules are, and how to track progress in Session.md (since session IDs aren’t supported)

## How to use
Run Codex with this file as the primary instruction context.  
Codex must read the referenced docs in `/agent/` before making changes.

---

## Codex System Prompt (paste as-is)

You are working in a repository that contains an `/agent/` folder with the project’s operating instructions.

### Mandatory reading (in this order)
1. `/agent/instructions.md` - requirements, copy, deliverables, acceptance checklist
2. `/agent/theme.md` - design system, palette, UI rules
3. `/agent/agent.md` - quality bar, constraints, coding standards

### Primary objective
Build a static, high-conversion landing page for Pisys.Net titled:
**“Free Cyber Risk Audit for UK Businesses”**

Use Astro for static output, GitHub Pages for hosting, and Web3Forms for submissions. The page must follow:
**Problem → Promise → Proof → Process → Prompt**

### IMPORTANT: Session tracking (required)
Create a file at: `/agent/Session.md`

Because Codex has no session IDs, you MUST maintain `Session.md` as a running change log and current state document.

#### `Session.md` must include these sections
1. **Current Goal** (1–3 lines)
2. **Plan** (short checklist)
3. **Repo Map** (key files created/modified)
4. **Decisions** (tech + design choices, e.g., Tailwind vs CSS)
5. **Changes This Iteration** (what you changed and why)
6. **Next Steps** (what remains)
7. **Validation** (manual checks done; note anything unverified)

#### Update rules for `Session.md`
- Update `Session.md` **after every change** that modifies code/content/config.
- Treat it as canonical truth for project progress.
- Keep entries concise and factual.
- Do not remove old entries; append iteration notes under a dated heading.
  - Use UTC date format: `## 2026-01-21`

### Workflow rules
- Implement in small, safe steps.
- After each step, update `Session.md`.
- Do not invent facts, certifications, statistics, client logos, or testimonials.
- Keep copy aligned with `/agent/instructions.md` (minor grammar improvements allowed; meaning must not change).
- Minimal JS; HTML-first; accessible forms with labels and focus states.
- Use brand colors:
  - Primary Blue `#013753`
  - Accent Red `#C62A20`

### Deliverables to produce
- Astro project with `src/pages/index.astro`, layout, components, metadata JSON, and a GitHub Pages deploy workflow.
- `public/robots.txt` (and sitemap solution)
- `README.md` with local dev + deploy notes
- `/agent/Session.md` maintained as described above.

### Definition of done
The acceptance checklist in `/agent/instructions.md` must be satisfied.
If anything cannot be verified locally (e.g., deploy), document it under **Validation** in `Session.md`.

Now begin by:
1) creating `/agent/Session.md` with an initial plan,
2) scaffolding the Astro project,
3) building the page structure and components,
4) wiring Web3Forms submission + success state,
5) adding SEO + JSON-LD,
6) adding GitHub Pages deployment workflow,
updating `Session.md` after each meaningful change.

---

End of `prompt.md`
