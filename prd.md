# Product Requirements Document (PRD)
## Emigration Aid — Full Website Redesign & Multi-Page Expansion
**Document Version:** 2.0 — Enhanced  
**Prepared by:** Senior Frontend Web Developer  
**Client:** Jamal Associates & Emigration Aid  
**Client Contact:** Khan Abu Rawshan Md Mostofa Jamal — Chief Executive  
**Date:** May 26, 2026  
**Status:** Approved for Development

---

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Project Goals & KPIs](#2-project-goals--kpis)
3. [Target Audience & Personas](#3-target-audience--personas)
4. [User Journey & Conversion Funnel](#4-user-journey--conversion-funnel)
5. [Design System](#5-design-system)
6. [Global Layout & Shared Components](#6-global-layout--shared-components)
7. [Persistent UI Elements](#7-persistent-ui-elements)
8. [Page Inventory & Wireframes](#8-page-inventory--wireframes)
9. [Component Library](#9-component-library)
10. [Micro-interaction Specifications](#10-micro-interaction-specifications)
11. [Form UX & Validation](#11-form-ux--validation)
12. [Analytics & Tracking](#12-analytics--tracking)
13. [SEO Strategy](#13-seo-strategy)
14. [Performance Budget](#14-performance-budget)
15. [Accessibility Standards](#15-accessibility-standards)
16. [Browser & Device Support](#16-browser--device-support)
17. [File & Asset Structure](#17-file--asset-structure)
18. [Shared Code Snippets](#18-shared-code-snippets)
19. [Development Checklist](#19-development-checklist)
20. [Content Inventory](#20-content-inventory)
21. [Phase Rollout & Timeline](#21-phase-rollout--timeline)
22. [Out of Scope (v1.0)](#22-out-of-scope-v10)
23. [Changelog](#23-changelog)
24. [Approval & Sign-off](#24-approval--sign-off)

---

## 1. Executive Summary

Emigration Aid (operating as Jamal Associates & Emigration Aid) is a premier VISA and education consultancy established on September 1, 2009, headquartered in Dhaka, Bangladesh. With 14 dedicated professionals, 500+ successful student placements, and partnerships across 10+ study destinations, the agency has earned significant authority in the Bangladeshi overseas education market.

The client requires a full, multi-page professional website designed to maximise client engagement, build digital brand authority, and convert website visitors — primarily aspiring students and skilled professionals — into booked free consultations.

### Source of Truth
The homepage (`code.html`) is the **absolute single source of truth** for all visual and interaction design decisions. Every page in the site must replicate its dark-mode glassmorphism aesthetic, animation behaviour, navigation structure, and component language with zero visual deviation. Font family is to be migrated from DM Sans to **Google Sans** uniformly across all pages.

### Document Scope
This PRD covers all 11 pages of the website (up from 9 in v1.0), all shared components, UX flows, micro-interactions, analytics instrumentation, SEO strategy, accessibility requirements, performance targets, and deployment checklist.

---

## 2. Project Goals & KPIs

### Primary Goals

| # | Goal | KPI | Target |
|---|------|-----|--------|
| G1 | Drive free consultation bookings | CTA click-through rate | ≥ 5% |
| G2 | Establish brand trust and authority | Avg. session duration | ≥ 3 min |
| G3 | Reduce visitor drop-off | Bounce rate | ≤ 45% |
| G4 | Serve mobile-first Bangladeshi student market | Mobile Lighthouse score | ≥ 90 |
| G5 | Enforce consistent brand identity | Design-system compliance | 100% across all pages |
| G6 | Rank organically for target keywords | Google ranking for top 5 keywords | Page 1 within 6 months |
| G7 | Enable WhatsApp as primary inquiry channel | WhatsApp button click rate | ≥ 8% of sessions |
| G8 | Achieve fast load times on 4G/slow networks | LCP on mobile | < 3.5s |

### Secondary Goals
- Establish the blog as an educational authority resource
- Build a testimonials bank to amplify social proof
- Create a scalable design system that allows future page additions with minimal effort

---

## 3. Target Audience & Personas

### Persona 1 — "Aspiring Rafi" (Primary)
- **Profile:** 21-year-old, BSc graduate from Dhaka University, wants to pursue a Master's in Computer Science in Australia or Canada
- **Device:** Primarily mobile (Android), occasionally laptop
- **Behaviour:** Discovers via Facebook/Instagram, watches YouTube for visa tips, compares agencies on Google
- **Pain Points:** Confused about IELTS requirements, worried about rejection, unsure which university to apply to
- **Goal on site:** Find country-specific information, see success stories, book a free consultation
- **Key pages:** Home → Destinations → Testimonials → Contact

### Persona 2 — "Professional Parisa" (Secondary)
- **Profile:** 34-year-old IT professional, 8 years of experience, wants to migrate to Canada or UK via skilled immigration
- **Device:** Desktop or laptop at work
- **Behaviour:** Researches thoroughly, reads blogs, checks agency credentials, compares PR point systems
- **Pain Points:** Unclear about skilled migration pathways, worried about document requirements
- **Goal on site:** Understand the immigration process, assess agency credibility, make contact
- **Key pages:** Home → Services → About → Contact

### Persona 3 — "Parent Nasrin" (Influencer)
- **Profile:** 48-year-old parent in Dhaka, funding their child's overseas education
- **Device:** Mobile, Facebook
- **Behaviour:** Reads testimonials, looks for trustworthy, established agency, checks contact details
- **Pain Points:** Fears of scams, financial risk, wants guarantee of legitimate process
- **Goal on site:** Verify agency legitimacy, read testimonials, call or WhatsApp directly
- **Key pages:** Home → About → Testimonials → Contact

---

## 4. User Journey & Conversion Funnel

### 4.1 Primary Conversion Funnel

```
AWARENESS
   ↓
Facebook/Instagram Ad  OR  Google Search  OR  Word of Mouth
   ↓
LANDING
   ↓
Homepage (index.html)
  → Hero sees destination flipper → emotional resonance
  → Scrolls to Why Choose Us → builds confidence
  → Sees stat cards (15+ Years / 500+ Students) → trust established
   ↓
EXPLORATION
   ↓
   ├── Clicks "Destinations" → destinations.html
   │     → Sees country cards → clicks specific country
   │     → Clicks "Explore Opportunities" → back to Contact
   │
   ├── Clicks "Services" → services.html
   │     → Reads service cards → sees process timeline
   │     → Clicks "Book Free Consultation" CTA
   │
   └── Clicks "About" → about.html
         → Reads story, sees team, reads testimonials strip
         → Clicks "See All Testimonials" → testimonials.html
   ↓
CONSIDERATION
   ↓
testimonials.html  OR  blog.html
  → Social proof / educational content reinforces trust
   ↓
CONVERSION
   ↓
contact.html
  → Fills multi-step form  OR  clicks WhatsApp button  OR  calls
   ↓
POST-CONVERSION
   ↓
Success state on form → "We'll contact you within 24 hours"
WhatsApp chat opens with pre-filled message
```

### 4.2 Entry Points & Exit Intents

| Entry Point | Landing Page | Expected Persona |
|-------------|-------------|-----------------|
| Facebook "Study Abroad" Ad | index.html or destinations.html | Persona 1 |
| Google "visa consultancy Dhaka" | index.html | All |
| Google "study in Australia Bangladesh" | destinations.html#australia | Persona 1 |
| Google "Canada skilled immigration Dhaka" | services.html#skilled-immigration | Persona 2 |
| Direct / Referral (word of mouth) | index.html | Persona 3 |

### 4.3 Exit Intent Strategy
- Floating WhatsApp button visible on all pages (always accessible)
- Sticky bottom CTA bar on mobile (appears after 40% scroll)
- Every section ends with or contains a CTA pointing to `contact.html`
- Blog articles end with a consultation CTA banner

---

## 5. Design System

### 5.1 Mandatory Design Tokens

All pages **must** import and use the exact Tailwind configuration from the homepage. Do not override these values without explicit written approval.

```
/* Core Surfaces */
--surface:                    #111317
--surface-container-low:      #1A1C20
--surface-container:          #1E2024
--surface-container-high:     #282A2E
--surface-container-highest:  #333539
--surface-bright:             #37393E
--background:                 #111317

/* Brand Colours */
--brand-blue:                 #1F5FA6
--brand-green:                #3DA64B
--gradient-journey:           linear-gradient(135deg, #1F5FA6 0%, #3DA64B 100%)

/* Semantic Colours */
--primary:          #abc7ff   /* Blue accent / interactive elements */
--secondary:        #43eda0   /* Green accent */
--tertiary:         #ffb77b   /* Orange accent */
--error:            #ffb4ab

/* Text */
--on-surface:       #e2e2e8   /* Primary text */
--on-surface-var:   #c1c6d5   /* Secondary text */
--outline:          #8b919f
--outline-variant:  #414753   /* Borders */

/* Glass Card */
--glass-bg:         rgba(255,255,255,0.04)
--glass-blur:       20px
--glass-border:     rgba(255,255,255,0.08)
--glass-shadow:     0 10px 40px 0 rgba(0,0,0,0.4)
```

### 5.2 Typography

**Font Family:** Google Sans (replaces DM Sans on all pages)

```html
<!-- Required in every page <head> -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Google+Sans:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
```

**Fallback chain:** `'Google Sans', 'Product Sans', 'Nunito', sans-serif`

**Type Scale:**

| Role | Desktop Size | Mobile Size | Weight | Line Height | Letter Spacing |
|------|-------------|-------------|--------|-------------|----------------|
| Hero H1 | 96–128px | 48px | 900 (Black) | 0.9 | -0.03em |
| Section H2 | 48–80px | 32px | 800 (ExtraBold) | 1.0 | -0.02em |
| Sub-H2 | 32–40px | 24px | 700 (Bold) | 1.1 | -0.01em |
| Card H3 | 24px | 20px | 700 (Bold) | 1.3 | 0 |
| Card H4 | 20px | 18px | 600 (SemiBold) | 1.4 | 0 |
| Body Large | 18px | 16px | 400 | 28px | 0 |
| Body Medium | 16px | 15px | 400 | 24px | 0 |
| Body Small | 14px | 13px | 400 | 20px | 0 |
| Label / Badge | 12px | 12px | 600 | 16px | +0.2em |
| Nav Link (fullscreen) | 64px | 40px | 700 | 1.0 | -0.02em |

> **Critical Rule:** All body text in card and section contexts must be `text-lg md:text-xl` minimum. No small/light text in hero or card contexts. Visibility is paramount.

### 5.3 Spacing System

```
Container max-width: 1280px  (max-w-container-max)
Desktop horizontal:  40px    (px-margin-desktop)
Mobile horizontal:   16px    (px-margin-mobile)
Gutter:              24px
Section vertical:    py-24 md:py-40
Card padding:        p-8 md:p-10
Card gap:            gap-6 md:gap-8
```

### 5.4 Border Radius Scale

```
Default / small:   2px    (rounded)
Medium:            4px    (rounded-lg)
Large:             8px    (rounded-xl)
Card:              24px   (rounded-3xl)
Floating card:     32px   (rounded-[2rem])
Hero roundoff:     48px   (rounded-[3rem])
Pill / button:     999px  (rounded-full)
```

### 5.5 Shadow Scale

```
Card default:   0 10px 40px 0 rgba(0,0,0,0.4)
Card hover:     0 20px 50px -10px rgba(61,166,75,0.3)
Button:         0 8px 32px rgba(0,0,0,0.3)
Button hover:   0 16px 48px rgba(0,0,0,0.5)
Nav:            0 1px 12px rgba(0,0,0,0.3)
```

### 5.6 Motion & Animation Catalogue

| Animation | Class / Selector | Behaviour | Duration | Easing |
|-----------|-----------------|-----------|----------|--------|
| Scroll reveal | `.animate-fade-up` | opacity 0→1, translateY 40→0 | 0.8s | ease-out |
| Card hover lift | `.interactive-card:hover` | translateY(-8px) scale(1.03) | 0.5s | cubic-bezier(0.175, 0.885, 0.32, 1.275) |
| Card hover glow | `.interactive-card:hover` | border-color → green, box-shadow green | 0.5s | ease |
| Card inner gradient | `.interactive-card:hover::before` | opacity 0→1 | 0.5s | ease |
| Icon spin-scale | `.interactive-card:hover .card-icon` | scale(1.25) rotate(15deg) | 0.5s | ease |
| Float loop | `.floating-card` | translateY 0→-15px→0 | 8s | ease-in-out |
| Float stagger | `.floating-card:nth-child(n)` | delay: 1.5s, 3s, 4.5s | — | — |
| Mesh gradient | `.mesh-gradient-bg` | background-position 0%→100%→0% | 20s | ease-in-out alternate |
| Mouse spotlight | `.spotlight-overlay` | radial-gradient follows cursor | real-time | — |
| Word flipper | `#hero-flipper` | translateY steps, 9 words | 27s | cubic-bezier(0.68,-0.55,0.265,1.55) |
| Underline draw | `.draw-underline` | width 0→100% | 3s | ease-out |
| Flag slide | `.flag-anim-N` | translateX 100%→0→-100% | 27s | cubic-bezier(0.68,-0.55,0.265,1.55) |
| Number count-up | `.stat-number[data-target]` | 0 → target number on scroll | 2s | ease-out |
| Nav blur change | `#mainNav` on scroll | bg-surface/70 → bg-surface/95 + shadow | 300ms | ease |
| Menu open/close | `#fullscreen-menu` | opacity 0→1 | 300ms | ease-in-out |
| Menu links stagger | `.menu-link` | translateY 20→0, opacity 0→1 | 0.4s | ease-out |
| WhatsApp pulse | `.whatsapp-fab` | scale 1→1.1→1 ring pulse | 2s | ease-in-out infinite |
| Scroll progress | `#scroll-progress` | width 0→100% | real-time | — |
| Back-to-top | `#back-to-top` | opacity 0→1 after 300px scroll | 300ms | ease |
| Toast notification | `.toast` | translateY 100%→0 | 400ms | cubic-bezier(0.175, 0.885, 0.32, 1.275) |
| Skeleton shimmer | `.skeleton` | background-position -200%→200% | 1.5s | ease-in-out infinite |
| Page transition | `body` on navigate | opacity 1→0→1 | 200ms each | ease |

### 5.7 Colour Usage Rules

| Context | Colour | Usage |
|---------|--------|-------|
| Primary interactive | `#abc7ff` | Links, active icons, highlights |
| Primary CTA gradient | `#1F5FA6 → #3DA64B` | Main buttons, key banners |
| Secondary accent | `#43eda0` | Success states, secondary badges |
| Tertiary accent | `#ffb77b` | Warnings, feature callouts |
| Card border default | `rgba(255,255,255,0.08)` | All glass cards |
| Card border hover | `rgba(61,166,75,0.5)` | Green on hover |
| Text primary | `#e2e2e8` | All headings and body |
| Text secondary | `#c1c6d5` | Subtitles, card body text |
| Destructive / Error | `#ffb4ab` | Form errors, warnings |
| WhatsApp brand | `#25D366` | WhatsApp FAB only |

---

## 6. Global Layout & Shared Components

### 6.1 Mandatory Elements — Every Page

Every `.html` file must contain **all** of the following, structurally identical to the homepage:

| # | Element | ID / Class | Notes |
|---|---------|-----------|-------|
| 1 | `<html>` attributes | `class="scroll-smooth dark" lang="en"` | Required |
| 2 | `<head>` block | — | Full config (see §18) |
| 3 | Spotlight overlay | `.spotlight-overlay` | Fixed, z-40 |
| 4 | Scroll progress bar | `#scroll-progress` | Fixed top, z-50, new in v2 |
| 5 | Navigation bar | `#mainNav` | Fixed top, z-50 |
| 6 | Fullscreen overlay menu | `#fullscreen-menu` | z-60 |
| 7 | Main content | `<main>` | All sections inside |
| 8 | WhatsApp FAB | `#whatsapp-fab` | Fixed bottom-right, z-50, new in v2 |
| 9 | Back-to-top button | `#back-to-top` | Fixed bottom-right above FAB, new in v2 |
| 10 | Mobile sticky CTA | `#mobile-sticky-cta` | Fixed bottom, mobile only, new in v2 |
| 11 | Cookie banner | `#cookie-banner` | Fixed bottom, shown on first visit, new in v2 |
| 12 | Footer | `<footer>` | 4-column grid |
| 13 | Toast container | `#toast-container` | Fixed top-right, z-60, new in v2 |
| 14 | Shared JS block | `<script>` | Bottom of body |

### 6.2 Navigation Specification

**Structure:** Fixed top bar → hamburger icon → fullscreen dark overlay with animated links

**Nav Bar elements (left to right):**
- Logo image (`assets/images/logo.png`, `h-10 md:h-12`)
- Brand text `"Emigration Aid"` (`text-primary`, `text-xl md:text-2xl font-bold`)
- [Spacer]
- Hamburger icon button (`#menuToggle`, Material Symbol `menu`, `text-3xl md:text-4xl`)

**Scroll behaviour:**
- Default: `bg-surface/70 backdrop-blur-md`
- After 50px scroll: `bg-surface/95 shadow-md` (transition 300ms ease)

**Fullscreen overlay menu links:**

| Label | Href | Transition Delay |
|-------|------|-----------------|
| Home | `index.html` | 100ms |
| Services | `services.html` | 150ms |
| Destinations | `destinations.html` | 200ms |
| About | `about.html` | 250ms |
| Contact | `contact.html` | 300ms |
| Book Free Consultation (mobile CTA) | `contact.html` | 350ms |

**Active page indication:** Add `text-primary` class to the current page's menu-link via JS on DOMContentLoaded.

```javascript
// Active nav link
const currentPage = window.location.pathname.split('/').pop() || 'index.html';
document.querySelectorAll('.menu-link[href]').forEach(link => {
  if (link.getAttribute('href') === currentPage) {
    link.classList.add('text-primary');
    link.setAttribute('aria-current', 'page');
  }
});
```

### 6.3 Footer Specification

**4-column grid layout** (1-col mobile → 2-col tablet → 4-col desktop)

**Column 1 — Brand:**
- Company name (`text-2xl md:text-3xl font-bold`)
- Tagline: `"Navigating your global future with expert guidance and unwavering support."`
- Facebook icon link → `https://facebook.com/emigrationaid` (opens in new tab)

**Column 2 — Services:**
Student Recruitment, Skilled Immigration, Counseling, Pre-Departure Briefings, Post-Arrival Assistance (all anchor to `services.html#[anchor]`)

**Column 3 — Company:**
About Us, Destinations, Testimonials, Blog & Resources, Contact

**Column 4 — Legal:**
Privacy Policy, Terms of Service

**Copyright bar:**
`© 2025 Emigration Aid — Jamal Associates. All rights reserved.` | `"Bridging Your Path to Global Education"`

---

## 7. Persistent UI Elements

### 7.1 WhatsApp Floating Action Button (FAB)

Critical for the Bangladeshi market where WhatsApp is the dominant communication channel.

**Specification:**
- Position: `fixed bottom-6 right-6` (mobile: `bottom-20 right-4` to clear mobile sticky CTA)
- Size: `w-16 h-16 md:w-20 md:h-20`
- Background: `#25D366` (WhatsApp brand green)
- Icon: WhatsApp SVG logo (white)
- Border radius: `rounded-full`
- Shadow: `0 8px 32px rgba(37,211,102,0.4)`
- Animation: Pulse ring (`::after` pseudo-element, scale 1→1.5, opacity 1→0, 2s infinite)
- Tooltip (desktop hover): `"Chat on WhatsApp"` floating label, left of FAB
- `href`: `https://wa.me/8801713111133?text=Hello%2C%20I%20would%20like%20to%20enquire%20about%20your%20services.`
- `target="_blank" rel="noopener noreferrer"`
- `aria-label="Chat with us on WhatsApp"`

**Pre-filled WhatsApp message:** `"Hello, I would like to enquire about your consultancy services."`

### 7.2 Scroll Progress Bar

**Specification:**
- Position: `fixed top-0 left-0 w-full z-[51]` (above nav)
- Height: `3px`
- Background: `gradient-journey` (`#1F5FA6 → #3DA64B`)
- Width: Driven by JS scroll percentage
- `id="scroll-progress"`

```javascript
window.addEventListener('scroll', () => {
  const scrollTop = document.documentElement.scrollTop;
  const scrollHeight = document.documentElement.scrollHeight - document.documentElement.clientHeight;
  const progress = (scrollTop / scrollHeight) * 100;
  document.getElementById('scroll-progress').style.width = `${progress}%`;
});
```

### 7.3 Back-to-Top Button

**Specification:**
- Position: `fixed bottom-24 right-6` (above WhatsApp FAB)
- Size: `w-12 h-12`
- Background: `bg-surface-container-high` with `border border-outline-variant/20`
- Icon: Material Symbol `keyboard_arrow_up`
- Visible: only after 300px scroll (opacity transition)
- On click: `window.scrollTo({ top: 0, behavior: 'smooth' })`

### 7.4 Mobile Sticky CTA Bar

Visible **only on mobile** (`md:hidden`), appears after user scrolls 40% of page height.

**Specification:**
- Position: `fixed bottom-0 left-0 w-full z-40`
- Background: `bg-surface-container-low/95 backdrop-blur-md border-t border-outline-variant/20`
- Content: Two buttons side by side
  - Left (50%): Phone icon + `"Call Now"` → `tel:+8801713111133`
  - Right (50%): Chat icon + `"WhatsApp"` → WhatsApp link
- Height: `h-16` (`64px`)
- Font: `text-base font-bold`

### 7.5 Cookie Consent Banner

**Specification:**
- Position: `fixed bottom-0 left-0 w-full z-[55]`
- Appears on first visit (check `localStorage.getItem('cookieConsent')`)
- Background: `bg-surface-container/95 backdrop-blur-md border-t border-outline-variant/20`
- Content: `"We use cookies to enhance your experience."` + `"Learn More"` link (→ `privacy.html`) + `"Accept"` button (gradient-journey)
- On accept: set `localStorage.setItem('cookieConsent', 'true')`, hide banner
- On dismiss: same as accept

### 7.6 Toast Notification System

For form success/error feedback.

**Specification:**
- Container: `#toast-container`, `fixed top-6 right-6 z-[60] flex flex-col gap-3`
- Toast card: `rounded-2xl p-4 md:p-6 glass-card flex items-center gap-4 min-w-[300px] max-w-[400px]`
- Types: `success` (green icon `check_circle`), `error` (red icon `error`), `info` (blue icon `info`)
- Auto-dismiss: 4 seconds
- Animation: slide in from right, slide out to right

---

## 8. Page Inventory & Wireframes

### 8.1 Homepage — `index.html` *(Adapt Existing)*

> **Status:** Exists as `code.html`. Requires font migration + link wiring + new persistent elements.

**Adaptation Tasks Checklist:**
- [ ] Replace DM Sans CDN with Google Sans CDN
- [ ] Update all `fontFamily` references in Tailwind config
- [ ] Wire nav links to actual `.html` files
- [ ] Wire footer links to corresponding pages
- [ ] Point logo `src` to `assets/images/logo.png`
- [ ] Add `#scroll-progress` bar
- [ ] Add `#whatsapp-fab`
- [ ] Add `#back-to-top` button
- [ ] Add `#mobile-sticky-cta`
- [ ] Add `#cookie-banner`
- [ ] Add active nav link JS
- [ ] Add `aria-current="page"` to Home link
- [ ] Add Google Analytics 4 snippet
- [ ] Add Facebook Pixel snippet

**Wireframe:**
```
┌─────────────────────────────────────────────────────┐
│ [Scroll Progress Bar]                               │
├─────────────────────────────────────────────────────┤
│ [NAV] Logo + "Emigration Aid"        [☰ Menu]       │
├─────────────────────────────────────────────────────┤
│                                                     │
│  HERO                           [Flag Showcase]     │
│  "Bridging Your Path to"        [Animated: AU/CA/  │
│  [Word Flipper: Australia...]    UK/US/PL/DK/HU/FR] │
│                                                     │
│  [Book Free Consultation ▶]                         │
│                                                     │
├─────────────────────────────────────────────────────┤
│  WHY CHOOSE US (mesh-gradient-bg)                   │
│                                                     │
│  [15+ Years] [500+ Students] [14 Team] [10+ Dest]  │
│                                                     │
│  [Decade] [Track Record] [Network]                  │
│  [End-to-End] [Ethical]                             │
│                                                     │
├─────────────────────────────────────────────────────┤
│  NEW: QUICK DESTINATION STRIP (added in v2)         │
│  🇦🇺 🇨🇦 🇬🇧 🇺🇸 🇵🇱 🇩🇰 🇭🇺 🇫🇷 → destinations.html     │
├─────────────────────────────────────────────────────┤
│  NEW: SERVICES PREVIEW (3 cards, added in v2)       │
│  "See All Services →" CTA                           │
├─────────────────────────────────────────────────────┤
│  NEW: TESTIMONIAL STRIP (2 cards, added in v2)      │
│  "See All Testimonials →" CTA                       │
├─────────────────────────────────────────────────────┤
│  [FOOTER]                                           │
└─────────────────────────────────────────────────────┘
                                         [💬 WhatsApp]
                                         [⬆ Back-top]
[Mobile: ─────[📞 Call Now]──[💬 WhatsApp]────────────]
```

**New Sections to Add to Homepage (v2):**

**Quick Destination Strip:**
Horizontally scrollable row of flag pills (emoji flag + country name) linking to anchors on `destinations.html`. On desktop: 9 pills in a flex-wrap row. Background: `bg-surface-container-low`, `rounded-3xl`.

**Services Preview (3 Cards):**
Show first 3 service cards (Student Recruitment, Skilled Immigration, Counseling) in a 3-col grid. Each card has icon, title, 1-sentence description, and `"Learn More →"` link. Section headline: `"Our Services"`. CTA: `"View All Services →"` → `services.html`.

**Testimonial Strip (2 Cards):**
Show 2 testimonial quote cards side-by-side (or stacked mobile). Section headline: `"What Our Students Say"`. CTA: `"Read All Testimonials →"` → `testimonials.html`.

---

### 8.2 Services Page — `services.html`

**Purpose:** Full detail on all 5 services. Primary conversion page.

**Wireframe:**
```
┌─────────────────────────────────────────────────────┐
│ [NAV] [SCROLL PROGRESS]                             │
├─────────────────────────────────────────────────────┤
│  HERO (mesh-gradient-bg)                            │
│  Badge: "What We Do"                                │
│  H1: "Everything You Need —                         │
│        Start to Finish"                             │
│  Sub: "From choosing your university to settling in"│
│  [Book Free Consultation ▶]                         │
│  [Animated icon cluster: 5 service icons rotating]  │
├─────────────────────────────────────────────────────┤
│  SERVICE NAVIGATION TABS (sticky below nav)         │
│  [Student] [Immigration] [Counseling]               │
│  [Pre-Depart.] [Post-Arrival]                       │
├─────────────────────────────────────────────────────┤
│  SERVICE DETAIL CARDS (full-width, alternating)     │
│  #student-recruitment                               │
│  #skilled-immigration                               │
│  #counseling                                        │
│  #pre-departure                                     │
│  #post-arrival                                      │
├─────────────────────────────────────────────────────┤
│  PROCESS TIMELINE                                   │
│  ①Consult → ②Select → ③Apply → ④Visa → ⑤Arrive    │
├─────────────────────────────────────────────────────┤
│  FAQ ACCORDION (Services-specific)                  │
├─────────────────────────────────────────────────────┤
│  BOTTOM CTA BANNER (gradient-journey)               │
│  "Ready to Begin Your Journey?"                     │
│  [Book Free Consultation] [Call Us Now]             │
├─────────────────────────────────────────────────────┤
│  [FOOTER]                                           │
└─────────────────────────────────────────────────────┘
```

**Section Specifications:**

**Hero:**
- Headline: `"Everything You Need — Start to Finish"` | `text-5xl md:text-8xl font-black`
- Sub: `text-xl md:text-2xl font-medium`
- Badge pill above headline: `"What We Do"` | `bg-primary/10 text-primary rounded-full px-4 py-2 text-label-md`
- Animated 5-icon orbit ring (CSS keyframe, icons rotate around a centre point)

**Sticky Service Tabs:**
- `position: sticky; top: 72px` (below nav)
- `z-index: 30`
- Scrolls horizontally on mobile
- On click: smooth scroll to corresponding section anchor
- Active tab: `bg-surface-container text-primary border-b-2 border-primary`

**Service Detail Cards:**
Each service is a full-width `interactive-card` with:
- Left side (60%): Service icon (large, `text-5xl`), service name (`text-3xl md:text-4xl font-black`), description paragraph (`text-lg md:text-xl`), bullet list of sub-services (with check icons in green), `"Book This Service →"` button
- Right side (40%): Large decorative icon or abstract SVG illustration

Services and their details:

| ID | Service | Icon | Accent | Sub-items |
|----|---------|------|--------|-----------|
| `#student-recruitment` | Student Recruitment | `school` | Primary Blue | Course guidance, Application support, Visa prep & interview |
| `#skilled-immigration` | Skilled Immigration | `flight_takeoff` | Brand Green | Skilled migration pathways, Paperwork & procedures, Job search & placement |
| `#counseling` | Counseling Services | `support_agent` | Tertiary Orange | Personalised sessions, Scholarship & financial aid info |
| `#pre-departure` | Pre-Departure Briefings | `luggage` | Primary Blue | Orientation programs, Cultural & academic adjustment |
| `#post-arrival` | Post-Arrival Assistance | `home_pin` | Brand Green | Accommodation support, Ongoing study period support |

**Process Timeline:**
- 5-step horizontal (desktop) / vertical (mobile) timeline
- Each step: numbered circle (`gradient-journey`), step title (`text-xl font-bold`), 2-line description
- Connecting line animates on scroll (CSS `width: 0→100%` triggered by IntersectionObserver)
- Steps: `Initial Consultation` → `University / Pathway Selection` → `Application Filing` → `Visa Processing` → `Pre-Departure & Arrival`

**Services FAQ Accordion:**
5–7 common questions (e.g., "How long does the visa process take?", "What documents do I need?", "Do you offer scholarship guidance?"). Each item: question (`text-lg md:text-xl font-bold`) + chevron icon, animated expand/collapse answer panel.

---

### 8.3 Destinations Page — `destinations.html`

**Purpose:** Inspire aspiration, country-specific inquiry funnel.

**Wireframe:**
```
┌─────────────────────────────────────────────────────┐
│ [NAV] [SCROLL PROGRESS]                             │
├─────────────────────────────────────────────────────┤
│  HERO                                               │
│  Badge: "Where Will You Go?"                        │
│  H1: "Your World of                                 │
│        Opportunities"                               │
│  Animated world map SVG (CSS highlight countries)   │
├─────────────────────────────────────────────────────┤
│  ANIMATED STATS BAR                                 │
│  10+ Countries | 500+ Placements | 15+ Years        │
│  | 100% Visa Support                                │
├─────────────────────────────────────────────────────┤
│  DESTINATION FILTER TABS                            │
│  [All] [English-Speaking] [European] [Scholarships] │
├─────────────────────────────────────────────────────┤
│  DESTINATION GRID (3-col desktop / 1-col mobile)    │
│  9 country cards                                    │
├─────────────────────────────────────────────────────┤
│  SCHOLARSHIP SPOTLIGHT (3 cards horizontal scroll)  │
├─────────────────────────────────────────────────────┤
│  BOTTOM CTA BANNER                                  │
├─────────────────────────────────────────────────────┤
│  [FOOTER]                                           │
└─────────────────────────────────────────────────────┘
```

**Destination Card Specification (each country):**

```
┌──────────────────────────────────┐
│  [Country Flag — full bleed top  │
│   with gradient overlay]         │
│  ████████████████████████████    │
│  ████████████████████████████    │
├──────────────────────────────────┤
│  🏳️ COUNTRY NAME  [Badge: EU/EN] │
│  ─────────────────────────────── │
│  ✓ Highlight 1                   │
│  ✓ Highlight 2                   │
│  ✓ Highlight 3                   │
│  ─────────────────────────────── │
│  Avg. Tuition: $X,XXX/yr         │
│                                  │
│  [Explore Opportunities →]       │
└──────────────────────────────────┘
```

**Destination Data Table:**

| Country | Flag | Badge | Highlight 1 | Highlight 2 | Highlight 3 | Avg Tuition/yr |
|---------|------|-------|-------------|-------------|-------------|----------------|
| Australia | 🇦🇺 | English | QS Top Universities | Post-Study Work Visa (2–4yr) | Clear PR Pathway | AUD 20,000–45,000 |
| Canada | 🇨🇦 | English | Express Entry & PGWP | Affordable Living Costs | Multicultural Society | CAD 15,000–35,000 |
| United Kingdom | 🇬🇧 | English | Russell Group Institutions | 2-Year Graduate Route Visa | World-class Research | GBP 12,000–30,000 |
| United States | 🇺🇸 | English | Ivy League Access | OPT/CPT Work Options | Research Excellence | USD 20,000–60,000 |
| Poland | 🇵🇱 | Europe | Affordable EU Education | Schengen Area Access | English-taught Programmes | EUR 2,000–6,000 |
| Denmark | 🇩🇰 | Europe | Scandinavian Quality | Some Tuition-Free Programmes | High Quality of Life | DKK 45,000–120,000 |
| Hungary | 🇭🇺 | Europe | Stipendium Hungaricum Scholarship | EU-recognised Degrees | Low Living Costs | EUR 3,000–8,000 |
| France | 🇫🇷 | Europe | Campus France Network | Grandes Écoles | Cultural Capital of Europe | EUR 3,000–15,000 |
| Other Europe | 🌍 | Europe | Germany, Netherlands, more | Varied Scholarship Options | EU Mobility Benefits | Varies |

**Filter behaviour (JS):** On tab click, cards with non-matching `data-category` attribute fade out (opacity 0, display none). Selected tab gets `text-primary border-b-2 border-primary`.

**Animated Stats Bar:** On scroll into view (IntersectionObserver), numbers count up from 0 to target using `requestAnimationFrame`.

**Scholarship Spotlight:**
3 featured scholarships as horizontal-scroll cards on mobile, 3-col grid on desktop:
- Chevening Scholarship (UK, fully funded)
- Stipendium Hungaricum (Hungary, fully funded)
- Vanier Canada Graduate Scholarships
Each card: scholarship name, country flag + name, key benefit, `"Learn More"` link.

---

### 8.4 About Page — `about.html`

**Purpose:** Humanise brand, build trust, demonstrate authority.

**Wireframe:**
```
┌─────────────────────────────────────────────────────┐
│ [NAV] [SCROLL PROGRESS]                             │
├─────────────────────────────────────────────────────┤
│  HERO                                               │
│  Badge: "Est. September 1, 2009"                    │
│  H1: "15+ Years of Opening Doors"                   │
│  Floating orb animation background                  │
├─────────────────────────────────────────────────────┤
│  OUR STORY (2-col: narrative + milestone timeline)  │
├─────────────────────────────────────────────────────┤
│  MISSION / VISION / VALUES                          │
│  (3 tall cards)                                     │
├─────────────────────────────────────────────────────┤
│  LEADERSHIP FEATURE CARD                            │
│  (Director profile)                                 │
├─────────────────────────────────────────────────────┤
│  TEAM STATS + ROLE CARDS                            │
├─────────────────────────────────────────────────────┤
│  TESTIMONIALS PREVIEW STRIP                         │
│  (2 cards + "See All Testimonials →")               │
├─────────────────────────────────────────────────────┤
│  BOTTOM CTA BANNER                                  │
├─────────────────────────────────────────────────────┤
│  [FOOTER]                                           │
└─────────────────────────────────────────────────────┘
```

**Hero floating orbs:** 3–5 CSS `div` elements with `border-radius: 50%`, large, blurred (`filter: blur(80px)`), slow-moving with `@keyframes float`. Colours: `rgba(31,95,166,0.3)`, `rgba(61,166,75,0.2)`, `rgba(171,199,255,0.1)`. These create an ambient light effect behind the headline.

**Milestone Timeline (vertical, right column):**

| Year | Milestone |
|------|-----------|
| 2009 | Founded — Jamal Associates & Emigration Aid established |
| 2012 | First 50 successful student placements |
| 2015 | Expanded to 7 study destinations |
| 2018 | Reached 200+ student placements |
| 2021 | Team grew to 14 professionals |
| 2024 | 500+ successful placements achieved |

Each milestone: year badge (gradient-journey), title, 1-line description. Vertical connecting line animates on scroll.

**Mission / Vision / Values:**

| Card | Icon | Title | Content |
|------|------|-------|---------|
| Mission | `explore` | Our Mission | Full mission statement from company profile |
| Vision | `visibility` | Our Vision | Full vision statement from company profile |
| Values | `balance` | Our Values | 4-value grid: Integrity, Excellence, Commitment, Innovation |

**Leadership Feature Card:**
Full-width `interactive-card`, large, two-column:
- Left: Director's name (`text-3xl md:text-5xl font-black`), title badge, quote (`"Bridging Your Path to Global Education"`), contact buttons (phone + email + WhatsApp)
- Right: Abstract graphic or placeholder silhouette (to be replaced with actual photo)

**Team Role Cards (2×2 or 4-col grid):**
`Visa Counsellors`, `Immigration Specialists`, `Student Advisors`, `Documentation Experts`
Each: icon, role name (`text-xl font-bold`), count badge.

---

### 8.5 Contact Page — `contact.html`

**Purpose:** Highest-priority conversion page. Every path on the site leads here.

**Wireframe:**
```
┌─────────────────────────────────────────────────────┐
│ [NAV] [SCROLL PROGRESS]                             │
├─────────────────────────────────────────────────────┤
│  HERO (clean, fast)                                 │
│  H1: "Let's Plan Your Journey"                      │
│  Sub: "Free consultation. No obligation."           │
│  Trust badges: [15+ Years] [500+ Placed] [Free]     │
├─────────────────────────────────────────────────────┤
│  MAIN SECTION (2-col desktop / 1-col mobile)        │
│  ┌────────────────────┐ ┌────────────────────────┐  │
│  │  MULTI-STEP FORM   │ │  CONTACT DETAILS       │  │
│  │                    │ │  + Office Hours Card   │  │
│  │  Step 1/3: Info    │ │  + Google Maps embed   │  │
│  │  Step 2/3: Goal    │ │                        │  │
│  │  Step 3/3: Message │ │                        │  │
│  └────────────────────┘ └────────────────────────┘  │
├─────────────────────────────────────────────────────┤
│  QUICK CONTACT STRIP                                │
│  [📞 Call] [📧 Email] [💬 WhatsApp] [📘 Facebook]  │
├─────────────────────────────────────────────────────┤
│  [FOOTER]                                           │
└─────────────────────────────────────────────────────┘
```

**Multi-Step Form Specification (NEW in v2):**

Replaces single-page form with a 3-step wizard for higher completion rates:

**Step 1/3 — Personal Information:**
- Progress bar at top (`33%`, gradient-journey fill)
- Step label: `"Step 1 of 3 — About You"`
- Fields: Full Name (`text`, required), Email (`email`, required), Phone (`tel`, required, `+880` prefix label)
- Next Button: `"Continue →"` (gradient-journey, full-width)

**Step 2/3 — Your Goal:**
- Progress bar: `66%`
- Step label: `"Step 2 of 3 — Your Goal"`
- Fields:
  - Service Interest (`select`): Student Recruitment / Skilled Immigration / Counseling / Pre-Departure / Post-Arrival
  - Preferred Destination (`select`): 9 countries + "Not sure yet"
  - Timeline (`select`): Within 3 months / 3–6 months / 6–12 months / Just exploring
- Back + Next buttons

**Step 3/3 — Your Message:**
- Progress bar: `100%`
- Step label: `"Step 3 of 3 — Tell Us More"`
- Fields: Message (`textarea`, 4 rows, optional but encouraged)
- Checkbox: `"I agree to be contacted via WhatsApp"` (pre-ticked)
- Submit Button: `"Book Free Consultation ✓"` (gradient-journey, full-width, `h-16`)

**Success State:**
Replace form area with: animated checkmark (CSS draw animation), `"Consultation Requested!"` heading, `"We'll reach you within 24 hours."` body, `"Chat on WhatsApp Now →"` secondary CTA.

**Contact Detail Cards (right column):**

| Icon | Label | Value | Link |
|------|-------|-------|------|
| `location_on` | Address | Suite A4, Toma Angelica, 280/1-281/1 North Shahjahanpur, Dhaka 1217 | Google Maps link |
| `call` | Phone | +8801713111133 | `tel:` |
| `call` | Phone | +8801715866866 | `tel:` |
| `call` | Phone | +8801321200700 | `tel:` |
| `mail` | Email | emigrationaid@gmail.com | `mailto:` |
| `mail` | Email | jamal@consultant.com | `mailto:` |
| `chat` | WhatsApp | +8801713111133 | `wa.me/` |
| `language` | Facebook | facebook.com/emigrationaid | External link |

**Office Hours Card:**

| Day | Hours |
|-----|-------|
| Saturday – Thursday | 9:00 AM – 6:00 PM |
| Friday | Closed |

---

### 8.6 Testimonials Page — `testimonials.html`

**Purpose:** Social proof repository. Converts hesitant visitors.

**Sections:**
1. **Hero:** `"500+ Dreams, All Achieved"` — animated number counter, sub: `"Real students. Real results. Real lives changed."`
2. **Masonry grid:** 3-col (desktop) / 1-col (mobile), testimonial quote cards
3. **Facebook Posts Section:** 5 embedded/linked Facebook post cards (from company profile links)
4. **Stats bar:** Repeat of key stats in an `interactive-card` row
5. **CTA Banner:** `"Your success story starts here"` + Book button

**Testimonial Card:**
- Large green `"` quote mark (decorative)
- Quote text (`text-lg md:text-xl`)
- Student name + destination flag emoji
- Year badge (`text-label-md`)
- Facebook source icon link

---

### 8.7 Blog / Resources Page — `blog.html`

**Purpose:** SEO authority, educational content, organic traffic.

**Sections:**
1. **Hero:** `"Your Global Education Resource"` + search bar
2. **Category filter pills:** All / Australia / Canada / UK / Visa Tips / Scholarships / Immigration
3. **Featured Article (full-width):** Largest card, latest post
4. **Article grid:** 3-col (desktop) / 1-col (mobile)
5. **Newsletter CTA:** Email input + Subscribe

**Article Card:**
- Category badge (pill)
- Thumbnail area (gradient placeholder if no image)
- Title (`text-xl md:text-2xl font-bold`)
- 2-line excerpt
- Read time badge + `"Read More →"`

**Suggested Initial Article Titles:**

| Title | Category | Est. Read Time |
|-------|----------|---------------|
| How to Apply for Australian Student Visa (Subclass 500): Step-by-Step Guide | Australia | 8 min |
| Top 10 Scholarships for Bangladeshi Students in 2025 | Scholarships | 6 min |
| Canada Express Entry: A Complete Guide for 2025 | Canada | 10 min |
| UK Graduate Route Visa Explained: Work in the UK After Your Degree | UK | 5 min |
| 10 Common Reasons for Student Visa Rejection (And How to Avoid Them) | Visa Tips |  7 min |
| Life as a Bangladeshi Student in Poland: Costs, Culture & More | Poland | 6 min |

---

### 8.8 404 Error Page — `404.html` *(New in v2)*

**Purpose:** Retain lost visitors, guide them back.

**Content:**
- Large `"404"` headline (`text-9xl font-black text-primary/20` background, `text-6xl text-on-surface` foreground)
- `"Looks like this page got a visa to somewhere else."` (on-brand humorous copy)
- Sub: `"The page you're looking for doesn't exist."`
- Two buttons: `"Go Home"` (gradient CTA) and `"Contact Us"` (ghost)
- Quick links: Home / Services / Destinations / Contact
- No footer navigation needed — keep page minimal

---

### 8.9 Privacy Policy — `privacy.html`
### 8.10 Terms of Service — `terms.html`

Both pages:
- Full nav + footer
- `mesh-gradient-bg` hero with page title and last-updated date
- Centred `max-w-4xl` content column
- Section headings: `text-2xl md:text-3xl font-bold text-primary`
- Body: `text-lg text-on-surface-variant leading-relaxed`
- Back-to-top anchor links between sections

---

## 9. Component Library

All components are reusable HTML+CSS+JS patterns. Build once, copy across pages.

### 9.1 Section Header Component

```html
<div class="text-center mb-16 md:mb-28 animate-fade-up">
  <!-- Optional badge -->
  <span class="inline-block mb-4 px-5 py-2 rounded-full bg-primary/10 
    text-primary text-label-md tracking-widest uppercase">
    [Badge Text]
  </span>
  <h2 class="text-4xl md:text-6xl lg:text-8xl text-on-surface font-black 
    tracking-tight mb-6 md:mb-8">
    [Section Headline]
  </h2>
  <p class="text-on-surface-variant text-xl md:text-2xl lg:text-3xl 
    max-w-4xl mx-auto font-medium">
    [Section sub-headline]
  </p>
</div>
```

### 9.2 CTA Button — Primary (Gradient)

```html
<a href="contact.html" 
  class="inline-flex items-center justify-center gap-3 rounded-full 
    gradient-journey text-on-primary font-bold shadow-xl 
    hover:shadow-2xl hover:-translate-y-1 transition-all duration-300 
    text-lg md:text-2xl h-16 md:h-20 px-8 md:px-16 tracking-wide">
  [Button Label]
  <span class="material-symbols-outlined">arrow_forward</span>
</a>
```

### 9.3 CTA Button — Secondary (Ghost)

```html
<a href="contact.html"
  class="inline-flex items-center justify-center gap-3 rounded-full 
    border-2 border-primary text-primary font-bold 
    hover:bg-primary hover:text-on-primary transition-all duration-300 
    text-lg md:text-xl h-14 md:h-18 px-8 md:px-12">
  [Button Label]
</a>
```

### 9.4 Interactive Service Card

```html
<div class="interactive-card rounded-3xl p-8 md:p-10 flex flex-col 
  items-start gap-4 md:gap-6 hover:-translate-y-3 animate-fade-up">
  <div class="p-3 md:p-4 rounded-xl bg-[COLOUR]/10 border 
    border-[COLOUR]/20 inline-block">
    <span class="material-symbols-outlined text-[COLOUR] 
      text-3xl md:text-4xl card-icon">[ICON]</span>
  </div>
  <div>
    <p class="text-on-surface text-xl md:text-2xl font-bold 
      mb-2 md:mb-3 tracking-tight">[Card Title]</p>
    <p class="text-on-surface-variant text-base md:text-lg 
      leading-relaxed">[Card Description]</p>
  </div>
  <a href="#" class="text-primary font-bold text-base md:text-lg 
    hover:text-secondary transition-colors mt-auto 
    flex items-center gap-2">
    Learn More
    <span class="material-symbols-outlined text-lg">arrow_forward</span>
  </a>
</div>
```

### 9.5 Stat Counter Card (Floating)

```html
<div class="interactive-card floating-card rounded-[2rem] p-8 md:p-10 
  flex flex-col items-center text-center animate-fade-up 
  min-h-[280px] md:min-h-[320px] justify-center">
  <div class="bg-number">[NUMBER]</div>
  <div class="relative z-10 flex flex-col items-center">
    <div class="w-16 h-16 md:w-20 md:h-20 rounded-2xl bg-[COLOUR]/20 
      flex items-center justify-center mb-6 md:mb-8 
      border border-[COLOUR]/30 backdrop-blur-sm">
      <span class="material-symbols-outlined text-[COLOUR] 
        text-3xl md:text-4xl card-icon">[ICON]</span>
    </div>
    <h3 class="text-2xl md:text-4xl text-on-surface mb-2 md:mb-3 
      font-bold stat-number" data-target="[NUMBER]">[NUMBER]+</h3>
    <p class="text-on-surface-variant text-sm md:text-lg uppercase 
      tracking-[0.2em] font-bold">[LABEL]</p>
  </div>
</div>
```

### 9.6 FAQ Accordion

```html
<div class="faq-item interactive-card rounded-2xl overflow-hidden 
  animate-fade-up mb-4">
  <button class="faq-trigger w-full flex items-center justify-between 
    p-6 md:p-8 text-left gap-4" 
    aria-expanded="false">
    <span class="text-on-surface text-lg md:text-xl font-bold">
      [Question]
    </span>
    <span class="material-symbols-outlined text-primary text-2xl 
      faq-icon transition-transform duration-300">expand_more</span>
  </button>
  <div class="faq-answer max-h-0 overflow-hidden 
    transition-[max-height] duration-500 ease-in-out">
    <p class="px-6 md:px-8 pb-6 md:pb-8 text-on-surface-variant 
      text-base md:text-lg leading-relaxed">
      [Answer text]
    </p>
  </div>
</div>
```

**FAQ JS:**
```javascript
document.querySelectorAll('.faq-trigger').forEach(trigger => {
  trigger.addEventListener('click', () => {
    const item    = trigger.parentElement;
    const answer  = item.querySelector('.faq-answer');
    const icon    = trigger.querySelector('.faq-icon');
    const isOpen  = trigger.getAttribute('aria-expanded') === 'true';

    // Close all others
    document.querySelectorAll('.faq-trigger').forEach(t => {
      t.setAttribute('aria-expanded', 'false');
      t.parentElement.querySelector('.faq-answer').style.maxHeight = '0';
      t.querySelector('.faq-icon').style.transform = 'rotate(0deg)';
    });

    if (!isOpen) {
      trigger.setAttribute('aria-expanded', 'true');
      answer.style.maxHeight = answer.scrollHeight + 'px';
      icon.style.transform = 'rotate(180deg)';
    }
  });
});
```

### 9.7 Full-Width CTA Banner

```html
<section class="relative py-20 md:py-32 overflow-hidden animate-fade-up">
  <div class="gradient-journey rounded-[2rem] md:rounded-[3rem] 
    mx-margin-mobile md:mx-margin-desktop p-10 md:p-20 
    text-center relative overflow-hidden">
    <!-- Decorative pattern overlay -->
    <div class="absolute inset-0 pattern-dots opacity-10"></div>
    <div class="relative z-10">
      <h2 class="text-3xl md:text-5xl lg:text-7xl font-black 
        text-white mb-6 md:mb-8 tracking-tight">
        [CTA Headline]
      </h2>
      <p class="text-white/80 text-lg md:text-2xl mb-8 md:mb-12 
        max-w-2xl mx-auto">
        [CTA sub-text]
      </p>
      <div class="flex flex-col sm:flex-row gap-4 justify-center">
        <a href="contact.html" 
          class="inline-flex items-center justify-center rounded-full 
            bg-white text-brand-blue font-bold 
            text-lg md:text-xl h-14 md:h-18 px-8 md:px-14 
            hover:-translate-y-1 transition-all shadow-xl">
          Book Free Consultation
        </a>
        <a href="tel:+8801713111133"
          class="inline-flex items-center justify-center rounded-full 
            border-2 border-white text-white font-bold 
            text-lg md:text-xl h-14 md:h-18 px-8 md:px-14 
            hover:bg-white/10 transition-all">
          <span class="material-symbols-outlined mr-2">call</span>
          Call Us Now
        </a>
      </div>
    </div>
  </div>
</section>
```

### 9.8 Skeleton Loading Card

Used while lazy-loaded content (blog articles, testimonials) is fetching.

```html
<div class="skeleton-card interactive-card rounded-3xl p-8 animate-pulse">
  <div class="skeleton h-6 w-24 rounded-full mb-4"></div>
  <div class="skeleton h-8 w-full rounded-lg mb-3"></div>
  <div class="skeleton h-8 w-3/4 rounded-lg mb-6"></div>
  <div class="skeleton h-4 w-full rounded mb-2"></div>
  <div class="skeleton h-4 w-5/6 rounded mb-8"></div>
  <div class="skeleton h-10 w-32 rounded-full"></div>
</div>

<style>
.skeleton {
  background: linear-gradient(90deg,
    rgba(255,255,255,0.04) 25%,
    rgba(255,255,255,0.08) 50%,
    rgba(255,255,255,0.04) 75%);
  background-size: 200% 100%;
  animation: shimmer 1.5s ease-in-out infinite;
}
@keyframes shimmer {
  0%   { background-position: -200% 0; }
  100% { background-position:  200% 0; }
}
</style>
```

---

## 10. Micro-interaction Specifications

### 10.1 Button States

| State | Visual Change | Duration |
|-------|--------------|----------|
| Default | Gradient background, shadow-xl | — |
| Hover | translateY(-4px), shadow-2xl deepens | 300ms |
| Active / Click | scale(0.97), shadow contracts | 150ms |
| Focus | `outline: 3px solid #abc7ff`, `outline-offset: 3px` | instant |
| Disabled | opacity: 0.4, cursor: not-allowed | instant |
| Loading | Spinner icon replaces label, disabled | — |

### 10.2 Form Input States

| State | Visual Change |
|-------|--------------|
| Default | `border border-outline-variant/20`, `bg-surface-container` |
| Focus | `border-primary`, `ring-2 ring-primary/20`, label floats up |
| Valid | `border-secondary` (`#43eda0`), green checkmark icon |
| Error | `border-error` (`#ffb4ab`), red `!` icon, error message below |
| Disabled | `opacity-40`, `cursor-not-allowed` |

Floating label animation: On focus or if input has value, `<label>` translates from inside the input to above it (`translateY(-1.5rem) scale(0.85)`).

### 10.3 Navigation States

| State | Behaviour |
|-------|----------|
| Default scroll position | `bg-surface/70 backdrop-blur-md` |
| Scrolled > 50px | `bg-surface/95 shadow-md` |
| Menu open | Body scroll locked, overlay opacity 1 |
| Active page link | `text-primary`, `aria-current="page"` |
| Hover on menu link | `text-primary`, subtle underline draw |

### 10.4 Card Interaction States

| State | Visual Change |
|-------|--------------|
| Default | Glass bg, white/8 border, shadow |
| Hover | translateY(-8px), scale(1.03), green border, green shadow, green gradient overlay fades in |
| Icon hover | scale(1.25), rotate(15deg) |
| Focus (keyboard) | Green outline ring |

### 10.5 FAQ Accordion

| State | Visual Change |
|-------|--------------|
| Closed | `max-height: 0`, chevron pointing down |
| Opening | `max-height: scrollHeight`, chevron rotates 180° (0.3s ease) |
| Open | Full height, green border on card |

### 10.6 WhatsApp FAB

| State | Visual Change |
|-------|--------------|
| Default | `#25D366` background, pulse ring animation |
| Hover | scale(1.1), shadow deepens, tooltip appears from left |
| Click | scale(0.95) then scale(1.1) |

### 10.7 Number Count-Up Animation

Triggered when stat card enters viewport (IntersectionObserver):
```javascript
function animateCounter(el, target, duration = 2000) {
  let start = 0;
  const increment = target / (duration / 16);
  const timer = setInterval(() => {
    start += increment;
    if (start >= target) {
      el.textContent = target + '+';
      clearInterval(timer);
    } else {
      el.textContent = Math.floor(start) + '+';
    }
  }, 16);
}
```

---

## 11. Form UX & Validation

### 11.1 Multi-Step Form Rules

- Step transitions: horizontal slide animation (current step slides left, new step slides in from right)
- Progress bar: CSS width transition, `gradient-journey` fill
- Step navigation: can go Back freely, cannot skip forward without validating current step
- On Back: previously entered data is preserved

### 11.2 Validation Rules

| Field | Rule | Error Message |
|-------|------|---------------|
| Full Name | Required, min 2 chars, no numbers | `"Please enter your full name"` |
| Email | Required, valid email format | `"Please enter a valid email address"` |
| Phone | Required, min 10 digits | `"Please enter a valid phone number"` |
| Service | Required (`select`) | `"Please select a service"` |
| Destination | Required (`select`) | `"Please select a destination"` |
| Timeline | Required (`select`) | `"Please select a timeline"` |
| Message | Optional, max 1000 chars | Character counter shown |

### 11.3 Form Submission

**Method:** Formspree (`https://formspree.io/f/[FORM_ID]`) via `fetch` API (no page reload).

```javascript
async function submitForm(data) {
  const response = await fetch('https://formspree.io/f/[FORM_ID]', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify(data)
  });
  return response.ok;
}
```

On success: Show success state (animated checkmark + thank you message) + fire GA4 `consultation_booked` event + fire Facebook Pixel `Lead` event.

On failure: Show error toast: `"Something went wrong. Please try WhatsApp or call us directly."` + show direct contact buttons.

---

## 12. Analytics & Tracking

### 12.1 Google Analytics 4 (GA4)

Add to `<head>` of every page:

```html
<!-- Google tag (gtag.js) — replace GA_MEASUREMENT_ID -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

### 12.2 Facebook Pixel

Add to `<head>` of every page:

```html
<!-- Facebook Pixel — replace PIXEL_ID -->
<script>
  !function(f,b,e,v,n,t,s){if(f.fbq)return;n=f.fbq=function(){...};
  fbq('init', 'PIXEL_ID');
  fbq('track', 'PageView');
</script>
```

### 12.3 Conversion Event Tracking

| Event | Trigger | GA4 Event | FB Pixel Event |
|-------|---------|-----------|---------------|
| CTA click | Any "Book Free Consultation" button | `begin_booking` | `InitiateCheckout` |
| Form start | Step 1 of form | `form_start` | `AddToCart` |
| Form complete | Successful submission | `consultation_booked` | `Lead` |
| WhatsApp click | WhatsApp FAB or button | `whatsapp_click` | `Contact` |
| Phone call | `tel:` link click | `phone_call` | `Contact` |
| Destination view | Country card click | `destination_viewed` + country param | `ViewContent` |
| Blog read | Article opened | `blog_read` + article title | `ViewContent` |
| Newsletter signup | Email subscribed | `newsletter_signup` | `Subscribe` |

### 12.4 Scroll Depth Tracking

Track scroll milestones (25%, 50%, 75%, 90%) on each page:

```javascript
const milestones = [25, 50, 75, 90];
const fired = new Set();
window.addEventListener('scroll', () => {
  const pct = Math.round((window.scrollY / (document.body.scrollHeight - window.innerHeight)) * 100);
  milestones.forEach(m => {
    if (pct >= m && !fired.has(m)) {
      fired.add(m);
      gtag('event', 'scroll_depth', { depth: m, page: document.title });
    }
  });
});
```

---

## 13. SEO Strategy

### 13.1 Target Keywords

| Keyword | Volume (BD) | Difficulty | Target Page |
|---------|------------|------------|-------------|
| visa consultancy Dhaka | High | Medium | index.html |
| study abroad consultancy Bangladesh | High | Medium | index.html |
| study in Australia from Bangladesh | High | Low | destinations.html |
| student visa Australia Bangladesh | High | Low | destinations.html |
| Canada immigration consultancy Dhaka | Medium | Medium | services.html |
| study in UK from Bangladesh | Medium | Low | destinations.html |
| IELTS visa consultancy Dhaka | Medium | Low | services.html |
| Emigration Aid Dhaka | Low (branded) | Very Low | index.html |
| abroad consultancy Shahjahanpur | Low (local) | Very Low | contact.html |
| scholarship Bangladesh 2025 | Medium | Low | blog.html |

### 13.2 On-Page SEO Per Page

| Page | Title Tag | Meta Description |
|------|-----------|-----------------|
| index.html | Emigration Aid — Top Visa & Education Consultancy in Dhaka | Expert guidance for studying abroad or migrating to Australia, Canada, UK & more. 15+ years, 500+ students. Book a free consultation in Dhaka. |
| services.html | Our Services — Student Recruitment & Immigration | Emigration Aid | From student recruitment to skilled immigration — full end-to-end support. Visa guidance, counseling, pre-departure & post-arrival services. |
| destinations.html | Study Destinations — Australia, Canada, UK & More | Emigration Aid | Explore 10+ top study destinations for Bangladeshi students. Get expert guidance on universities, visas, and scholarships for Australia, Canada, UK, USA & Europe. |
| about.html | About Us — 15+ Years of Trusted Education Consultancy | Emigration Aid | Founded in 2009, Emigration Aid has helped 500+ students achieve their academic dreams abroad. Meet our team and learn our story. |
| contact.html | Book Free Consultation — Contact Emigration Aid Dhaka | Ready to start your journey? Book a free consultation with Emigration Aid. Located in Shahjahanpur, Dhaka 1217. Call, WhatsApp, or fill our form. |
| blog.html | Blog & Resources — Visa Tips, Scholarships & Guides | Emigration Aid | Expert guides on student visas, scholarships, and immigration for Bangladeshi students. Stay informed with Emigration Aid's resource hub. |

### 13.3 Structured Data (JSON-LD)

Add to `index.html` `<head>`:

```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "Emigration Aid",
  "alternateName": "Jamal Associates & Emigration Aid",
  "description": "Expert visa and education consultancy in Dhaka, Bangladesh.",
  "url": "https://www.emigrationaid.com",
  "logo": "https://www.emigrationaid.com/assets/images/logo.png",
  "foundingDate": "2009-09-01",
  "founder": {
    "@type": "Person",
    "name": "Khan Abu Rawshan Md Mostofa Jamal"
  },
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "Suite A4, Toma Angelica, 280/1-281/1 North Shahjahanpur",
    "addressLocality": "Dhaka",
    "postalCode": "1217",
    "addressCountry": "BD"
  },
  "telephone": ["+8801713111133", "+8801715866866", "+8801321200700"],
  "email": "emigrationaid@gmail.com",
  "sameAs": ["https://www.facebook.com/emigrationaid"],
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Saturday","Sunday","Monday","Tuesday","Wednesday","Thursday"],
      "opens": "09:00",
      "closes": "18:00"
    }
  ]
}
```

### 13.4 Technical SEO Requirements

- `sitemap.xml` — List all 11 pages with `<lastmod>` and `<priority>`
- `robots.txt` — Allow all, point to sitemap
- Canonical URLs — `<link rel="canonical">` on every page
- Open Graph tags — All pages
- Twitter Card meta — All pages
- Image `alt` — All images
- `lang="en"` on `<html>`
- No broken internal links
- Gzip/Brotli compression enabled on server
- HTTPS enforced

---

## 14. Performance Budget

### 14.1 Targets

| Metric | Mobile Target | Desktop Target |
|--------|--------------|----------------|
| Lighthouse Performance | ≥ 90 | ≥ 95 |
| First Contentful Paint | < 2.0s | < 1.0s |
| Largest Contentful Paint | < 3.5s | < 2.0s |
| Total Blocking Time | < 200ms | < 100ms |
| Cumulative Layout Shift | < 0.1 | < 0.05 |
| Time to Interactive | < 4.5s | < 2.5s |
| Total Page Weight | < 1.5MB | < 2MB |

### 14.2 Optimisation Rules

**Images:**
- All images served as WebP format
- Responsive `srcset` and `sizes` attributes on all `<img>`
- Lazy loading: `loading="lazy"` on all below-fold images
- Maximum hero image: 400KB (WebP)
- Country flag images: SVG preferred, max 20KB each

**Fonts:**
- `font-display: swap` in @font-face
- Preconnect to `fonts.googleapis.com` and `fonts.gstatic.com`
- Load only weights used: 400, 500, 600, 700, 800, 900

**CSS/JS:**
- Tailwind loaded via CDN (acceptable for this project scale)
- No unused JavaScript libraries
- All event listeners added after DOMContentLoaded
- IntersectionObserver used for all scroll effects (no scroll event for animations)
- Animations use `transform` and `opacity` only (GPU-composited, no layout thrashing)

**Third-party:**
- Google Maps: loaded lazily on scroll into view (Intersection Observer on map container)
- Facebook embeds: use screenshot + link fallback if embed is slow

---

## 15. Accessibility Standards

**Target:** WCAG 2.1 Level AA compliance

### 15.1 Keyboard Navigation

- All interactive elements focusable via Tab key
- Logical tab order (matches visual order)
- Focus indicator: `outline: 3px solid #abc7ff; outline-offset: 3px` (never `outline: none`)
- Keyboard trap in fullscreen menu (Tab cycles through menu links only when menu is open)
- Escape key closes fullscreen menu

### 15.2 ARIA Implementation

| Element | ARIA |
|---------|------|
| `#mainNav` | `<nav aria-label="Main navigation">` |
| `#fullscreen-menu` | `role="dialog" aria-modal="true" aria-label="Site navigation"` |
| `#menuToggle` | `aria-label="Open menu" aria-expanded="false/true"` |
| `#menuClose` | `aria-label="Close menu"` |
| Active nav link | `aria-current="page"` |
| FAQ trigger | `aria-expanded="true/false"` |
| FAQ answer | `role="region"` |
| Form fields | `aria-required="true"`, `aria-describedby="[error-id]"` |
| WhatsApp FAB | `aria-label="Chat with us on WhatsApp"` |
| Back-to-top | `aria-label="Back to top"` |
| Skip link | `<a href="#main-content" class="sr-only focus:not-sr-only">Skip to main content</a>` |

### 15.3 Colour Contrast

| Element | Foreground | Background | Ratio | WCAG |
|---------|-----------|------------|-------|------|
| Body text | `#e2e2e8` | `#111317` | 14.4:1 | AAA ✓ |
| Secondary text | `#c1c6d5` | `#111317` | 9.8:1 | AAA ✓ |
| Primary blue on dark | `#abc7ff` | `#111317` | 8.1:1 | AAA ✓ |
| Button text on gradient | `#ffffff` | `#1F5FA6` | 7.2:1 | AAA ✓ |
| Label on card bg | `#c1c6d5` | `rgba(255,255,255,0.04)` | ≥ 4.5:1 | AA ✓ |

### 15.4 Reduced Motion

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
  .animate-fade-up { opacity: 1; transform: none; }
  .floating-card   { animation: none; }
  .word-flipper    { animation: none; }
}
```

---

## 16. Browser & Device Support

### 16.1 Browser Matrix

| Browser | Version | Support Level |
|---------|---------|---------------|
| Chrome (Android) | Latest 2 | Full ✓ |
| Chrome (Desktop) | Latest 2 | Full ✓ |
| Safari (iOS) | Latest 2 | Full ✓ |
| Firefox | Latest 2 | Full ✓ |
| Samsung Internet | Latest 2 | Full ✓ |
| Edge | Latest 2 | Full ✓ |
| Opera Mini | Latest | Degraded (no blur/animation) — functional ✓ |

**Graceful degradation for Opera Mini / low-end browsers:**
- `backdrop-filter` not supported → fallback `background: rgba(17,19,23,0.95)`
- CSS animations not supported → content still visible (opacity not hidden)
- CSS Grid not supported → flex fallback

### 16.2 Device Breakpoints

| Breakpoint | Width | Device Category |
|------------|-------|----------------|
| Default | 375px | Small mobile (iPhone SE) |
| `sm` | 640px | Large mobile |
| `md` | 768px | Tablet portrait |
| `lg` | 1024px | Tablet landscape / Small laptop |
| `xl` | 1280px | Desktop |
| `2xl` | 1536px | Wide desktop (capped at 1280px content) |

### 16.3 Network Considerations

The primary audience (Bangladeshi students, mobile) may be on 3G or 4G with variable connectivity. All performance optimisations in §14 must be treated as requirements, not suggestions.

---

## 17. File & Asset Structure

```
/emigration-aid-website/
│
├── index.html                 ← Homepage (adapted from code.html)
├── services.html              ← Services page
├── destinations.html          ← Destinations page
├── about.html                 ← About page
├── contact.html               ← Contact / Booking page
├── testimonials.html          ← Testimonials page
├── blog.html                  ← Blog & Resources
├── 404.html                   ← Not Found page (NEW)
├── privacy.html               ← Privacy Policy
├── terms.html                 ← Terms of Service
│
├── sitemap.xml                ← All 10 pages
├── robots.txt                 ← Allow all, point to sitemap
│
├── assets/
│   ├── images/
│   │   ├── logo.png               ← Uploaded circular badge logo
│   │   ├── logo-text.png          ← Text variant (for footer optional)
│   │   ├── og-image.jpg           ← Open Graph (1200×630px)
│   │   ├── favicon.ico
│   │   ├── apple-touch-icon.png   ← 180×180px
│   │   └── destinations/
│   │       ├── australia.webp     ← Country hero images (800×600px WebP)
│   │       ├── canada.webp
│   │       ├── uk.webp
│   │       ├── usa.webp
│   │       ├── poland.webp
│   │       ├── denmark.webp
│   │       ├── hungary.webp
│   │       └── france.webp
│   │
│   └── icons/
│       └── whatsapp.svg           ← WhatsApp brand icon (white)
│
└── README.md                  ← Developer setup & deployment notes
```

---

## 18. Shared Code Snippets

### 18.1 Universal `<head>` Block

```html
<head>
  <meta charset="utf-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>[Page Name] — Emigration Aid | Global Education & Immigration</title>
  <meta name="description" content="[Page-specific description, 150 chars]"/>
  <meta name="robots" content="index, follow"/>
  <link rel="canonical" href="[page URL]"/>

  <!-- Open Graph -->
  <meta property="og:type"        content="website"/>
  <meta property="og:title"       content="[Page Name] — Emigration Aid"/>
  <meta property="og:description" content="[Description]"/>
  <meta property="og:image"       content="assets/images/og-image.jpg"/>
  <meta property="og:url"         content="[page URL]"/>
  <meta property="og:site_name"   content="Emigration Aid"/>

  <!-- Twitter Card -->
  <meta name="twitter:card"        content="summary_large_image"/>
  <meta name="twitter:title"       content="[Page Name] — Emigration Aid"/>
  <meta name="twitter:description" content="[Description]"/>
  <meta name="twitter:image"       content="assets/images/og-image.jpg"/>

  <!-- Favicon -->
  <link rel="icon" href="assets/images/favicon.ico"/>
  <link rel="apple-touch-icon" href="assets/images/apple-touch-icon.png"/>

  <!-- Preconnect -->
  <link rel="preconnect" href="https://fonts.googleapis.com"/>
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>

  <!-- Google Sans -->
  <link href="https://fonts.googleapis.com/css2?family=Google+Sans:wght@400;500;600;700;800;900&display=swap" rel="stylesheet"/>

  <!-- Material Symbols -->
  <link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&display=swap" rel="stylesheet"/>

  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com?plugins=forms,container-queries"></script>
  <script id="tailwind-config">
    tailwind.config = {
      darkMode: "class",
      theme: {
        extend: {
          colors: {
            "primary":                    "#abc7ff",
            "surface-tint":               "#abc7ff",
            "secondary-container":        "#00d086",
            "on-secondary":               "#003921",
            "on-error-container":         "#ffdad6",
            "surface-variant":            "#333539",
            "outline-variant":            "#414753",
            "on-surface":                 "#e2e2e8",
            "surface-bright":             "#37393e",
            "surface-container-high":     "#282a2e",
            "primary-fixed-dim":          "#abc7ff",
            "on-primary":                 "#002f65",
            "on-primary-fixed-variant":   "#00458f",
            "surface-container-low":      "#1a1c20",
            "tertiary-fixed-dim":         "#ffb77b",
            "tertiary-container":         "#db7900",
            "surface-container-highest":  "#333539",
            "surface":                    "#111317",
            "on-tertiary-fixed-variant":  "#6d3900",
            "on-tertiary-container":      "#452200",
            "primary-fixed":              "#d7e3ff",
            "on-primary-fixed":           "#001b3f",
            "background":                 "#111317",
            "on-secondary-fixed-variant": "#005232",
            "on-tertiary":                "#4d2700",
            "on-secondary-fixed":         "#002111",
            "surface-container":          "#1e2024",
            "primary-container":          "#4791ff",
            "on-tertiary-fixed":          "#2e1500",
            "inverse-surface":            "#e2e2e8",
            "error-container":            "#93000a",
            "inverse-on-surface":         "#2f3035",
            "surface-container-lowest":   "#0c0e12",
            "secondary":                  "#43eda0",
            "tertiary":                   "#ffb77b",
            "surface-dim":                "#111317",
            "error":                      "#ffb4ab",
            "tertiary-fixed":             "#ffdcc2",
            "secondary-fixed":            "#59feb0",
            "outline":                    "#8b919f",
            "on-surface-variant":         "#c1c6d5",
            "secondary-fixed-dim":        "#31e196",
            "on-primary-container":       "#002a5c",
            "on-error":                   "#690005",
            "on-background":              "#e2e2e8",
            "inverse-primary":            "#005cbb",
            "on-secondary-container":     "#005232"
          },
          borderRadius: {
            "DEFAULT": "0.125rem", "lg": "0.25rem",
            "xl": "0.5rem",        "full": "0.75rem"
          },
          spacing: {
            "unit": "8px", "margin-desktop": "40px",
            "margin-mobile": "16px", "gutter": "24px",
            "container-max": "1280px"
          },
          fontFamily: {
            "label-md":           ["Google Sans"],
            "headline-lg-mobile": ["Google Sans"],
            "headline-xl":        ["Google Sans"],
            "headline-md":        ["Google Sans"],
            "body-sm":            ["Google Sans"],
            "body-md":            ["Google Sans"],
            "body-lg":            ["Google Sans"],
            "headline-lg":        ["Google Sans"],
            "sans":               ["Google Sans", "sans-serif"]
          },
          fontSize: {
            "label-md":           ["12px", { lineHeight:"16px", letterSpacing:"0.05em", fontWeight:"600" }],
            "headline-lg-mobile": ["28px", { lineHeight:"34px", fontWeight:"700" }],
            "headline-xl":        ["48px", { lineHeight:"56px", letterSpacing:"-0.02em", fontWeight:"700" }],
            "headline-md":        ["24px", { lineHeight:"32px", fontWeight:"600" }],
            "body-sm":            ["14px", { lineHeight:"20px", fontWeight:"400" }],
            "body-md":            ["16px", { lineHeight:"24px", fontWeight:"400" }],
            "body-lg":            ["18px", { lineHeight:"28px", fontWeight:"400" }],
            "headline-lg":        ["32px", { lineHeight:"40px", letterSpacing:"-0.01em", fontWeight:"700" }]
          }
        }
      }
    }
  </script>

  <!-- GA4 -->
  <script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
  <script>
    window.dataLayer=window.dataLayer||[];
    function gtag(){dataLayer.push(arguments);}
    gtag('js',new Date()); gtag('config','GA_MEASUREMENT_ID');
  </script>
</head>
```

### 18.2 Persistent UI Elements HTML

```html
<!-- Scroll Progress Bar -->
<div id="scroll-progress" class="fixed top-0 left-0 h-[3px] z-[51] w-0 gradient-journey transition-none"></div>

<!-- Spotlight Overlay -->
<div class="spotlight-overlay" style="--mouse-x:50%;--mouse-y:50%;"></div>

<!-- WhatsApp FAB -->
<a id="whatsapp-fab"
   href="https://wa.me/8801713111133?text=Hello%2C%20I%20would%20like%20to%20enquire%20about%20your%20services."
   target="_blank" rel="noopener noreferrer"
   aria-label="Chat with us on WhatsApp"
   class="fixed bottom-24 right-6 z-50 w-16 h-16 md:w-20 md:h-20 
          rounded-full flex items-center justify-center 
          shadow-[0_8px_32px_rgba(37,211,102,0.4)] 
          hover:scale-110 transition-transform duration-300"
   style="background-color:#25D366;">
  <svg width="32" height="32" viewBox="0 0 24 24" fill="white" xmlns="http://www.w3.org/2000/svg">
    <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"/>
  </svg>
  <!-- Pulse ring -->
  <span class="absolute inset-0 rounded-full animate-ping opacity-30" style="background-color:#25D366;"></span>
</a>

<!-- Back to Top -->
<button id="back-to-top"
        aria-label="Back to top"
        class="fixed bottom-44 right-6 z-50 w-12 h-12 rounded-full 
               bg-surface-container-high border border-outline-variant/20 
               flex items-center justify-center opacity-0 pointer-events-none 
               hover:bg-surface-container-highest hover:border-primary/30 
               transition-all duration-300"
        onclick="window.scrollTo({top:0,behavior:'smooth'})">
  <span class="material-symbols-outlined text-on-surface-variant text-xl">keyboard_arrow_up</span>
</button>

<!-- Mobile Sticky CTA (mobile only) -->
<div id="mobile-sticky-cta" 
     class="fixed bottom-0 left-0 w-full z-40 md:hidden 
            bg-surface-container-low/95 backdrop-blur-md 
            border-t border-outline-variant/20 
            flex opacity-0 pointer-events-none transition-opacity duration-300">
  <a href="tel:+8801713111133" 
     class="flex-1 flex items-center justify-center gap-2 h-16 
            text-on-surface font-bold text-base border-r border-outline-variant/20">
    <span class="material-symbols-outlined text-primary">call</span> Call Now
  </a>
  <a href="https://wa.me/8801713111133"
     target="_blank"
     class="flex-1 flex items-center justify-center gap-2 h-16 
            font-bold text-base" style="color:#25D366;">
    <span class="material-symbols-outlined">chat</span> WhatsApp
  </a>
</div>

<!-- Cookie Banner -->
<div id="cookie-banner"
     class="fixed bottom-0 left-0 w-full z-[55] 
            bg-surface-container/95 backdrop-blur-md 
            border-t border-outline-variant/20 
            px-margin-mobile md:px-margin-desktop py-4 
            flex flex-col sm:flex-row items-center justify-between gap-4">
  <p class="text-on-surface-variant text-sm md:text-base text-center sm:text-left">
    We use cookies to enhance your experience. 
    <a href="privacy.html" class="text-primary hover:underline">Learn more</a>
  </p>
  <button onclick="document.getElementById('cookie-banner').style.display='none';localStorage.setItem('cookieConsent','true');"
          class="flex-shrink-0 px-6 py-2 rounded-full gradient-journey text-on-primary font-bold text-sm">
    Accept
  </button>
</div>

<!-- Toast Container -->
<div id="toast-container" class="fixed top-6 right-6 z-[60] flex flex-col gap-3 pointer-events-none"></div>
```

### 18.3 Complete Shared JS Block

```html
<script>
  // ─── Skip cookie banner if already accepted ───────────────────────
  if (localStorage.getItem('cookieConsent')) {
    document.getElementById('cookie-banner').style.display = 'none';
  }

  // ─── Scroll progress bar ──────────────────────────────────────────
  const progressBar = document.getElementById('scroll-progress');
  window.addEventListener('scroll', () => {
    const st = document.documentElement.scrollTop;
    const sh = document.documentElement.scrollHeight - document.documentElement.clientHeight;
    progressBar.style.width = `${(st / sh) * 100}%`;
  }, { passive: true });

  // ─── Back-to-top visibility ───────────────────────────────────────
  const backToTop = document.getElementById('back-to-top');
  window.addEventListener('scroll', () => {
    if (window.scrollY > 300) {
      backToTop.classList.remove('opacity-0', 'pointer-events-none');
    } else {
      backToTop.classList.add('opacity-0', 'pointer-events-none');
    }
  }, { passive: true });

  // ─── Mobile sticky CTA visibility ────────────────────────────────
  const mobileCta = document.getElementById('mobile-sticky-cta');
  window.addEventListener('scroll', () => {
    const scrollPct = window.scrollY / (document.body.scrollHeight - window.innerHeight);
    if (scrollPct > 0.4) {
      mobileCta.classList.remove('opacity-0', 'pointer-events-none');
    } else {
      mobileCta.classList.add('opacity-0', 'pointer-events-none');
    }
  }, { passive: true });

  // ─── Spotlight effect ─────────────────────────────────────────────
  document.addEventListener('mousemove', (e) => {
    const spotlight = document.querySelector('.spotlight-overlay');
    if (spotlight) {
      spotlight.style.setProperty('--mouse-x', `${e.clientX}px`);
      spotlight.style.setProperty('--mouse-y', `${e.clientY}px`);
    }
  });

  // ─── Scroll fade-up animations ────────────────────────────────────
  const fadeObserver = new IntersectionObserver((entries, obs) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('is-visible');
        obs.unobserve(entry.target);
      }
    });
  }, { rootMargin: '0px', threshold: 0.1 });
  document.querySelectorAll('.animate-fade-up').forEach(el => fadeObserver.observe(el));

  // ─── Number count-up ──────────────────────────────────────────────
  function animateCounter(el, target, duration = 2000) {
    let start = 0;
    const increment = target / (duration / 16);
    const suffix = el.dataset.suffix || '+';
    const timer = setInterval(() => {
      start += increment;
      if (start >= target) {
        el.textContent = target + suffix;
        clearInterval(timer);
      } else {
        el.textContent = Math.floor(start) + suffix;
      }
    }, 16);
  }
  const counterObserver = new IntersectionObserver((entries, obs) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const target = parseInt(entry.target.dataset.target, 10);
        if (!isNaN(target)) animateCounter(entry.target, target);
        obs.unobserve(entry.target);
      }
    });
  }, { threshold: 0.5 });
  document.querySelectorAll('.stat-number[data-target]').forEach(el => counterObserver.observe(el));

  // ─── Nav scroll shadow ────────────────────────────────────────────
  window.addEventListener('scroll', () => {
    const nav = document.getElementById('mainNav');
    if (!nav) return;
    if (window.scrollY > 50) {
      nav.classList.add('shadow-md');
      nav.classList.replace('bg-surface/70', 'bg-surface/95');
    } else {
      nav.classList.remove('shadow-md');
      nav.classList.replace('bg-surface/95', 'bg-surface/70');
    }
  }, { passive: true });

  // ─── Fullscreen menu ──────────────────────────────────────────────
  const menuToggle      = document.getElementById('menuToggle');
  const menuClose       = document.getElementById('menuClose');
  const fullscreenMenu  = document.getElementById('fullscreen-menu');
  const menuLinks       = document.querySelectorAll('.menu-link');

  function toggleMenu() {
    const isOpen = fullscreenMenu.classList.toggle('active');
    document.body.style.overflow = isOpen ? 'hidden' : '';
    menuToggle.setAttribute('aria-expanded', String(isOpen));
  }
  menuToggle?.addEventListener('click', toggleMenu);
  menuClose?.addEventListener('click', toggleMenu);
  menuLinks.forEach(link => link.addEventListener('click', toggleMenu));

  // Escape key closes menu
  document.addEventListener('keydown', (e) => {
    if (e.key === 'Escape' && fullscreenMenu.classList.contains('active')) {
      toggleMenu();
    }
  });

  // ─── Active nav link ──────────────────────────────────────────────
  const currentPage = window.location.pathname.split('/').pop() || 'index.html';
  document.querySelectorAll('.menu-link[href]').forEach(link => {
    if (link.getAttribute('href') === currentPage) {
      link.classList.add('text-primary');
      link.setAttribute('aria-current', 'page');
    }
  });

  // ─── Toast helper ─────────────────────────────────────────────────
  function showToast(message, type = 'success') {
    const icons = { success: 'check_circle', error: 'error', info: 'info' };
    const colours = { 
      success: 'text-secondary', 
      error: 'text-error', 
      info: 'text-primary' 
    };
    const toast = document.createElement('div');
    toast.className = `glass-card rounded-2xl p-4 flex items-center gap-4 
      min-w-[280px] max-w-[380px] pointer-events-auto 
      translate-x-full opacity-0 transition-all duration-400`;
    toast.innerHTML = `
      <span class="material-symbols-outlined ${colours[type]} text-2xl flex-shrink-0">${icons[type]}</span>
      <p class="text-on-surface text-base font-medium flex-1">${message}</p>
    `;
    document.getElementById('toast-container').appendChild(toast);
    requestAnimationFrame(() => {
      toast.classList.remove('translate-x-full', 'opacity-0');
    });
    setTimeout(() => {
      toast.classList.add('translate-x-full', 'opacity-0');
      setTimeout(() => toast.remove(), 400);
    }, 4000);
  }

  // ─── Scroll depth tracking (GA4) ─────────────────────────────────
  if (typeof gtag !== 'undefined') {
    const milestones = [25, 50, 75, 90];
    const fired = new Set();
    window.addEventListener('scroll', () => {
      const pct = Math.round((window.scrollY / (document.body.scrollHeight - window.innerHeight)) * 100);
      milestones.forEach(m => {
        if (pct >= m && !fired.has(m)) {
          fired.add(m);
          gtag('event', 'scroll_depth', { depth: m });
        }
      });
    }, { passive: true });
  }

  // ─── Track CTA clicks ────────────────────────────────────────────
  document.querySelectorAll('a[href="contact.html"]').forEach(el => {
    el.addEventListener('click', () => {
      if (typeof gtag !== 'undefined') gtag('event', 'begin_booking');
    });
  });
  document.querySelectorAll('a[id="whatsapp-fab"], a[href*="wa.me"]').forEach(el => {
    el.addEventListener('click', () => {
      if (typeof gtag !== 'undefined') gtag('event', 'whatsapp_click');
    });
  });
</script>
```

---

## 19. Development Checklist

### 19.1 Universal Checks — Every Page

#### Setup
- [ ] `<html class="scroll-smooth dark" lang="en">` present
- [ ] Google Sans CDN link present in `<head>` (DM Sans removed)
- [ ] Material Symbols Outlined CDN link present
- [ ] Tailwind CDN script + config block present (identical to homepage)
- [ ] GA4 snippet present (replace `GA_MEASUREMENT_ID`)
- [ ] Facebook Pixel snippet present (replace `PIXEL_ID`)
- [ ] `<title>` follows naming convention
- [ ] `<meta name="description">` present and unique per page
- [ ] Open Graph tags complete
- [ ] `<link rel="canonical">` present
- [ ] Favicon link present

#### Layout & Structure
- [ ] `#scroll-progress` bar present
- [ ] `.spotlight-overlay` div present
- [ ] `#mainNav` nav bar present and scroll-behaviour working
- [ ] `#fullscreen-menu` overlay present with all 5 nav links
- [ ] Active page nav link highlighted
- [ ] `<main>` element wrapping all content sections
- [ ] `#whatsapp-fab` present with correct `wa.me` link
- [ ] `#back-to-top` button present
- [ ] `#mobile-sticky-cta` present (mobile only)
- [ ] `#cookie-banner` present
- [ ] `#toast-container` present
- [ ] Footer present with all 4 columns and correct links
- [ ] Copyright year: 2025

#### Functionality
- [ ] All nav links wire to correct `.html` files
- [ ] All footer links wire to correct pages
- [ ] All section CTAs link to `contact.html`
- [ ] Back-to-top button works
- [ ] Mobile sticky CTA appears at 40% scroll
- [ ] Cookie banner hides on accept + stores preference
- [ ] Escape key closes fullscreen menu
- [ ] Menu body-lock (no scroll behind open menu)

#### Responsive
- [ ] No horizontal scroll at 375px, 768px, 1280px
- [ ] All cards stack to 1-col on mobile
- [ ] Text sizes step down correctly (md: classes working)
- [ ] Hero text readable on 375px viewport

#### Animation
- [ ] All `.animate-fade-up` elements trigger on scroll
- [ ] `.interactive-card` hover states working
- [ ] Spotlight overlay follows mouse
- [ ] Back-to-top visibility triggered at 300px scroll
- [ ] Scroll progress bar width updates on scroll
- [ ] `prefers-reduced-motion` respected

#### Accessibility
- [ ] Skip-to-main-content link at top of body
- [ ] All images have descriptive `alt` attributes
- [ ] All interactive elements keyboard-reachable
- [ ] Focus indicators visible (no `outline: none`)
- [ ] ARIA labels on icon-only buttons
- [ ] `aria-expanded` on menu toggle
- [ ] Form fields have associated `<label>` elements

#### Performance
- [ ] All images are WebP
- [ ] All below-fold images have `loading="lazy"`
- [ ] No unused CSS or JS libraries imported
- [ ] Lighthouse mobile score ≥ 90 verified

### 19.2 Page-Specific Checks

- [ ] **index.html** — Word flipper running, flag animation running, 3 new sections (destination strip, services preview, testimonial strip) added, all links wired
- [ ] **services.html** — All 5 service cards present, sticky tabs working, process timeline animates, FAQ accordion working
- [ ] **destinations.html** — All 9 destination cards present, filter tabs working, stats counter counts up on scroll, scholarship spotlight present
- [ ] **about.html** — Founding date correct (Sep 1, 2009), timeline milestones correct, director info accurate, values grid complete
- [ ] **contact.html** — Multi-step form (3 steps) working, step validation enforced, success state shows, all contact details present, office hours correct, Google Maps embed lazy-loaded
- [ ] **testimonials.html** — Facebook post links present and correct, testimonial cards populated
- [ ] **blog.html** — Category filter works, article grid present, newsletter signup present
- [ ] **404.html** — Quick links back to main pages present, on-brand copy present
- [ ] **privacy.html / terms.html** — Last-updated date visible, legal text formatted, section anchors working

---

## 20. Content Inventory

### 20.1 Authoritative Data (from Company Profile — Use Verbatim)

| Field | Value |
|-------|-------|
| Company Name | Jamal Associates & Emigration Aid |
| Trading Name | Emigration Aid |
| Founded | September 1, 2009 |
| Director / CEO | Khan Abu Rawshan Md Mostofa Jamal |
| Title | Chief Executive |
| Team Size | 14 professionals |
| Phone 1 | +8801713111133 |
| Phone 2 | +8801715866866 |
| Phone 3 | +8801321200700 |
| Email 1 | emigrationaid@gmail.com |
| Email 2 | jamal@consultant.com |
| Address | Suite A4, Toma Angelica, 280/1-281/1 North Shahjahanpur, Dhaka 1217, Bangladesh |
| Facebook | https://facebook.com/emigrationaid |
| Tagline | "Bridging Your Path to Global Education" |
| Destinations | Australia, Canada, UK, USA, Poland, Denmark, Hungary, France, Other Europe |
| WhatsApp CTA | `wa.me/8801713111133` |
| Office Hours | Sat–Thu: 9:00 AM – 6:00 PM · Fri: Closed |

### 20.2 Stats (Verify with Client Before Publishing)

| Stat | Homepage Value | Source |
|------|--------------|--------|
| Years of experience | 15+ Years | Calculated from 2009 founding |
| Students placed | 500+ | Approximate — verify with client |
| Team members | 14 | Company profile |
| Study destinations | 10+ | 9 listed + "Other Europe" |

### 20.3 Content Gaps — Required from Client Before Launch

| Item | Needed For | Priority |
|------|-----------|----------|
| Student testimonial texts (with written permission) | testimonials.html | High |
| Office interior/team photographs | about.html, contact.html | High |
| Individual team member names & roles | about.html | Medium |
| Blog article full copy (6 articles) | blog.html | Medium |
| Privacy Policy legal text | privacy.html | High |
| Terms of Service legal text | terms.html | High |
| Formspree form endpoint ID | contact.html | High |
| GA4 Measurement ID | All pages | High |
| Facebook Pixel ID | All pages | Medium |
| Confirmed placement statistics | All stat cards | High |
| High-resolution country images (WebP) | destinations.html | Medium |
| Open Graph hero image (1200×630px) | All pages | Medium |
| Google Maps embed URL for office location | contact.html | Low |

---

## 21. Phase Rollout & Timeline

| Phase | Pages | Priority | Dev Days |
|-------|-------|----------|----------|
| **Phase 1 — Core** | `index.html` (adapted + new sections), `contact.html` (multi-step), `services.html` | Critical | 4 days |
| **Phase 2 — Trust** | `about.html`, `destinations.html`, `testimonials.html` | High | 3 days |
| **Phase 3 — Growth** | `blog.html`, `404.html` | Medium | 2 days |
| **Phase 4 — Legal** | `privacy.html`, `terms.html`, `sitemap.xml`, `robots.txt` | Medium | 1 day |
| **Phase 5 — QA & Launch** | All pages — responsive testing, Lighthouse audit, SEO audit, content population | Required | 2 days |

**Total Estimated Development: 12 working days (1 developer)**

### Milestones

| Milestone | Target Day |
|-----------|-----------|
| Phase 1 complete & client review | Day 4 |
| Phase 2 complete & client review | Day 7 |
| Phase 3+4 complete | Day 10 |
| Full QA pass | Day 11 |
| Client sign-off & launch | Day 12 |

---

## 22. Out of Scope (v1.0)

The following features are explicitly **excluded** from this PRD. They may form a **v2.0 PRD**:

| Feature | Notes |
|---------|-------|
| Backend / server-side | All dynamic functionality via third-party services only |
| CMS integration | Static HTML only in v1.0 |
| Email from contact form | Formspree endpoint (third-party) |
| User accounts / portals | Future v2 |
| Payment gateway | Future v2 |
| Live chat widget (Tawk.to etc.) | WhatsApp FAB covers this in v1 |
| Bangla / multilingual version | Future v2 |
| Admin dashboard | Future v2 |
| Job board / careers page | Future v2 |
| Online document submission portal | Future v2 |
| Student tracking portal | Future v2 |

---

## 23. Changelog

| Version | Date | Author | Summary |
|---------|------|--------|---------|
| 1.0 | May 26, 2026 | Senior FE Developer | Initial PRD — 9 pages, basic specs |
| 2.0 | May 26, 2026 | Senior FE Developer | Major enhancement: added user personas, conversion funnels, persistent UI (WhatsApp FAB, scroll progress, back-to-top, mobile sticky CTA, cookie banner, toast system), 3 new homepage sections, multi-step contact form, destination filter, count-up animations, FAQ accordion, skeleton loading, full component library (9 components), micro-interaction catalogue (18 entries), form validation spec, GA4+FB Pixel tracking with 10 events, SEO keyword strategy + JSON-LD schema, performance budget, WCAG 2.1 AA accessibility spec, browser support matrix, 404 page, enhanced shared JS block, full universal dev checklist |

---

## 24. Approval & Sign-off

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Client / Owner | Khan Abu Rawshan Md Mostofa Jamal | _________________ | ________ |
| Lead Frontend Developer | _________________________ | _________________ | ________ |
| Design & UX Review | _________________________ | _________________ | ________ |
| QA Review | _________________________ | _________________ | ________ |

---

*"Bridging Your Path to Global Education"*  
**Emigration Aid — Jamal Associates**  
Suite A4, Toma Angelica, 280/1-281/1 North Shahjahanpur, Dhaka 1217, Bangladesh  
📞 +8801713111133 · ✉️ emigrationaid@gmail.com · 🌐 facebook.com/emigrationaid
