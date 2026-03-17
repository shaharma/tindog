# Website Design Plan: Adv. Becky Fuhrmann
## Updated: 2026-03-17 | Status annotations added after full audit

> Legend: DONE = implemented and verified | PARTIAL = started, needs work | TODO = not started | BLOCKED = needs client input

---

## 1. BRAND IDENTITY & DESIGN SYSTEM

### Color Palette — "Modern Counselor"
| Role | Color | Hex | Status |
|------|-------|-----|--------|
| Primary (60%) | Deep Charcoal | `#1a1a2e` | DONE |
| Secondary (30%) | Warm Stone | `#a69882` | DONE |
| Accent (10%) | Muted Gold | `#b8934b` | DONE |
| Surface | Warm White | `#faf9f6` | DONE |
| Surface Alt | Soft Cream | `#f3f0ea` | DONE |
| Text Body | Charcoal | `#2c2c2c` | DONE |
| Text Muted | Warm Gray | `#6b6b6b` | DONE |

### Typography
| Role | Font | Status |
|------|------|--------|
| EN Headlines | Cormorant Garamond 600 | DONE |
| HE Headlines | Heebo 700 | DONE |
| EN Body | Inter 400/500 | DONE |
| HE Body | Heebo 400/500 | DONE |
| Accent/Labels | Inter 600 uppercase | DONE |

### Design Language
| Element | Status | Notes |
|---------|--------|-------|
| Rounded corners (8-12px) | DONE | Cards, buttons |
| Generous whitespace | DONE | Varied section padding |
| Subtle texture / paper grain | DONE | Via CSS on warm-white bg |
| Asymmetric layouts | DONE | Hero sections |
| Micro-animations (fade-up on scroll) | DONE | IntersectionObserver-based `.reveal` |
| `prefers-reduced-motion` support | DONE | Added in this session |
| No decorative filler | DONE | Clean, content-focused |

---

## 2. SITE STRUCTURE

### Pages
| Page | EN | HE | Status |
|------|----|----|--------|
| Homepage | `en/index.html` | `index.html` (root) | DONE |
| Commercial Law | `en/commercial.html` | `he/commercial.html` | DONE |
| Corporate Law | `en/corporate.html` | `he/corporate.html` | DONE |
| Data Privacy & DPO | `en/privacy.html` | `he/privacy.html` | DONE |
| About | `en/about.html` | `he/about.html` | DONE |
| Contact & Intake | `en/contact.html` | `he/contact.html` | DONE |
| Blog Index | `en/blog/index.html` | `he/blog/index.html` | DONE |
| Blog: Data Privacy Startups | `en/blog/data-privacy-startups.html` | `he/blog/data-privacy-startups.html` | DONE |
| Blog: Commercial Contract Review | `en/blog/commercial-contract-review.html` | `he/blog/commercial-contract-review.html` | TODO |
| Blog: Corporate Governance | `en/blog/corporate-governance-growth.html` | `he/blog/corporate-governance-growth.html` | TODO |

### Shared Components
| Component | Status | Notes |
|-----------|--------|-------|
| Navbar — fixed, frosted-glass | DONE | Scroll effect, mobile hamburger |
| Footer — contact, links, disclaimer | DONE | Standardized across all pages (this session) |
| Language toggle — header pill | DONE | Always visible, not inside hamburger |
| Mobile sticky CTA | DONE | Call + WhatsApp buttons |

---

## 3. PAGE-BY-PAGE CONTENT

### 3.1 HOMEPAGE
| Section | Status | Notes |
|---------|--------|-------|
| Hero (full-viewport, photo + headline + CTA) | PARTIAL | Layout done, **photo missing** (`images/becky-hero.jpg`) — fallback placeholder active |
| Three Pillars (Structure / Protect / Grow) | DONE | 3 cards linking to practice areas |
| Brief Intro ("who" in 3 sentences) | DONE | Credentials inline |
| Social Proof / Trust | DONE | Sector tags (fintech, SaaS, legaltech, etc.) |
| CTA Band | DONE | "Ready to discuss?" + CTA + phone |
| Latest Insights (blog cards) | PARTIAL | 3 cards shown; 2 of 3 articles don't have individual pages yet |
| Footer | DONE | |

