## 2026-01-21

**Current Goal**
- Build an Astro-based static landing page for Pisys.Net: “Free Cyber Risk Audit for UK Businesses” following Problem → Promise → Proof → Process → Prompt.

**Plan**
- Scaffold Astro project and base layout using Pisys palette.
- Build page sections/components, forms, and content files (SEO + AI context).
- Add Web3Forms handling, robots/sitemap approach, and GitHub Pages workflow.
- Document setup in README and keep Session.md updated each iteration.

**Repo Map**
- prompt.md - project brief
- Agent/instructions.md - (empty)
- Agent/theme.md - visual system
- Agent/agent.md - build constraints
- Agent/Session.md - change log (this file)
- astro.config.mjs, tsconfig.json - Astro project config
- package.json, package-lock.json, node_modules - project dependencies
- public/ - static assets placeholder
- src/ - Astro starter source (to be replaced)
- .gitignore, .vscode - defaults from Astro starter
- .github/workflows/deploy.yml - GitHub Pages deployment workflow

**Decisions**
- Use Astro with Tailwind for styling; define brand tokens via CSS variables/Tailwind config.
- Use Web3Forms POST with inline success state; no third-party trackers.
- Disable Astro telemetry via env var when running commands in this environment (permission issue writing ~/.config/astro).

**Changes This Iteration**
- Created Session.md with initial goal, plan, repo map, and decisions.
- Scaffolded Astro minimal starter (npm create astro@latest), moved into repo root, removed temporary folder.
- Added Tailwind v4 integration and global brand tokens.
- Built BaseLayout with meta defaults, JSON-LD support, and imported global styles.
- Created landing page sections/components (Hero, Value, Promise/Proof, Process, Form, Footer trust) following the required flow.
- Added SEO and AI context content files, placeholder sitemap/robots, GitHub Pages workflow, and rewritten README.
- Renamed package to `pisys-funnel`; build succeeds with telemetry disabled env.
- Set canonical domain to `https://landing.pisys.net` across config, SEO, robots, and sitemap.
- Added logo strip component and ensured form CTA text styling; rebuilt successfully.
- Updated logo strip to use provided assets (Pisys, Cyber Essentials Plus, ISO 27001, ISO 9001) and icons for UK-based team + SME delivery; reinforced CTA text color and rebuilt.
- Moved Pisys logo into Hero header and removed it from the trust strip; rebuilt.
- Forced btn-primary link color to white to address missing text in some contexts; rebuilt successfully.
- Increased specificity with !important on btn-primary to override inherited link color rules; rebuilt.
- Form success handling now disables fields and changes CTA text to meet “hide/disable after success” requirement; rebuilt.
- Added supplied logos to footer trust section alongside icons; rebuilt.
- Visual polish: hero ambient gradients, section eyebrows/heading accents, upgraded cards, consistent accent panels; rebuilt after resolving Tailwind utility error.
- Updated hero copy to match provided wording (emotional hook and supporting line across devices, Microsoft 365, backups); rebuilt.
- Linked trust badges (top and footer) to https://trust.pisys.net; rebuilt.
- Form refinements: moved Web3Forms key to PUBLIC env fallback, made role/focus optional, added aria-live + focus handling on success/error to reduce friction; rebuilt.
- Added CNAME for landing.pisys.net and an OG image SVG asset, set ogImage URL in seo.json; rebuilt.
- Tightened desktop spacing (narrower container, reduced section padding, smaller gaps, hero padding tweaked) for a denser funnel feel; rebuilt.
- Added smooth scrolling for anchor jumps with reduced-motion fallback; rebuilt.
- CRO improvements: env-guarded Web3Forms key, form still usable with edit/resend, company/role/focus optional, focus/aria tweaks, helper text; hero logo lazy-loaded; rebuilt.
- Raised contrast for process cards and inputs; wrapped form in a bordered shell for clearer boundaries; rebuilt.

**Next Steps**
- Replace placeholder Web3Forms access key in `src/components/PromptForm.astro`.
- Set the real canonical URL in `astro.config.mjs`, `src/content/seo.json`, robots.txt, and sitemap.xml.
- Content/QC pass: check headings order, contrast, and copy against any provided brand copy if supplied later.
- Optional: add OG image asset once provided.

**Validation**
- `ASTRO_TELEMETRY_DISABLED=1 npm run build` - passes, outputs static site in `dist/`.

