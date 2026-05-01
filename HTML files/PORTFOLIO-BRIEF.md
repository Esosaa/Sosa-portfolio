# Sosa — Portfolio Website Brief

## What This Is

A portfolio website for Esosa (Sosa), a Senior Product Designer specializing in fintech, logistics, and operations. The portfolio exists to get her hired at a mid-to-senior level. Every decision — layout, copy, typography, color — is designed to communicate one thing: this is someone who turns complex systems into clear, high-trust products and leads that process end to end.

The portfolio is not a visual showcase. It's a demonstration of thinking.

---

## Site Structure

```
sosa-portfolio.html          → Landing page (home)
sosa-flux-casestudy.html     → Case study 01: Flux
sosa-fitnest-casestudy.html  → Case study 02: Fitnest
sosa-logigo-casestudy.html   → Case study 03: Logigo
```

### How the pages connect

The **landing page** is the entry point. It contains:
- Hero section with positioning statement
- 3 project cards linking to individual case study pages
- Selected Builds section (personal projects: Twine, Chime)
- About section
- Footer with contact links

Each **case study page** is self-contained but links back to the landing page via the nav logo and a "← All Projects" back link. At the bottom of each case study, a "Next Project" link cycles through all three:

```
Flux → Fitnest → Logigo → Flux (loop)
```

This means a recruiter who clicks into any case study can read through all three without returning to the landing page.

---

## Design System

### Colors

```css
/* Light backgrounds */
--bg-light: #F0EDE8;      /* Primary light background */
--bg-mid: #E4E0DA;         /* Cards, meta bars on light sections */
--bg-warm: #E8E2D8;        /* Warm accent band (used in Fitnest, Logigo) */

/* Dark backgrounds */
--bg-dark: #12100E;        /* Primary dark background — warm near-black */
--bg-dark-card: #1E1B18;   /* Elevated cards/frames on dark sections */

/* Text */
--text-dark: #0E0E0C;
--text-body: #3D3A36;
--text-muted: #8A857E;
--text-light: #F0EDE8;
--text-light-muted: rgba(240,237,232,0.5);

/* Accent */
--accent: #A89484;                        /* Warm stone — used for eyebrows, labels, hover states */
--accent-subtle: rgba(168,148,132,0.12);  /* Background tint for callouts and tool tags */

/* Borders */
--border-light: rgba(14,14,12,0.1);
--border-dark: rgba(240,237,232,0.08);
--border-dark-hover: rgba(240,237,232,0.15);
```

### Typography

**Fraunces** (serif) — Display font. Used only for large hero titles, project names, pull quotes, blockquotes, large stat numbers, and the footer CTA headline. This font carries personality and warmth.

**Geist** (sans-serif) — Body and UI font. Used for everything else: body copy, section headings, nav, buttons, tags, eyebrows, descriptions, meta labels. This font carries clarity and precision.

```css
--display: 'Fraunces', Georgia, serif;
--body: 'Geist', -apple-system, Helvetica, sans-serif;
```

**Rules:**
- Body text letter-spacing: -0.3px globally
- Eyebrows: 11px, weight 600, letter-spacing 0.2em, uppercase, colored with --accent
- Section headings: Geist, 20-26px, weight 500
- Display headings: Fraunces, 36-72px, weight 400
- Body text: Geist, 16px, weight 400, color --text-body

### Spacing and Layout

```css
--max-w: 1080px;    /* Wide container — images, meta bars, pivot components */
--prose-w: 680px;   /* Narrow container — all readable text content */
--radius: 4px;      /* Border radius on all interactive elements */
```

**Critical rule:** All readable text sits within the 680px prose column. Images, meta bars, gallery grids, and structural components expand to the 1080px wide container. This ensures a recruiter's eyes never have to readjust horizontally while reading. The prose column is consistent across every page.

### Light/Dark Section Rhythm

Pages alternate between light and dark sections to create depth and pacing. The pattern is not rigid — it varies per page — but every page uses both light and dark sections.

**Landing page:** Light hero → Dark work → Light builds → Dark about → Light footer

**Flux:** Light hero → Dark hero image → Light prose → Dark stat band → Light prose → Dark features → Light pivot → Dark distributors → Light reflections → Light next

**Fitnest:** Light hero → Warm hero image band → Light research → Light findings → Dark insight band → Light competitive/solution → Dark design gallery → Light testing → Warm website band → Dark reflections → Light next

**Logigo:** Light hero → Dark hero image → Light research → Warm journey map → Dark audience reveal → Light solution → Dark platform screens → Warm mobile → Light reflections → Dark next/footer

---

## Each Case Study Has a Unique Layout

This is intentional. The three case studies should NOT feel like the same template with different content. Each project has a different story shape, and the layout reflects that.

### Flux — Editorial, building toward a pivot
- Pain points as a 4-column horizontal strip
- 30% stat as a full-width dark band with oversized Fraunces number
- Large pull quote that breaks the reading flow
- Features in alternating zigzag layout (text left/image right, then flipped)
- Pivot as a three-column layout with circular arrow divider on warm background
- Distributor section as a two-column split with tall mobile phone frame