### 3.2 PRACTICE AREA PAGES (commercial, corporate, privacy)
| Section | Status | Notes |
|---------|--------|-------|
| Page Hero (pillar word + name + overview) | DONE | |
| What I Help With (4-6 sub-services) | DONE | 6 services per page |
| Who This Is For (target clients) | DONE | 3 client-type cards per page |
| My Approach | DONE | Specific, personal tone |
| Anonymized Case Highlight | TODO | Needs client input |
| CTA Section | DONE | |

### 3.3 ABOUT PAGE
| Section | Status | Notes |
|---------|--------|-------|
| Professional Photo (large, editorial) | PARTIAL | Layout done, **photo missing** (`images/becky-about.jpg`) — fallback placeholder active |
| Story (first person, 3-4 paragraphs) | DONE | |
| Credentials (bar, LL.M, DPO, board cert) | DONE | 4 credential cards |
| Career Highlights / Milestones | DONE | 4 key milestones |
| CTA to contact | DONE | |

### 3.4 CONTACT PAGE
| Section | Status | Notes |
|---------|--------|-------|
| Headline ("Let's Talk") | DONE | |
| Process Steps (3-step how it works) | DONE | Moved from homepage per plan |
| Contact Form (name, phone, email, subject, message) | PARTIAL | **Form has NO backend** — simulated submission only. Needs Formspree/Netlify integration |
| Direct Contact Methods (phone, email, WhatsApp, LinkedIn) | DONE | All 4 methods with icons |
| FAQ Accordion | DONE | 4 questions, `aria-expanded` now managed (fixed this session) |
| Hours of operation | DONE | Sun-Thu 9:00-18:00 |

### 3.5 BLOG / INSIGHTS
| Item | Status | Notes |
|------|--------|-------|
| Blog index grid | DONE | 3 article cards |
| Article 1: "5 Things About Data Privacy" | DONE | Full article, both languages |
| Article 2: "Commercial Contract Review" | TODO | Card exists with `href="#"` placeholder, page not created |
| Article 3: "Corporate Governance" | TODO | Card exists with `href="#"` placeholder, page not created |
| Individual article layout | DONE | Clean reading layout, author byline, CTA |
| Related articles at bottom | TODO | Not implemented on article pages |

---

## 4. BILINGUAL IMPLEMENTATION

| Feature | Status | Notes |
|---------|--------|-------|
| Subdirectory structure (HE root, EN `/en/`) | DONE | |
| Separate HTML files per language | DONE | 17 files total |
| `hreflang` tags on all pages | DONE | Relative URLs (need absolute URLs with final domain before launch) |
| Separate `<title>` and `<meta description>` | DONE | All pages |
| Language toggle (pill, always visible) | DONE | EN \| עב, outside hamburger |
| `dir="rtl"` / `dir="ltr"` correct | DONE | |
| CSS logical properties for RTL | DONE | |
| Hebrew font sizing bump (~10%) | DONE | |

---

## 5. TECHNICAL ARCHITECTURE

### File Structure
| Item | Status |
|------|--------|
| `css/styles.css` (shared, single file) | DONE — 1,370+ lines |
| `js/main.js` (shared, vanilla JS) | DONE — 134 lines |
| `images/` directory | EXISTS but **EMPTY** |
| No CSS/JS frameworks | DONE |

### CSS Architecture
| Feature | Status | Notes |
|---------|--------|-------|
| Custom properties (colors, spacing, typography) | DONE | Full design system |
| RTL via `[dir="rtl"]` + logical properties | DONE | |
| `prefers-reduced-motion` media query | DONE | Added this session |
| Noscript/no-JS `.reveal` fallback | DONE | Added this session |
| Dead CSS cleanup | TODO | `.container-narrow`, `.section-lg`, `.section-dark`, `.label-on-dark`, `.text-large` are unused |
| `.article-content` class | TODO | Defined in CSS but not applied to blog article body — article typography styles not applied |

### JavaScript
| Feature | Status | Notes |
|---------|--------|-------|
| Navbar scroll behavior | DONE | |
| Mobile hamburger toggle | DONE | With `aria-expanded` |
| Scroll-reveal (IntersectionObserver) | DONE | Graceful degradation |
| FAQ accordion | DONE | `aria-expanded` management added this session |
| Smooth scroll for anchors | DONE | |
| Contact form validation | DONE | Client-side only |
| Contact form submission | TODO | **Simulated — needs real backend (Formspree/Netlify)** |

