# Pisys.Net – Free Cyber Risk Audit Landing Page

Static Astro site for the Pisys.Net offer “Free Cyber Risk Audit for UK Businesses,” following the Problem → Promise → Proof → Process → Prompt flow.

## Prerequisites
- Node.js 20+ and npm.
- Web3Forms access key (replace the placeholder in `src/components/PromptForm.astro`).

## Local development
```sh
npm install
npm run dev
# open http://localhost:4321
```

## Build
```sh
npm run build
npm run preview   # optional validation of the build output
```

## Configuration to update
- `astro.config.mjs` → set `site` to the live canonical URL (also used for sitemap/meta).
- `src/content/seo.json` → update `canonical`, `title/description`, and `serviceArea` if needed.
- `src/components/PromptForm.astro` → replace `YOUR_WEB3FORMS_ACCESS_KEY` with the real key.
- `public/robots.txt` and `public/sitemap.xml` → set the correct domain paths.

## Deployment (GitHub Pages)
1. Push to GitHub with Pages enabled for the repository.
2. The workflow `.github/workflows/deploy.yml` builds the site and publishes `dist/` using GitHub Pages actions.
3. If your Pages site uses a project path (e.g., `/repo-name/`), set the `site` value in `astro.config.mjs` and `canonical` in `src/content/seo.json` accordingly.

## Content & structure
- Page sections live as Astro components in `src/components/`.
- Metadata lives in `src/content/seo.json`; AI context is in `src/content/ai-context.json`.
- Global styling and brand tokens are defined in `src/styles/global.css` (Tailwind v4).

## Form handling
- Form posts to Web3Forms with inline success state and aria-live messaging.
- No third-party tracking is included by default.

## Testing checklist
- Primary CTA visible above the fold and scrolls to the form.
- Form submission shows inline success and preserves focus visibility.
- Metadata and JSON-LD render without console errors.
- Layout retains WCAG AA contrast for text and buttons.
# Pisys-Funnel
