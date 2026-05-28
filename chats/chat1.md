# Mobile Responsive Design

_Started 2026-05-22 00:51 UTC_

---

## User

<system-info comment="Only acknowledge these if relevant">
Project title is now "Web Page"
Project is currently empty (no files)
Current date is now May 22, 2026
</system-info>

<default aesthetic>
If no references, art direction or design systems were provided, use this default professional modern, minimal aesthetic as a base. Declare your choice out loud so you stick to it. Guidance:
- Choose a type pairing from web-safe set or Google Fonts. Helvetica is a good choice. Avoid hard-to-read or overly stylized fonts. Use 1-3 fonts only.
- Foreground and background: choose a color tone (warm, cool, neutral, something in-between). Use subtly-toned whites and blacks; avoid saturations above 0.02 for whites.
- Accents: choose 0-2 additional accent colors using oklch. All accents should share same chroma and lightness; vary hue.
- NEVER write out an SVG yourself that's more complicated than a square, circle, diamond, etc.
- For imagery, never hand-draw SVGs; use subtly-striped SVG placeholders instead with monospace explainers for what should be dropped there (e.g. “product shot”)

CRITICAL: ignore default aesthetic entirely if given other aesthetic instructions like reference images, design systems or guidance, or if there are files in the project already.
</default aesthetic>

<pasted_text name="Pasted text (74 lines)">
# Taiye — Personal Site Design Brief

## Overview
A quiet, minimal one-page personal site for Taiye Promise K. — AI automation developer, product builder, student, and founder of Kotique Studio. Not a portfolio. Not a landing page. A digital identity card.

---