### Fitnest — Warm, personal, research-centered
- Hero bakes the origin story in, with meta info beside it in two columns
- Hero image on a warm background band (not dark)
- User findings as staggered numbered cards in a masonry-like grid
- Problem statement as a dark insight band
- Design screens as a gallery grid with cards (image + caption below)
- Testing results as a horizontal 3-column strip
- Website screenshot on warm background band

### Logigo — Discovery and convergence
- Hero uses inline tag pills instead of a meta grid
- Journey map as a wide horizontal placeholder on warm background
- Two-audience reveal as a dramatic side-by-side split with ampersand divider
- Shared pain points as centered tags on a darker band below the split
- Platform screens stacked full-width with oversized faded numbers
- Mobile section on warm background with large phone frame
- Reflections on light background (unique — other pages end dark)

---

## Voice and Copy Guidelines

Sosa's voice is specific. The copy on this portfolio should sound like her, not like a portfolio template.

**Tone:** Clear, direct, conversational but not casual. She gets to the point. She guides you through her thinking instead of dumping information. She doesn't hide behind buzzwords or oversell.

**Rules:**
- No "leveraged," "innovative," "user-centric," "cutting-edge"
- No hyphens used as dashes — use commas or periods instead
- First person ("I" and "we") throughout
- Short paragraphs. No walls of text.
- Project descriptions on the landing page are 1-2 lines max. The case study does the heavy lifting.
- Section headings are conversational: "What kept coming up" not "Research Findings"
- Reflections should end with a concrete takeaway, not a vague lesson

**Example of her voice:**
"We went in thinking we were solving a logistics problem. We came out building for an entire ecosystem. That wasn't the plan, but the research made it unavoidable."

---

## Animations and Scroll Effects

### Currently implemented
- **Fade-up on scroll:** All sections use `.reveal` class with IntersectionObserver. Elements fade up 28px with 0.8s ease when they enter the viewport.
- **Hero stagger:** Eyebrow, title, subtitle/bottom animate in sequence with increasing delays (0.15s, 0.3s, 0.5s, 0.6s).

### Suggested additions for Claude Code to build

**1. Smooth page transitions**
When navigating between the landing page and case studies, a subtle fade-out/fade-in transition (200-300ms) would make the site feel like one cohesive experience rather than separate HTML pages. If building with a framework like Astro or Next.js, use View Transitions API or a page transition library.

**2. Parallax on hero images**
The dark hero image sections on each case study page could have a subtle parallax effect — the image scrolls slightly slower than the page (maybe 0.85x speed). This adds depth without being distracting. Keep it subtle. Sosa's identity is controlled, not showy.

**3. Stagger reveal on grid items**
On the landing page project cards, the Fitnest findings grid, the Logigo audience split, and the design gallery cards — instead of all items fading in at once, stagger them with a 100-120ms delay between each. First card appears, then second, then third. This creates a sense of choreography.

**4. Project card image lift on hover (landing page)**
The project image frames on the landing page already have a translateY(-4px) and box-shadow on hover. Consider adding a very subtle scale(1.02) on the image inside the frame to make it feel like the content is alive, not just the container.

**5. Horizontal scroll on the Flux pain strip**
On mobile, the 4-column pain point strip could become a horizontal scroll container instead of stacking vertically. This preserves the "strip" feeling and adds an interaction moment on touch devices.

**6. Number count-up on the Flux stat band**
The "30%" number could count up from 0 when it enters the viewport. Use a simple requestAnimationFrame counter over about 1.5 seconds. Don't add easing effects that make it feel like a startup landing page — just a clean, linear count.

**7. Scroll-linked nav background**
The nav is already semi-transparent with backdrop blur. On case study pages, consider making the nav fully transparent at the top and transitioning to the blurred background as the user scrolls past the hero. This makes the hero feel more immersive.

**8. Cursor interaction on project cards (desktop only)**
On the landing page, when hovering over a project card, the cursor could change to a custom "View →" indicator that follows the mouse within the card area. This replaces the text-based "Read case study →" CTA and feels more interactive. Only implement on desktop — falls back to normal on touch devices.

---

## File Checklist

All four HTML files are complete references:

| File | Status | Notes |
|------|--------|-------|
| `sosa-portfolio.html` | Complete | Landing page with Geist body, Fraunces display |
| `sosa-flux-casestudy.html` | Complete | Editorial zigzag layout, pull quotes, stat band |
| `sosa-fitnest-casestudy.html` | Complete | Warm personal feel, staggered findings, gallery grid |
| `sosa-logigo-casestudy.html` | Complete | Audience split reveal, stacked screens, warm mobile section |

### What still needs to be done
- Replace all placeholder image frames with actual project screenshots
- Add real email address and social links
- Add a real photo in the about section
- Decide on a deployment platform (Vercel, Netlify, custom domain)
- Consider building with Astro or Next.js for page transitions and better performance
- Implement suggested animations above
- Test on mobile devices and refine responsive breakpoints
- Update the landing page hero eyebrow to provide more context (e.g., "Product Designer / Fintech, Logistics, Operations" instead of "Product Design & Strategy")

---

## One Line to Remember

This portfolio is for someone who turns complex systems into clear, high-trust products — and leads that process end to end. Every design decision, every word, every layout choice should reinforce that.
