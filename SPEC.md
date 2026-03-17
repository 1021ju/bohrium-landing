# Bohrium Landing Page — Development Spec

## Overview

Redesigned landing page for `bohrium.com/en/intro` (and `dp.tech/en/product/bohrium` — these two should consolidate into one, with the other redirecting).

**Target audience:** International researchers (English-speaking)
**Primary CTA:** Sign up / Get Started Free → `https://bohrium.com`
**Demo:** [GitHub Pages link — see repo]

---

## Page Structure

### 1. Navigation (sticky)
| Element | Detail |
|---------|--------|
| Logo | `bohrium-logo.png` (Bh 107 element icon + wordmark) |
| Links | Features (anchor) · Compare (anchor) · Pricing (anchor) · Discord (external) |
| CTA | "Get Started Free" → `https://bohrium.com` |
| Behavior | Transparent on hero, white bg + border on scroll |

### 2. Hero Section
| Element | Detail |
|---------|--------|
| Background | Full-width brand visual (current: `home-bg.png` from CDN; may be replaced with new asset from design) |
| Overlay | Semi-transparent dark overlay for text readability |
| Badge | "Trusted by 300,000+ researchers" |
| Headline | "Academic search you can **trust**." — "trust" in gradient text |
| Subheadline | "Every answer backed by real papers. 170M+ peer-reviewed sources, 100% citation traceability, zero hallucinated references." |
| CTAs | Primary: "Get Started Free" · Secondary: "See how it works" (ghost/glass button) |
| Demo | Simulated Science Navigator search box with typing animation + AI response with citation chips |

### 3. Social Proof Bar
Four stats in a row with dividers:
- 170M+ peer-reviewed papers
- 20M+ scholar profiles
- 140K+ journals indexed
- 100+ partner institutions

### 4. Science Navigator Section (anchor: #features)
| Element | Detail |
|---------|--------|
| Label | "Core Feature" |
| Heading | "Science Navigator — search that reasons." |
| Tabs | Lite · Expert · DeepThink |
| Each tab | Left: title + description + feature bullets · Right: visual placeholder (replace with real screenshots) |

**Tab content:**
- **Lite:** Quick answers, instant from 170M+ papers, multi-modal
- **Expert:** Deep analysis, hundreds of sources, review-quality synthesis
- **DeepThink:** Chain-of-thought reasoning, transparent process, hypothesis evaluation

### 5. Research Workflow Section (dark bg: `#1D2129`)
Six cards in 3×2 grid:

| Step | Title | Tool | Description |
|------|-------|------|-------------|
| 01 | Discover | Science Navigator | Ask questions, 170M+ papers, three modes |
| 02 | Go deep | Deep Research | 10K+ word literature reviews |
| 03 | Read & organize | Knowledge Base | Zotero sync, 100+ paper chat |
| 04 | Create | SciDraw & AI Poster | Plain language → vectors, PDF → poster 60s |
| 05 | Track | Journals & Scholar | 140K+ journals, 20M+ scholars |
| 06 | Verify | Sciencepedia | 420K+ verified concepts, knowledge graph |

### 6. Comparison Table (anchor: #compare)
Bohrium vs Perplexity vs Elicit vs Consensus across 7 dimensions:
- Citation traceability, deep literature review, full-text access, knowledge management, research graphics, multi-device sync, price

### 7. Pricing Strip (anchor: #pricing)
| Tier | Price | Note |
|------|-------|------|
| Free | $0 | Core features, limited queries |
| Plus | $20/mo | More queries, priority access |
| Pro | $40/mo | Unlimited, all features |

Plus: "Education discount: 40% off — coming soon" badge
CTA: "Start for Free"

### 8. Testimonials
Three cards with real user quotes (from product knowledge base).

### 9. Footer
| Column | Content |
|--------|---------|
| Brand | Logo + one-line description |
| Product | Science Navigator · Deep Research · Knowledge Base · SciDraw |
| Resources | Help Center · Update Log · Privacy Policy · Terms of Service |
| Community | Discord · X (Twitter) · LinkedIn · support email |