## Tone & Aesthetic Direction
- **Mood:** Quiet. Still. Intentional. Like someone who doesn't need to shout.
- **Theme:** Dark background (near-black, not pure black) with deep blue as the primary accent — pulled from profile photo background (#2563EB range).
- **Light variant:** Soft off-white sections can be used sparingly for contrast.
- **No yellow. No gradients. No stock illustrations.**
- **Typography:** Pair a distinctive serif or editorial display font for the name/headline with a clean mono or refined sans for body. Something that feels considered, not default.
- **Motion:** Subtle. Slow fade-ins on scroll. No bouncing, no aggressive animation.
- **Spatial feel:** Generous whitespace. Let things breathe. Nothing cramped.

---

## Profile Photo
- Circular photo of Taiye — young Black man, black Chanel shirt, cobalt blue background.
- Use the blue from the photo as the accent color throughout the site.
- The photo should feel integrated, not pasted in. Consider desaturating slightly or adding a subtle blue-toned overlay to match the dark site palette.

---

## Site Structure (Single Page)

### 1. Hero / Intro
- Name: **Taiye Promise K.**
- One-line identity: something like — *"I build things with AI. Sometimes I build the things that build things."*
- Or simpler: *"Developer. Builder. Studio founder."*
- Location: Akure, Nigeria
- Profile photo — present but not dominating

### 2. What I Do
Four short blocks (no long descriptions, just a label + 1–2 lines):

- **AI Automation** — Voice agents, WhatsApp bots, n8n workflows. I help businesses automate the parts that slow them down.
- **Product Building** — I build my own products. Ghost Shift, Broken Hero, Echo Vault, IRONBOUND — things I'm making because they should exist.
- **Kotique Studio** — I'm building an AI-powered film studio infrastructure. Not making films — building the machine that will.
- **Student** — Studying at FUTA (Federal University of Technology Akure). Tech, always.

### 3. Currently Building
A minimal list — project name + one-sentence status. No links required yet.

- **Ghost Shift** — Anonymous job marketplace. In development.
- **Broken Hero** — Browser roguelike with deck-building. In development.
- **Echo Vault** — Voice-based personal archive SaaS. Planned.
- **Kotique Studio** — AI film studio infrastructure. Active.
- **IRONBOUND** — In development.

### 4. Also
One quiet line, no section heading needed:
*"I also explore network marketing and community building — currently with FHG/Neolife."*

### 5. Connect
- Upwork
- Fiverr
- GitHub (if available)
- Email (optional placeholder)

---

## Technical Notes
- Single HTML file preferred (HTML + CSS + minimal JS)
- No frameworks needed — keep it lightweight
- Mobile responsive
- No external dependencies except fonts (Google Fonts or similar)
- Smooth scroll, subtle entrance animations on load

---

## What Makes It Unforgettable
The contrast between **"I'm a student in Akure"** and **"I'm building an AI film studio"** — that tension should come through quietly. Not stated directly. Just felt in the layout and copy.
</pasted_text>

<!-- The user explicitly selected the following skills for this project, as attachments to their message. These are not optional context — they define how you work. Use them. -->
<attached-skill name="Hi-fi design">
Create a high-fidelity, polished design. Follow the instructions about design in your system prompt, particularly the 'How to do design work' section. Use the design_canvas starter component, or make a full-bleed prototype and offer options via Tweaks.
</attached-skill>

<attached-skill name="Interactive prototype">
Create a fully interactive prototype with realistic state management and transitions. Use React useState/useEffect for dynamic behavior. Include hover states, click interactions, form validation, animated transitions, and multi-step navigation flows. It should feel like a real working app, not a static mockup.
</attached-skill>


<system-reminder>Auto-injected reminder (ignore if not relevant): do not recreate copyrighted or branded UI unless the user's email domain matches that company. Create original designs instead.</system-reminder>

## Assistant

_[tool: copy_starter_component]_

The brief is detailed enough that I'll just build it. Let me commit to the system out loud:

- **Type:** Instrument Serif (display/name) + JetBrains Mono (body, labels, lists) — editorial × technical, mirroring the "student building AI film studio" tension
- **Palette:** near-black `#0b0c0f` background, cobalt accent `#2563EB`, warm off-white `#f5f4f1` foreground at low opacity, single off-white section for the "Currently Building" list as the brief allows
- **Motion:** slow fade+lift on scroll, nothing else
- **Layout:** left-aligned, generous whitespace, an editorial column with a circular photo slot floating in the hero
- **Photo:** drag-and-drop slot so Taiye can drop the real photo in (uses the cobalt blue from the photo as the slot's resting state)

Let me grab the image-slot starter and build.

_[tool: write_file]_

_[tool: done]_

_[tool: fork_verifier_agent]_

Built it as a single page, dark cobalt-on-near-black, Instrument Serif paired with JetBrains Mono. A few notes:

- **Portrait slot** — the circular spot in the hero is a drag-and-drop slot. Drop the actual photo on it and it persists; the cobalt fill matches the photo background so it reads as integrated even before you drop one in.
- **Email** is a placeholder (`hello@taiye.dev`) — swap it. Upwork/Fiverr/GitHub links are `#`; fill the real URLs.
- A soft cobalt cursor halo (desktop only) gives the dark surface a little life without being noisy. Tell me if it's too much and I'll pull it.

## User

kotikutaiye@gmail.com

CAN YOU MAKE IT RESPONSIVE FOR MOBILE AND TABET AS WELL?

## Assistant

_[tool: read_file]_

_[tool: str_replace_edit]_

Updating the email and adding proper tablet + tightened mobile responsiveness.

_[tool: done]_

_[tool: fork_verifier_agent]_

Done. Email updated to `kotikutaiye@gmail.com`. Added a tablet breakpoint (≤1024px) and tightened the mobile layout (≤640px) plus a very-narrow guard (≤380px). Key responsive changes:

- **Tablet:** hero scales down, photo gets larger relative to viewport, "Currently Building" rows wrap the status line below the project name so "In development" doesn't get squeezed.
- **Mobile:** single-column everywhere, photo moves above the name at 88px, slashes drop out of the locus line, footer stacks, hover-padding suppressed (irrelevant on touch).
- **<380px:** caps the largest type so the name never overflows on small phones.

## User

Verifier agent check completed

## User

https://github.com/taiye-kotiku

## User

https://github.com/taiye-kotiku

## Assistant

_[tool: str_replace_edit]_

GitHub link wired up to `github.com/taiye-kotiku`. Drop me your Upwork and Fiverr URLs whenever and I'll plug those in too.

## User

IS THE TEXT OKAY?

## Assistant

Mostly — it's pulled almost verbatim from your brief, which was already well-written. Two things to flag:

1. **IRONBOUND** — your brief just said "In development" with no description. I wrote "Quiet for now" as filler. It's evocative but it tells the reader nothing. Better options: drop the descriptive note entirely (let the name stand alone like a teaser), or give me a one-line tagline for it.

2. **"FUTA"** as the heading works if your audience is Nigerian — they'll know it. For an international audience the body line explains it, so it's fine, but you could swap the heading to "Student" if you want zero friction.

Optional polish, your call:
- "Developer · Builder · Founder" in the locus line is a little résumé-flavoured for an otherwise quiet site. Consider just `Akure, Nigeria / UTC+1` and let the rest of the page do the talking.
- "Available — selectively" up top is a strong signal — keep if you mean it, drop if you don't want inbound.

Want me to apply any of these?

## User

FOR IRONOUND,IN DEVELOPMENT
USE STUDENT BUT STILL KEEP FUTA
I WANT INBOUND

## Assistant

_[tool: str_replace_edit]_

Done. IRONBOUND now reads "In development" like the others, and the fourth block is "Student" with FUTA called out in the body line.

## User

HOW DO WE PBLISH THIS, THIS IS GOOD

## Assistant

_[tool: invoke_skill]_

_[tool: str_replace_edit]_

I'll bundle the site into a single self-contained file you can host anywhere, then walk you through hosting it.

_[tool: super_inline_html]_

_[tool: show_html]_

_[tool: present_fs_item_for_download]_

Bundled into one self-contained file. Download it above, then pick a host:

**Easiest (60 seconds, free, gives you a URL):**
- **Netlify Drop** → [app.netlify.com/drop](https://app.netlify.com/drop) — drag the file onto the page, get a `yoursite.netlify.app` URL instantly. Claim a custom subdomain in settings.
- **Vercel** or **Cloudflare Pages** work the same way.

**If you want it on your own domain:**
- Buy a domain (Namecheap, Porkbun, ~$10/yr — `taiye.dev` or `taiyepromise.com` would fit)
- In Netlify/Vercel: Domain Settings → add custom domain → follow the DNS instructions.

**If you want it on GitHub (since you already have an account):**
- Create a repo named `taiye-kotiku.github.io`
- Upload the file but rename it to `index.html`
- Settings → Pages → enable. Live at `taiye-kotiku.github.io`.

Recommend Netlify Drop for speed. Tell me when it's live if you want me to add the URL anywhere.

## User

https://www.fiverr.com/taiyekotiku

https://www.upwork.com/freelancers/~01b3e3f59cbf1205f6

## Assistant

_[tool: str_replace_edit]_

_[tool: super_inline_html]_

_[tool: present_fs_item_for_download]_

Upwork and Fiverr links wired up. Re-download above — that's your final file, ready to drop on Netlify.

