# SEO Audit — Taiye Promise K. Personal Website
**URL:** https://taiye-kotiku.github.io/  
**Audited:** 2026-05-29  
**Auditor:** Claude Code (automated HTML-level audit)

---

## SEO Health Score: 81 / 100

| Category | Score | Notes |
|---|---|---|
| Technical SEO | 18 / 20 | Solid foundation; og:image added |
| On-Page SEO | 15 / 20 | Heading hierarchy fixed; content thin |
| Schema / Structured Data | 17 / 20 | Person + WebSite in place; ProfilePage missing |
| Performance Hints | 14 / 20 | LCP fix applied; no image CDN |
| AI / GEO Readiness | 8 / 10 | Good citability; llms.txt not yet created |
| Content Quality / E-E-A-T | 9 / 10 | Clear identity, skills, projects |

---

## What Was Fixed Automatically

### 1. Open Graph — og:image added (was completely missing)
```html
<meta property="og:image" content="https://taiye-kotiku.github.io/og-image.png" />
<meta property="og:image:width" content="1200" />
<meta property="og:image:height" content="630" />
<meta property="og:image:alt" content="Taiye Promise K. — AI Automation Developer & Studio Founder" />
```
This was a **critical gap** — without og:image, link previews on Twitter/X, LinkedIn, WhatsApp, and iMessage show a blank card.

### 2. Twitter Card — upgraded to `summary_large_image` + image + creator tags
```html
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:image" content="https://taiye-kotiku.github.io/og-image.png" />
<meta name="twitter:image:alt" content="..." />
<meta name="twitter:creator" content="@taiyekotiku" />
<meta name="twitter:site" content="@taiyekotiku" />
```
Previously `summary` (small thumbnail). `summary_large_image` gives full-width card previews on X/Twitter.

### 3. `<meta name="author">` and `<meta name="theme-color">` added
```html
<meta name="author" content="Taiye Promise K." />
<meta name="theme-color" content="#2563EB" />
```
`theme-color` sets the browser chrome colour on mobile (cobalt blue matches the brand).

### 4. Sitemap link hint added
```html
<link rel="sitemap" type="application/xml" href="/sitemap.xml" />
```
Tells crawlers where to find the sitemap (file still needs to be created — see Manual Actions).

### 5. Heading hierarchy fixed — `<p class="label">` → `<h2 class="label">`
The three section labels ("What I do", "Currently building", "Connect") were `<p>` tags. Changed to `<h2>` with identical styling (added `font-weight: 400` to `.label` to prevent browser default bold).

**Before:** H1 → H3 (skipped H2 entirely — a Google quality signal and accessibility failure)  
**After:** H1 → H2 → H3 (correct semantic hierarchy)

### 6. Hero portrait LCP fix — `loading="lazy"` → `loading="eager"` + `fetchpriority="high"`
```html
loading="eager"
fetchpriority="high"
```
The hero portrait is the **Largest Contentful Paint element**. Lazy-loading it delays LCP and tanks Core Web Vitals scores. `fetchpriority="high"` hints the browser to fetch it before other resources.

### 7. Font preload hint added
```html
<link rel="preload" href="https://fonts.googleapis.com/css2?..." as="style" />
```
Tells the browser to fetch the font stylesheet early, reducing FOIT (Flash of Invisible Text). Note: Google Fonts already had `display=swap` — that was already correct.

### 8. Person schema — email added to `sameAs`
```json
"sameAs": [
  "https://github.com/taiye-kotiku",
  "https://www.upwork.com/freelancers/~01b3e3f59cbf1205f6",
  "https://www.fiverr.com/taiyekotiku",
  "mailto:kotikutaiye@gmail.com"
]
```

---

## What Still Needs Manual Action

### HIGH PRIORITY

#### A. Create `og-image.png` (1200×630px)
The og:image tag now points to `https://taiye-kotiku.github.io/og-image.png` — **this file does not exist yet**. Until it does, social share cards will still be blank.

