# TNT Capital Website — Rollout Plan

---

## Table of Contents

1. [Rollout Objective](#rollout-objective)
2. [Recommended Timeline](#recommended-timeline)
3. [Phase 1 — Foundation and Scope](#phase-1--foundation-and-scope)
4. [Phase 2 — Content Development](#phase-2--content-development)
5. [Phase 3 — Design System and Page Design](#phase-3--design-system-and-page-design)
6. [Phase 4 — Technical Foundation](#phase-4--technical-foundation)
7. [Phase 5 — English MVP Build](#phase-5--english-mvp-build)
8. [Phase 6 — Vietnamese Version](#phase-6--vietnamese-version)
9. [Phase 7 — Testing and Refinement](#phase-7--testing-and-refinement)
10. [Phase 8 — Controlled Launch](#phase-8--controlled-launch)
11. [Phase 9 — Public Rollout](#phase-9--public-rollout)
12. [Recommended Build Principle](#recommended-build-principle)

---

## Rollout Objective

Launch a credible bilingual institutional website for TNT Capital that clearly presents:

- Investment Management
- Insights
- Ventures
- Team
- Contact

The first version should be **simple, polished, and easy to maintain**.

The website does not need a complex backend at launch. However, the structure should support future expansion, including:

- More research and articles
- More investments and ventures
- Additional team members
- Portfolio filtering
- Private investor access
- More advanced data and reporting

---

## Recommended Timeline

| Total Estimated Window | 8–10 weeks |
|------------------------|------------|

This assumes:

- You are building the website yourself
- You are still learning during the process
- Most website copy has not yet been written
- Only two research pieces currently exist
- The first version should be professionally structured, not rushed

> The timeline is flexible. **Quality and clarity matter more than launching by a fixed date.**

---

## Build Path (locked)

| Stage | Tool | Role |
|-------|------|------|
| Visual design + page build | **Framer** | Design and assemble the site visually |
| AI-assisted editing | **Cursor ↔ Framer** | Cursor connects to the Framer project to edit layouts, styles, CMS, and components |
| Final production host | **WordPress** (existing TNT server) | Publish / hand off the finished site onto WordPress |

How to think about the phases:

1. **Phases 1–2** — Scope and content (docs + copy), independent of tools  
2. **Phases 3–7** — Design and build in **Framer**, with Cursor connected to Framer when editing  
3. **Phases 8–9** — Controlled check, then **publish onto the WordPress server** TNT already has  

> Framer is the design/build environment. WordPress is the final destination. Do not treat Next.js/Vercel as the production path for this rollout unless TNT deliberately revises this plan later.

Cursor + Framer connection (when ready): use the Framer agent setup (`npx @framer/agent@latest setup`), open a session on the TNT Framer project, then edit from Cursor. Exact connect steps can be walked through the first time you start Phase 3.

---

## Phase 1 — Foundation and Scope

| | |
|---|---|
| **Estimated Duration** | Week 1 |
| **Goal** | Define exactly what the first version includes before designing or building |

### Tasks

#### Confirm the MVP Website Structure

```
TNT Capital
├── Home
├── Investment Management
├── Insights
├── Ventures
├── Team
└── Contact
```

#### Confirm the English and Vietnamese Structure

```
/en/
/vi/
```

Both versions should use the same page structure. Content does not need to be published in both languages at the exact same time, but the system should be prepared for both from the beginning.

#### Define the MVP Content

The first launch should include:

- [ ] Homepage
- [ ] Investment Management page
- [ ] Insights publication library
- [ ] Two existing research pieces
- [ ] Ventures overview
- [ ] Team page
- [ ] Contact page
- [ ] Vietnam 2045
- [ ] TNT Capital Doctrine

#### Define What Is Excluded

Do not build:

- Investor accounts
- Private reporting
- Public fund performance
- Public fund details
- User registration
- Advanced dashboards
- AI features
- Automated investment evaluation
- Complex workflow systems

### Phase 1 Deliverables

- [ ] Confirmed sitemap
- [ ] Confirmed MVP feature list
- [ ] Confirmed English and Vietnamese structure
- [ ] List of required website copy
- [ ] List of available research and visual assets

---

## Phase 2 — Content Development

| | |
|---|---|
| **Estimated Duration** | Weeks 2–3 |
| **Goal** | Write the content before trying to finish the visual design |

> The website should not be designed around placeholder text because the amount and type of content will affect the layout.

### Content to Prepare

#### Homepage

Write:

- [ ] Main institutional statement
- [ ] Short description of TNT Capital
- [ ] Global perspective
- [ ] Vietnam conviction
- [ ] Introduction to Investment Management
- [ ] Introduction to Insights
- [ ] Introduction to Ventures
- [ ] Introduction to Team
- [ ] Final contact call to action

#### Investment Management

Write:

- [ ] Overview
- [ ] Investment philosophy
- [ ] Public-market approach
- [ ] Private-market approach
- [ ] Risk philosophy
- [ ] Decision-making principles
- [ ] Long-term orientation

> The page should describe investment activity without publicly mentioning the private fund.

#### Insights

Prepare:

- [ ] Insights introduction
- [ ] Category descriptions
- [ ] Two existing research pieces
- [ ] Vietnam 2045
- [ ] TNT Capital Doctrine
- [ ] Author information
- [ ] Publication dates
- [ ] Article summaries

#### Ventures

Write:

- [ ] Venture-building overview
- [ ] How TNT approaches venture creation
- [ ] Current active ventures that can be shown publicly
- [ ] What TNT provides beyond capital
- [ ] How founders and operators can contact TNT

#### Team

Write:

- [ ] Who TNT Capital is
- [ ] Founder profile
- [ ] Current team members *(if applicable)*
- [ ] Advisors *(if applicable)*
- [ ] Values and working principles

> Do not create empty team categories.

#### Contact

Prepare inquiry categories:

- [ ] Strategic partnership
- [ ] Investment opportunity
- [ ] Founder or company introduction
- [ ] Research inquiry
- [ ] Media inquiry
- [ ] General inquiry

#### Vietnamese Version

- [ ] Vietnamese copy should be adapted naturally
- [ ] Do not directly translate every English sentence word for word

### Phase 2 Deliverables

- [ ] Complete English website copy
- [ ] First Vietnamese copy draft
- [ ] Research articles formatted for the website
- [ ] Publication summaries
- [ ] Team information
- [ ] Venture and portfolio descriptions

---

## Phase 3 — Design System and Page Design (Framer)

| | |
|---|---|
| **Estimated Duration** | Weeks 3–4 |
| **Goal** | Apply [`design.md`](./design.md) in Framer before finishing every page |

### Design Direction

Follow [`design.md`](./design.md). The site should feel intentional, institutional, editorial, and recognizably TNT (Dark Green `#275317` hierarchy — not a generic off-white corporate look).

### Tooling for this phase

- [ ] Framer project created / confirmed for TNT Capital
- [ ] Cursor connected to the Framer project (Framer agent session)
- [ ] Color and text styles in Framer set from `design.md`
- [ ] Shared components started on the Framer canvas

### Create the Core Design System in Framer

Define as Framer color + text styles (sourced from `design.md`):

- [x] Background / section surfaces (White, TNT Mist, Soft Gray, Dark Green)
- [x] Primary and secondary text colors
- [x] Brand greens (Primary `#275317`, Secondary `#4D6345`, Mist `#F5FFF9`)
- [x] Heading typography (Source Serif 4 H1–H3)
- [x] Body typography (Source Sans 3, 18 / 17 px)
- [x] Button and link styles (per design.md)
- [ ] Spacing system applied consistently on canvas
- [ ] Form styles
- [ ] Image treatment (restrained; not fully defined in design.md)
- [ ] Publication layout
- [ ] Mobile navigation

### Design the Main Reusable Components (in Framer)

Create:

- [ ] Header
- [ ] Footer
- [ ] Hero section
- [ ] Section introduction
- [ ] Core-area cards
- [ ] Article cards
- [ ] Portfolio or venture cards
- [ ] Team member cards
- [ ] Contact form
- [ ] Language selector
- [ ] Related-publication section

### Design Priority

Design in this order in Framer:

1. Homepage
2. Article page
3. Insights library
4. Investment Management
5. Venture
6. About / Team
7. Contact
8. Mobile breakpoints

### Phase 3 Deliverables

- [x] Basic design system (`design.md` v1.0)
- [ ] Framer styles matching design.md
- [ ] Desktop page frames in Framer
- [ ] Mobile breakpoints in Framer
- [ ] Reusable component set on canvas
- [ ] Cursor ↔ Framer workflow confirmed

---

## Phase 4 — Technical Foundation (Framer project)

| | |
|---|---|
| **Estimated Duration** | Week 4 |
| **Goal** | Set up Framer (and Cursor connection) so design and content stay structured before WordPress publish |

### Recommended Structure

Build and iterate in **Framer**:

- Reusable Framer components and shared styles from `design.md`
- Structured CMS collections where needed (publications, ventures, team)
- Separate English and Vietnamese content paths
- Clear separation between visual design (Framer) and final host (WordPress)

Cursor assists by connecting to the Framer project — not by replacing Framer as the canvas.

### Core Content Types

#### Publications

| Field | Description |
|-------|-------------|
| Title | Article title |
| Summary | Short description |
| Author | Author name and profile |
| Publication date | Date of publication |
| Category | Research / Memo / Essay / etc. |
| Language | English / Vietnamese |
| Main content | Full article body |
| Featured image | Cover or header image |
| Downloadable document | Optional PDF attachment |
| Related publications | Linked articles |
| Featured status | Homepage or category highlight |
| URL slug | Clean URL identifier |

#### Ventures

| Field | Description |
|-------|-------------|
| Venture name | Full name of the venture |
| Short description | One-line summary |
| Full description | Detailed description |
| Status | Active / In development / etc. |
| Website | External URL |
| Logo | Venture logo image |
| Images | Supporting visuals |
| TNT's relationship | Role TNT plays |
| Public visibility | Shown or hidden publicly |

#### Portfolio Entries

| Field | Description |
|-------|-------------|
| Company name | Full company name |
| Category | Sector or industry |
| Market type | Public / Private |
| Description | Investment description |
| Website | External URL |
| Logo | Company logo |
| Public visibility | Shown or hidden publicly |

#### Team Members

| Field | Description |
|-------|-------------|
| Name | Full name |
| Role | Title or position |
| Biography | Professional background |
| Image | Profile photo |
| LinkedIn / professional link | External profile |
| Display order | Position in listing |
| Public visibility | Shown or hidden publicly |

### Scaling Principles

The first version should avoid unnecessary backend complexity, but it should be built around:

- Structured content instead of one-off page hacks
- Reusable Framer components
- Language-specific content fields
- Easy addition of new publications
- Easy addition of ventures and team members
- Private fields that are not shown publicly
- A clear **Framer → WordPress** publish path at the end

### Phase 4 Deliverables

- [ ] Framer project ready for TNT Capital
- [ ] Cursor ↔ Framer session working
- [ ] Routes / pages established in Framer
- [ ] English and Vietnamese structure established
- [ ] CMS collections created (as needed)
- [ ] Reusable components prepared
- [ ] WordPress server access confirmed for later publish (credentials/host only — no build yet)

---

## Phase 5 — English MVP Build (in Framer)

| | |
|---|---|
| **Estimated Duration** | Weeks 5–6 |
| **Goal** | Complete the English site in Framer first (Cursor assists; WordPress comes later) |

### Build Order

#### 1. Global Structure

- [ ] Header
- [ ] Navigation
- [ ] Footer
- [ ] Mobile navigation
- [ ] Language selector
- [ ] Page layout system

#### 2. Homepage

- [ ] Hero
- [ ] Core areas
- [ ] Featured publications
- [ ] Selected ventures or portfolio
- [ ] Vietnam 2045
- [ ] Team introduction
- [ ] Contact call to action

#### 3. Investment Management

- [ ] Overview
- [ ] Philosophy
- [ ] Investment approach
- [ ] Public markets
- [ ] Private markets
- [ ] Risk and decision principles

#### 4. Insights

- [ ] Publication library
- [ ] Category filters
- [ ] Article pages
- [ ] Related publications
- [ ] Vietnam 2045
- [ ] TNT Capital Doctrine
- [ ] Existing research pieces

#### 5. Ventures

- [ ] Overview
- [ ] Active ventures
- [ ] Portfolio companies
- [ ] Venture-building approach
- [ ] Contact path

#### 6. Team

- [ ] Who We Are
- [ ] Founder
- [ ] Current team
- [ ] Advisors
- [ ] Values

#### 7. Contact

- [ ] Inquiry type selector
- [ ] Name field
- [ ] Email field
- [ ] Organization field
- [ ] Website field
- [ ] Message field
- [ ] Submission confirmation

### Phase 5 Deliverables

- [ ] Complete English website
- [ ] Responsive desktop and mobile experience
- [ ] Working content system
- [ ] Working contact form
- [ ] Two published research pieces
- [ ] Public ventures and portfolio entries added

---

## Phase 6 — Vietnamese Version

| | |
|---|---|
| **Estimated Duration** | Week 7 |
| **Goal** | Create a complete Vietnamese version using the same website structure |

### Tasks

- [ ] Add Vietnamese navigation
- [ ] Add Vietnamese homepage copy
- [ ] Add Vietnamese Investment Management copy
- [ ] Add Vietnamese Insights introduction
- [ ] Add Vietnamese Ventures copy
- [ ] Add Vietnamese Team copy
- [ ] Add Vietnamese Contact copy
- [ ] Add Vietnamese versions of available publications
- [ ] Test language switching
- [ ] Test Vietnamese typography

### Language Rules

- Each language should have its own page URL
- Visitors should remain on the same equivalent page when switching languages
- Missing translations should be clearly indicated
- Vietnamese copy should be reviewed for natural tone and institutional credibility

### Phase 6 Deliverables

- [ ] Complete Vietnamese site structure
- [ ] Vietnamese core pages
- [ ] Working bilingual navigation
- [ ] Correct Vietnamese typography
- [ ] English and Vietnamese metadata

---

## Phase 7 — Testing and Refinement

| | |
|---|---|
| **Estimated Duration** | Week 8 |
| **Goal** | Remove inconsistencies, errors, and unfinished experiences before launch |

### Functional Testing

Test:

- [ ] Navigation
- [ ] Language switching
- [ ] Contact form
- [ ] Article links
- [ ] Related publications
- [ ] Portfolio links
- [ ] External links
- [ ] Document downloads
- [ ] Mobile menu
- [ ] Form confirmations

### Content Testing

Review:

- [ ] Grammar
- [ ] Repeated wording
- [ ] Institutional tone
- [ ] English and Vietnamese consistency
- [ ] Publication dates
- [ ] Author names
- [ ] Venture descriptions
- [ ] Team information
- [ ] Legal or misleading claims

### Device Testing

Test on:

- [ ] Desktop
- [ ] Laptop
- [ ] Tablet
- [ ] iPhone
- [ ] Android phone
- [ ] Multiple browsers

### Performance Testing

Review:

- [ ] Image sizes
- [ ] Loading speed
- [ ] Mobile performance
- [ ] Font loading
- [ ] Long article performance
- [ ] Broken links

### Phase 7 Deliverables

- [ ] Tested website
- [ ] Corrected copy
- [ ] Improved mobile experience
- [ ] Fixed links and forms
- [ ] Launch-ready English and Vietnamese versions

---

## Phase 8 — Controlled Launch (WordPress)

| | |
|---|---|
| **Estimated Duration** | Week 9 |
| **Goal** | Move the approved Framer build onto the TNT WordPress server, launch quietly, and fix real-world issues before wide promotion |

### Publish path

- [ ] Freeze Framer design for launch candidate
- [ ] Export / hand off approved pages and assets from Framer
- [ ] Implement or import onto the **existing WordPress server**
- [ ] Match `design.md` globals on WordPress (fonts, colors, surfaces)
- [ ] Point staging URL at WordPress for soft-launch review
- [ ] Only then promote the public domain

### Soft Launch

Share the WordPress staging or soft-live site with a small group of:

- Trusted strategic partners
- Advisors
- Investors
- Founders
- Researchers
- Close professional contacts

Ask them to review:

- [ ] Whether TNT's activity is clear
- [ ] Whether the institution feels credible
- [ ] Whether the navigation makes sense
- [ ] Whether any wording feels exaggerated
- [ ] Whether the contact process works
- [ ] Whether the bilingual experience feels natural
- [ ] Whether Framer → WordPress visual fidelity holds

### Review Real Usage

Monitor:

- [ ] Most visited pages
- [ ] Research article views
- [ ] Language usage
- [ ] Contact submissions
- [ ] Mobile usage
- [ ] Pages where visitors leave
- [ ] Broken links or errors

### Phase 8 Deliverables

- [ ] Site live on TNT WordPress server (soft launch)
- [ ] First external feedback
- [ ] Corrected launch issues
- [ ] Final public WordPress version ready

---

## Phase 9 — Public Rollout (WordPress production)

| | |
|---|---|
| **Estimated Duration** | Week 10 |
| **Goal** | Use the WordPress site as TNT Capital's official institutional platform |

### Public Rollout Actions

- [ ] Confirm production domain on WordPress
- [ ] Announce the website through LinkedIn
- [ ] Share the two existing research pieces
- [ ] Publish the Vietnam 2045 page
- [ ] Introduce the Manifesto / institutional doctrine
- [ ] Update professional profiles with the website
- [ ] Add the website to email signatures
- [ ] Share relevant pages directly with strategic partners
- [ ] Use the website in founder and investment conversations

> The rollout should emphasize **substance** rather than simply announcing that a website exists.

**Examples of meaningful launch content:**

- Why TNT Capital exists
- How TNT approaches long-term investing
- TNT's conviction in Vietnam
- A featured research publication
- An active venture or investment perspective

### Post-Launch Development

#### First 30 Days

Focus on:

- Fixing usability issues
- Improving unclear copy
- Reviewing contact inquiries
- Monitoring language usage
- Publishing one additional article
- Improving the most visited pages

#### First 90 Days

Consider adding:

- Better publication search
- Topic tags
- Downloadable research reports
- More portfolio entries
- Venture case studies
- Email subscription
- Basic analytics dashboard
- Improved contact management

#### Later Versions

Only build these when there is a **real operational need**:

- Investor portal
- Private documents
- Secure reporting
- Detailed portfolio dashboards
- Interactive research data
- Partnership application workflows
- Advanced publication recommendations

---

## Recommended Build Principle

> Design and build in **Framer** (with Cursor connected). Publish the finished site onto **WordPress**.

| Principle | Description |
|-----------|-------------|
| **Framer first** | Visual system and pages are designed and assembled in Framer |
| **Cursor assists Framer** | Cursor edits the connected Framer project; it is not a separate production host |
| **WordPress last** | Final production lives on TNT’s existing WordPress server |
| **design.md locked** | Colors, type, surfaces, and UI rules come from `design.md` |
| **Structured content** | Prefer CMS collections over one-off page hacks |
| **Bilingual support** | English and Vietnamese from the start |
| **Public/private separation** | Clear control over what is visible publicly |

This keeps design fast while landing on the hosting TNT already owns.

---

## Phase Summary

| Phase | Focus | Duration |
|-------|-------|----------|
| **1** | Foundation and Scope | Week 1 |
| **2** | Content Development | Weeks 2–3 |
| **3** | Design System and Page Design **(Framer)** | Weeks 3–4 |
| **4** | Technical Foundation **(Framer + Cursor)** | Week 4 |
| **5** | English MVP Build **(Framer)** | Weeks 5–6 |
| **6** | Vietnamese Version **(Framer)** | Week 7 |
| **7** | Testing and Refinement **(Framer)** | Week 8 |
| **8** | Controlled Launch **(→ WordPress)** | Week 9 |
| **9** | Public Rollout **(WordPress production)** | Week 10 |

---

*Document version: MVP*  
*Last updated: September 2026*  
*Build path: Framer (+ Cursor) → WordPress*  
*Design source of truth: [`design.md`](./design.md)*  
*TNT Capital — Internal Use*