### Performance
| Feature | Status | Notes |
|---------|--------|-------|
| Inline critical CSS | PARTIAL | Hero animation CSS is inline; main CSS is external |
| Lazy-load images | TODO | No `loading="lazy"` on below-fold images |
| Preload hero image + fonts | TODO | No `<link rel="preload">` tags |
| Target <2s FCP on mobile | UNTESTED | |

### SEO
| Feature | Status | Notes |
|---------|--------|-------|
| Unique `<title>` per page | DONE | All 17 pages |
| Unique `<meta description>` per page | DONE | All 17 pages |
| `hreflang` tags | DONE | **Need absolute URLs before launch** |
| `og:title`, `og:description`, `og:type` | DONE | All pages |
| `og:locale` | DONE | Fixed `he/commercial.html` this session |
| `og:url` | TODO | Missing on all pages — needs final domain |
| `og:image` | TODO | Missing on all pages — needs image file created |
| `<link rel="canonical">` | TODO | Missing on all pages — needs final domain |
| Structured data (JSON-LD) | TODO | `LegalService`, `Person`, `Article` schemas |
| `sitemap.xml` | TODO | |
| `robots.txt` | TODO | |
| Favicon | TODO | No `favicon.svg` or `<link rel="icon">` |
| `<meta name="keywords">` consistency | PARTIAL | Missing on `en/commercial.html` and `en/about.html` |
| Blog article `article:published_time` | TODO | |
| Blog article `<time datetime="">` | TODO | |

### Accessibility
| Feature | Status | Notes |
|---------|--------|-------|
| `role="navigation"` + `aria-label` | DONE | All navbars |
| Hamburger `aria-expanded` | DONE | |
| FAQ `aria-expanded` | DONE | Fixed this session |
| Image `alt` text | DONE | All `<img>` tags |
| `<main>` landmark element | TODO | No page uses `<main>` |
| SVG `aria-hidden="true"` | TODO | Decorative SVGs in buttons lack this |
| Form `aria-live` for feedback | TODO | No announcement for screen readers on form submit |
| Semantic `<time>` for dates | TODO | Blog dates not in `<time>` elements |

---

## 6. CRITICAL FIXES FROM ORIGINAL PLAN

| Issue | Status | Notes |
|-------|--------|-------|
| DPO score removed | DONE | |
| Professional email domain | DONE | `becky@fuhrmann-law.co.il` throughout |
| Language toggle always visible | DONE | Outside hamburger |
| Real professional photo | BLOCKED | **Client needs to provide `becky-hero.jpg` and `becky-about.jpg`** |
| Trust strip removed from homepage | DONE | Credentials on About page |
| No repeated stats | DONE | |
| "Why Choose Me" folded into service pages | DONE | |
| "Process" moved to Contact page | DONE | |
| Specific, non-generic copy | DONE | |
| WhatsApp as contact method | DONE | All pages, mobile sticky CTA |
| Form submits to real backend | TODO | **Still simulated — needs Formspree/Netlify** |
| Favicon + OG image | TODO | |
| CSS/JS extracted to shared files | DONE | |
| "Free consultation" → "Introductory meeting" | DONE | "Schedule an Introductory Meeting" / "פגישת היכרות" |
| `tel:` international format | DONE | Fixed this session: `+972507726286` |

---

## 7. CONTENT STILL NEEDED FROM CLIENT

| Item | Status | Notes |
|------|--------|-------|
| Professional headshot (hero) | BLOCKED | Placeholder fallback active |
| Professional headshot (about) | BLOCKED | Placeholder fallback active |
| Bar association number | BLOCKED | Not currently displayed |
| Client quotes/testimonials | BLOCKED | Using sector tags instead |
| Career highlights review | DONE | 4 milestones written (anonymized) |
| WhatsApp number confirmed | DONE | 050-772-6286 / +972507726286 |
| Copy review and approval | BLOCKED | Both HE and EN need client sign-off |

---

## 8. IMPLEMENTATION ORDER — STATUS

