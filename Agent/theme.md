# theme.md
> Pisys.Net Landing Page Theme System  
> Primary Blue: `#013753` • Accent Red: `#C62A20`  
> Goal: calm, premium, business-first cyber resilience aesthetic (no “hacker” clichés)

## 1) Brand feel (what we’re aiming for)
**Keywords:** calm, trustworthy, practical, resilient, modern UK-business, board-friendly.  
**Avoid:** neon green, terminal/hacker imagery, glitch effects, skulls, lock icons everywhere, fear-based visuals.

Design should feel like:
- “Clear professional audit” (not “panic security alert”)
- “Business continuity” (not “IT jargon”)

---

## 2) Color system
### Core
- **Primary / Blue:** `#013753` (Pisys.Net primary)
- **Accent / Red:** `#C62A20` (Pisys.Net accent/logo)
- **Background:** `#FFFFFF`
- **Text (default):** `#0F172A` (deep slate)
- **Muted text:** `#475569` (slate)
- **Borders / lines:** `#E2E8F0` (light slate)
- **Section background (subtle):** `#F8FAFC` (very light slate)

### Usage rules
- Blue is used for: primary CTA button, key headings, links, major emphasis.
- Red is used for: accents only (badges, small highlights, icon fills, underlines).  
  Do **not** make the entire UI “red-heavy”.

### CTA states
- Primary button background: **Blue**
- Primary button hover: slightly darker blue (auto via Tailwind `hover:bg-...` or CSS darken)
- Focus ring: blue with visible outline (WCAG AA)
- Use red sparingly for “limited availability” pill or underline.

---

## 3) Typography
Use system-safe defaults for performance + credibility.

### Font stack
- `ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji", "Segoe UI Emoji"`

### Type scale (suggested)
- **H1:** 40–52px (mobile ~34–40px), tight leading, bold
- **H2 (hook):** 22–28px, semi-bold
- **Section headings:** 20–24px, bold
- **Body:** 16–18px, relaxed leading (1.6+)
- **Micro text:** 12–14px

### Copy formatting rules
- Keep lines short-ish: max width ~60–72ch for body.
- Use bullet lists for clarity (already in content).
- Avoid long dense paragraphs.

---

## 4) Layout + spacing
### Layout container
- Max width: **1100–1200px** for main container
- Horizontal padding: 16px mobile, 24px tablet, 32px desktop

### Spacing rhythm
- Section padding: 56–88px vertical depending on density
- Card padding: 20–28px
- Element spacing: multiples of 4/8px (Tailwind default)

### Grid
- Desktop: 2-column layouts for value/proof/process when helpful
- Mobile: always stacked, with CTA visible early

---

## 5) Components (visual language)
### Buttons
- **Primary CTA:** filled blue, white text, rounded-xl, medium shadow
- **Secondary:** outline blue, transparent background
- Minimum height 44px for accessibility

### Cards / panels
- White cards on subtle background sections
- Rounded-2xl corners
- Soft shadow (not heavy)
- Border `#E2E8F0` optional for definition

### Badges / pills
- Use red accent in a subtle way:
  - Outline red + red text (or very light red background)
  - Example: “Limited availability” pill

### Icons
- Optional, minimal, consistent stroke style
- Prefer “business” icons: shield, checklist, clock, building, document
- Avoid “skull / hacker” motifs

---

## 6) Page sections (recommended visuals)
### Hero
- Left-aligned or centered H1 + hook + supporting line
- Primary CTA above the fold
- Include micro reassurance under CTA
- Optional: a simple “audit scope” mini-row (Devices • Microsoft 365 • Backups) as small chips

### Value
- Present as a bulleted list in a card/panel for scannability

### Proof
- Two short paragraphs, optionally in a card with a subtle left border accent (red or blue)

### Process
- Simple 4-step horizontal (desktop) / vertical (mobile)
- Use minimal icons or numbered steps

### CTA + Form
- Light section background, CTA text above form
- Form in a clean card with strong labels

### Footer trust extensions
- Display as icon/badge row or clean list
- Keep it understated, not salesy

---

## 7) Motion (optional, subtle)
- Prefer no animation by default.
- If added: tiny fade-in on scroll, short duration, no parallax.
- Do not animate the CTA aggressively.

---

## 8) Accessibility rules (non-negotiable)
- WCAG AA contrast for all text and interactive elements.
- Visible focus states for links/buttons/inputs.
- Form labels always present (no placeholder-only inputs).
- Error messages must be clear and tied to fields.

---

## 9) Tailwind token mapping (if using Tailwind)
Define these in `tailwind.config` (or use CSS variables if not customizing Tailwind):

- `--color-primary: #013753`
- `--color-accent: #C62A20`
- `--color-text: #0F172A`
- `--color-muted: #475569`
- `--color-border: #E2E8F0`
- `--color-subtle: #F8FAFC`

Recommended class usage:
- Primary button: `bg-[var(--color-primary)] text-white hover:opacity-95 focus:ring-2 focus:ring-[var(--color-primary)]`
- Accent elements: `text-[var(--color-accent)] border-[var(--color-accent)]`

---

## 10) “Looks wrong if…”
- The page feels like a pentest/hacker brand.
- Red is everywhere.
- Copy is cramped or overly technical.
- The form looks like a generic embed rather than part of the page.
- The CTA isn’t clearly the most important element.

---
End of `theme.md`