Suggested design: dark background (#0b0c0f), large serif name "Taiye Promise K.", cobalt blue accent line, tagline "AI Automation Developer · Kotique Studio · Akure, Nigeria".

Tools: Figma, Canva, or a simple HTML-to-image script.

#### B. Create `/sitemap.xml`
Single-page site — the sitemap is simple:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://taiye-kotiku.github.io/</loc>
    <lastmod>2026-05-29</lastmod>
    <changefreq>monthly</changefreq>
    <priority>1.0</priority>
  </url>
</urlset>
```
Submit to Google Search Console after publishing.

#### C. Create `/robots.txt`
```
User-agent: *
Allow: /

Sitemap: https://taiye-kotiku.github.io/sitemap.xml
```

#### D. Verify Twitter/X handle
`@taiyekotiku` is assumed from the Fiverr username. Confirm the actual Twitter/X handle and update `twitter:creator` / `twitter:site` if different.

#### E. Add LinkedIn to `sameAs` in JSON-LD
If a LinkedIn profile exists, add it:
```json
"https://www.linkedin.com/in/taiyekotiku"
```
LinkedIn is one of the strongest authority signals for Person schema in AI/knowledge graph contexts.

### MEDIUM PRIORITY

#### F. Create `/llms.txt`
AI search engines (Perplexity, ChatGPT with browsing, Bing AI) increasingly respect `llms.txt` as a signal for how to cite/use your content. Recommended minimal content:

```
# Taiye Promise K.
> AI automation developer and founder of Kotique Studio, based in Akure, Nigeria.

Taiye Promise K. builds voice agents, WhatsApp bots, n8n automation workflows,
and AI-powered products. He is the founder of Kotique Studio, an AI-powered film
studio infrastructure company. He is studying at the Federal University of
Technology, Akure (FUTA).

## Contact
- Email: kotikutaiye@gmail.com
- GitHub: https://github.com/taiye-kotiku
- Upwork: https://www.upwork.com/freelancers/~01b3e3f59cbf1205f6
- Fiverr: https://www.fiverr.com/taiyekotiku
```

#### G. Add `ProfilePage` schema type
The current schema uses `Person` + `WebSite`. Google Knowledge Panel triggering benefits from also typing the page as `ProfilePage`:
```json
{
  "@type": "ProfilePage",
  "mainEntity": { "@id": "https://taiye-kotiku.github.io/#person" }
}
```

#### H. Add real portrait URL to schema `image` field
When the portrait is hosted as an actual file (not base64), add to Person schema:
```json
"image": {
  "@type": "ImageObject",
  "url": "https://taiye-kotiku.github.io/portrait.jpg",
  "width": 400,
  "height": 400
}
```

#### I. Increase content depth (~1,700 words currently)
The page has approximately 1,700 words (excluding base64 data). For competitive ranking on terms like "AI automation developer Nigeria" or "WhatsApp bot developer Akure", aim for 2,500–3,000 words. Consider expanding:
- A short "About" paragraph with specific projects and outcomes
- A brief case study or testimonial
- Explicit skill keywords (n8n, Make.com, Voiceflow, GPT-4, etc.)

### LOW PRIORITY

#### J. Add `<nav>` landmark with skip link
Currently no `<nav>` element. Internal anchor links (#work, #building, #connect) exist in the DOM but are not exposed as navigation. Adding a visually hidden skip nav improves accessibility and gives crawlers an explicit site outline.

#### K. Title tag slightly long (76 chars)
The 60-char sweet spot for desktop SERP display: consider trimming to:
`Taiye Promise K. — AI Automation Developer | Akure, Nigeria` (59 chars)
The current title is fine and unlikely to cause ranking issues, but it may be truncated in SERPs.

#### L. Google Search Console setup
Submit the canonical URL and sitemap.xml through Google Search Console. Request indexing if the page has not yet appeared in search results.

---

## Quick Reference: What's Already Solid

- `<html lang="en">` — correct
- `<meta charset="utf-8">` — correct
- `<meta name="viewport">` — correct
- Canonical tag — correct (`https://taiye-kotiku.github.io/`)
- `<meta name="robots" content="index, follow">` — correct
- Favicon (inline SVG cobalt-blue "T") — implemented
- `preconnect` for Google Fonts — in place
- `font-display=swap` on Google Fonts — already present before audit
- Exactly one `<h1>` — correct
- Image alt text — present and descriptive
- External links have `rel="noopener"` — correct
- JSON-LD Person + WebSite schema — comprehensive
- `@id` anchors in schema — correct (enables Knowledge Graph connections)
- `og:locale`, `og:site_name` — present
- E-E-A-T signals: real name, real location, real email, real university, real platforms — strong

---

*Audit performed by static HTML analysis. Dynamic rendering, Core Web Vitals (CWV), and PageSpeed scores require a live browser test via Lighthouse or PageSpeed Insights.*