| Phase | Status |
|-------|--------|
| 1. Shared foundation (CSS + JS + components) | DONE |
| 2. Homepage HE | DONE |
| 3. Homepage EN | DONE |
| 4. Practice area pages (HE + EN, all 3) | DONE |
| 5. About page (HE + EN) | DONE |
| 6. Contact page (HE + EN) | DONE |
| 7. Blog structure + 1 article (HE + EN) | DONE (1 of 3 articles) |
| 8. Polish: animations, accessibility, SEO | PARTIAL — see details below |
| 9. Testing & verification | NOT STARTED |

### Phase 8 Detail: Polish Items

**Done this session:**
- `prefers-reduced-motion` CSS support
- FAQ `aria-expanded` in JS
- Footer standardized across all 16 pages (consistent Quick Links + Contact header)
- Nav CTA text standardized ("Schedule a Meeting" everywhere)
- Nav-logo text standardized ("Adv. Becky Fuhrmann" / "עו״ד בקי פורמן")
- `tel:` hrefs updated to international format
- `he/commercial.html` fixed (aria-label, phone SVG, og:locale, font import)
- `en/corporate.html` hero label de-duplicated
- Noscript `.reveal` fallback in CSS

**Still TODO (feasible without client input):**
- [ ] Write blog articles 2 and 3 (commercial contracts + corporate governance) — 4 HTML files
- [ ] Add `<main>` landmark to all 17 pages
- [ ] Add `aria-hidden="true"` to decorative SVGs
- [ ] Apply `.article-content` class to blog article body
- [ ] Add `loading="lazy"` to below-fold images
- [ ] Add `<link rel="preload">` for hero image and fonts
- [ ] Create `sitemap.xml`
- [ ] Create `robots.txt`
- [ ] Create `favicon.svg` (simple "BF" monogram)
- [ ] Add `<time datetime="">` to blog dates
- [ ] Add `aria-live` region for form feedback
- [ ] Add `<meta name="keywords">` to `en/commercial.html` and `en/about.html`
- [ ] Clean up unused CSS classes
- [ ] Add JSON-LD structured data (`LegalService` on homepage, `Person` on about, `Article` on blog posts)
- [ ] Add related articles section to blog article pages

**TODO (needs final domain / client input):**
- [ ] Update all `hreflang` tags to absolute URLs
- [ ] Add `<link rel="canonical">` to all pages
- [ ] Add `og:url` to all pages
- [ ] Create `og:image` (social sharing preview)
- [ ] Integrate contact form with real backend (Formspree / Netlify Forms)
- [ ] Replace photo placeholders with real professional photos
- [ ] Add anonymized case highlights to practice area pages
- [ ] Client review of all copy

---

## 9. VERIFICATION CHECKLIST

| Test | Status |
|------|--------|
| Open every page in Chrome and Firefox | NOT STARTED |
| Hebrew <-> English navigation on every page | NOT STARTED |
| All inter-page links in both languages | NOT STARTED |
| Mobile responsive (375px, 768px, 1024px, 1440px) | NOT STARTED |
| RTL layout mirrors correctly | NOT STARTED |
| Submit test form → verify delivery | BLOCKED (no backend) |
| W3C HTML validation | NOT STARTED |
| Lighthouse audit (90+ perf, 100 a11y) | NOT STARTED |
| OG tags via social card validators | BLOCKED (no og:image, og:url) |
| hreflang verification | BLOCKED (needs absolute URLs) |

---

## 10. CONSISTENCY FIXES APPLIED (Session Log)

### Session 2026-03-17 (current)
1. Fixed `en/about.html` + `en/contact.html` nav-logo links (pointed to HE root instead of EN home)
2. Standardized nav-logo text to "Adv. Becky Fuhrmann" across all EN pages
3. Fixed `he/commercial.html`: added `aria-label`, phone SVG in CTA, `og:locale`, standardized font import
4. Standardized EN footer Quick Links across all pages (practice areas + About + Insights)
5. Standardized HE footer Quick Links across all pages
6. Removed redundant hero label on `en/corporate.html`
7. Standardized nav CTA button text: "Schedule a Meeting" everywhere (was "Book a Consultation" on about/contact)
8. Standardized CTA band text: "Schedule an Introductory Meeting" on `en/about.html`
9. Standardized footer contact column header to "Contact" across all EN pages
10. Standardized footer brand name and copyright text
11. Updated all `tel:` hrefs to international format (`+972507726286`)
12. Added `prefers-reduced-motion` CSS support
13. Added noscript `.reveal` fallback
14. Added `aria-expanded` management to FAQ accordion in JS