**Social icon links (bottom row, icons only):**
- Discord: `https://discord.gg/t4unbMVs49`
- X: `https://x.com/Bohrium_AI4S`
- LinkedIn: `https://www.linkedin.com/showcase/bohriumai4s/`

### 10. FAQ Chatbot (floating)
- Bottom-right chat bubble
- Click to open panel with pre-set FAQ suggestions
- Keyword-matching against 10 FAQ entries (subscription, refund, invoices, etc.)
- Fallback: "Contact support@bohrium.com or ask on Discord"

---

## Design System

### Typography
| Use | Font | Weight | Tracking |
|-----|------|--------|----------|
| Headings | Plus Jakarta Sans | 800 (ExtraBold) | -0.02em |
| Body | Inter | 400 (Regular) | default |
| Labels/badges | Inter | 600-700 | 0.04-0.1em |

### Colors
| Token | Value | Use |
|-------|-------|-----|
| Brand Blue | `#5282FF` | Primary accent, buttons, links |
| Cyan | `#3ABFFF` | Gradient mid-point, secondary accent |
| Deep Blue | `#1A53EF` | Gradient endpoint, dark accent |
| Accent gradient | `#5282FF → #3ABFFF → #1A53EF` | CTA buttons, active tabs |
| Text Primary | `#1D2129` | Headings, body text |
| Text Secondary | `#4E5969` | Descriptions |
| Text Muted | `#86909C` | Labels, captions |
| Border | `#E5E6EB` | Dividers, card borders |
| Surface | `#F2F3F5` | Input backgrounds, subtle fills |
| Background | `#FAFBFC` | Page background |
| Background gradient | `#F0F0FD → #F0FAFD` | Section backgrounds |
| Dark bg | `#1D2129` | Workflow section, footer |

**Important:** No purple in product content. Purple (`#7E3EFF` etc.) is reserved for API product line only.

### Spacing & Radius
| Token | Value |
|-------|-------|
| Button/tag radius | 10px |
| Card/panel radius | 14px |
| Container radius | 20px |
| Glass blur | 12-16px |
| Card shadow | `0 8px 40px rgba(82, 130, 255, 0.1)` |

### Effects
- Glass-morphism: `background: rgba(255,255,255,0.85); backdrop-filter: blur(12px); border: 1.5px solid rgba(255,255,255,0.9)`
- Decorative blobs: `filter: blur(40-50px); opacity: 0.1-0.25; border-radius: 20px`

---

## Assets Needed from Design

1. **Hero background** — New brand visual or approved existing asset
2. **Science Navigator screenshots** — One per mode (Lite/Expert/DeepThink)
3. **Product screenshots** — For workflow cards (optional, can use icons)
4. **Partner institution logos** — If keeping partnership section
5. **User testimonial photos** — If using real photos instead of anonymous

---

## Technical Notes

- Current demo is a single `index.html` with inline CSS/JS, zero dependencies
- Production implementation should use the existing frontend stack (Next.js)
- FAQ chatbot is pure frontend keyword-matching — could be upgraded to API-backed later
- Hero typing animation is vanilla JS with `setTimeout`
- Scroll animations use `IntersectionObserver`
- All social links open in new tab (`target="_blank" rel="noopener"`)
- The two current URLs (`bohrium.com/en/intro` and `dp.tech/en/product/bohrium`) should be consolidated — one canonical URL, one 301 redirect

---

## Action Items for Dev

- [ ] Review demo HTML and confirm section structure
- [ ] Provide hero background asset (design team)
- [ ] Provide Science Navigator screenshots for each mode
- [ ] Implement in Next.js using existing component library
- [ ] Set up 301 redirect from duplicate URL
- [ ] Verify Discord invite link is set to never expire
- [ ] Confirm pricing tiers and edu discount copy with product team
