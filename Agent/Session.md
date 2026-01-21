## 2026-01-21

**Current Goal**
- Build an Astro-based static landing page for Pisys.Net: “Free Cyber Risk Audit for UK Businesses” following Problem → Promise → Proof → Process → Prompt.

**Plan**
- Scaffold Astro project and base layout using Pisys palette.
- Build page sections/components, forms, and content files (SEO + AI context).
- Add Web3Forms handling, robots/sitemap approach, and GitHub Pages workflow.
- Document setup in README and keep Session.md updated each iteration.

**Repo Map**
- prompt.md — project brief
- Agent/instructions.md — (empty)
- Agent/theme.md — visual system
- Agent/agent.md — build constraints
- Agent/Session.md — change log (this file)
- astro.config.mjs, tsconfig.json — Astro project config
- package.json, package-lock.json, node_modules — project dependencies
- public/ — static assets placeholder
- src/ — Astro starter source (to be replaced)
- .gitignore, .vscode — defaults from Astro starter
- .github/workflows/deploy.yml — GitHub Pages deployment workflow

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
- `ASTRO_TELEMETRY_DISABLED=1 npm run build` — passes, outputs static site in `dist/`.