## 2026-01-22

**Plan**
- Audit current CTAs, proof, process, and trust sections to map required edits vs director feedback.
- Update hero copy, CTA wording, social norm, “scope confirmation call” process, and confidentiality cue near the form.
- Consolidate “what you’ll receive” into a single section and trim page length while preserving the persuasion flow.
- Add a sample (redacted) report artefact and refresh the trust/credentials section per guidelines.
- Align metadata/AI context with the new “board-ready 1-page risk snapshot” positioning, then run build check.

**Changes**
- Rewrote Hero messaging to match director copy (board-ready 1-page snapshot, risk-reversal line) and swapped all hero CTAs to “Request my risk snapshot” for lower friction (src/components/Hero.astro).
- Removed duplicated hero “What you’ll receive” card to shorten the fold; added concise scope chips and embedded the social norm reassurance near the primary CTA (src/components/Hero.astro).
- Kept credentials cue in a compact card to maintain authority without adding length (src/components/Hero.astro).
- Consolidated deliverables into a single “What this audit will show you” panel and expanded bullets to cover board snapshot, 30/60/90 actions, and remote delivery while retaining problem framing (src/components/Value.astro).
- Reframed the process to “scope confirmation call,” refreshed step names/timings, and aligned CTA copy (src/components/Process.astro).
- Added a confidentiality cue, swapped form CTA/microcopy to “Request my risk snapshot,” and updated success language to reference the scope confirmation call (src/components/PromptForm.astro).
- Rebuilt the Promise/Proof area with a redacted sample report artefact, embedded the social norm reassurance, and streamlined supporting bullets to avoid duplicate deliverables (src/components/Promise.astro).
- Reworked trust sections to remove “Trusted alignment,” switch to logos-only credentials rows, and updated footer CTA to the new wording (src/components/Logos.astro, src/components/FooterTrust.astro).
- Updated SEO and AI context to emphasize the board-ready 1-page risk snapshot positioning and the scope confirmation call step (src/content/seo.json, src/content/ai-context.json).
- Ran `ASTRO_TELEMETRY_DISABLED=1 npm run build` to confirm the updated copy and components still compile cleanly.
- Reduced scroll depth by tightening section padding globally (py 8/10/12), shrinking hero/form/process/FAQ spacing, and trimming card padding where possible while keeping hierarchy (global.css, Hero.astro, Value.astro, Promise.astro, Process.astro, PromptForm.astro, FAQ.astro, FooterTrust.astro). Build re-verified.
- Consolidation pass: removed the separate Value section from the page flow, merged “What this audit will show you” with the proof/sample report, moved the form directly after proof, trimmed FAQ to two items, and set the process to a compact 4-step scope-confirmation flow (index.astro, Promise.astro, Process.astro, FAQ.astro).
- Re-ran `ASTRO_TELEMETRY_DISABLED=1 npm run build` after consolidation to verify output.
- Replaced all em dashes with plain punctuation across public copy and docs to avoid AI-ish tone (Hero.astro, Value.astro, Promise.astro, PromptForm.astro, seo.json, agent.md, Session.md, prompt.md). Build rechecked.
- Populated the sample report artefact with redacted but readable content (risk score, top exposures, readiness notes, and actionable cards) so it no longer appears blank while still conveying the board snapshot format (src/components/Promise.astro).
- Simplified the sample report layout: wider, fewer sections (overall score, top exposures, readiness, three mini-cards) for a cleaner, less vertical view while keeping actionable detail (src/components/Promise.astro).
- Further compressed the sample report (score + two short lists) to cut height, matching the “no long sections” request (src/components/Promise.astro). 
- Moved Process above the submission form in the page flow (src/pages/index.astro).
- Added conversion tweaks: hero microcopy “We reply within one business day,” a “What you’ll get” trio under the form header, and a mobile-only sticky CTA bar appearing after 30% scroll (Hero.astro, PromptForm.astro, StickyCTA.astro, index.astro). FAQ restored to fuller set (FAQ.astro). Build rechecked.

**What remains**
- Final review against director checklist; ready for handover unless further tweaks are requested.
- Check scroll depth (target ≤2 desktop, ≤3 mobile viewports) after trims.
- Replace placeholder Web3Forms access key in src/components/PromptForm.astro.
