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

- Asset Management
- Thinking
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
├── Asset Management
├── Thinking
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
- [ ] Asset Management page
- [ ] Thinking publication library
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
- [ ] Introduction to Asset Management
- [ ] Introduction to Thinking
- [ ] Introduction to Ventures
- [ ] Introduction to Team
- [ ] Final contact call to action

#### Asset Management

Write:

- [ ] Overview
- [ ] Investment philosophy
- [ ] Public-market approach
- [ ] Private-market approach
- [ ] Risk philosophy
- [ ] Decision-making principles
- [ ] Long-term orientation

> The page should describe investment activity without publicly mentioning the private fund.

#### Thinking

Prepare:

- [ ] Thinking introduction
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

## Phase 3 — Design System and Page Design

| | |
|---|---|
| **Estimated Duration** | Weeks 3–4 |
| **Goal** | Create one consistent visual system before building every page independently |

### Design Direction

The website should feel:

- Minimal
- Off-white
- Structured
- Modern
- Institutional
- Calm
- Serious without feeling old-fashioned

### Create the Core Design System

Define:

- [ ] Background colors
- [ ] Primary and secondary text colors
- [ ] Accent color
- [ ] Heading typography
- [ ] Body typography
- [ ] Spacing system
- [ ] Button styles
- [ ] Link styles
- [ ] Card styles
- [ ] Form styles
- [ ] Image treatment
- [ ] Publication layout
- [ ] Mobile navigation

### Design the Main Reusable Components

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

Design in this order:

1. Homepage
2. Article page
3. Thinking library
4. Asset Management
5. Ventures
6. Team
7. Contact
8. Mobile versions

### Phase 3 Deliverables

- [ ] Basic design system
- [ ] Desktop page designs
- [ ] Mobile page designs
- [ ] Reusable component list
- [ ] Final layout direction

---

## Phase 4 — Technical Foundation

| | |
|---|---|
| **Estimated Duration** | Week 4 |
| **Goal** | Set up the website so it remains simple now but can grow later |

### Recommended Structure

Use a modern content-based website architecture with:

- Reusable page components
- Structured content collections
- Separate English and Vietnamese content
- A content management system
- Clear separation between design, content, and data

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

- Structured content instead of hardcoded pages
- Reusable components
- Language-specific content fields
- Easy addition of new publications
- Easy addition of ventures and team members
- Private fields that are not shown publicly
- Clear public and private content separation

### Phase 4 Deliverables

- [ ] Website project created
- [ ] Page routing established
- [ ] English and Vietnamese structure established
- [ ] Content types created
- [ ] Reusable components prepared
- [ ] Content management system connected

---

## Phase 5 — English MVP Build

| | |
|---|---|
| **Estimated Duration** | Weeks 5–6 |
| **Goal** | Build and complete the English version first |

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

#### 3. Asset Management

- [ ] Overview
- [ ] Philosophy
- [ ] Investment approach
- [ ] Public markets
- [ ] Private markets
- [ ] Risk and decision principles

#### 4. Thinking

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
- [ ] Add Vietnamese Asset Management copy
- [ ] Add Vietnamese Thinking introduction
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

## Phase 8 — Controlled Launch

| | |
|---|---|
| **Estimated Duration** | Week 9 |
| **Goal** | Launch quietly, verify real-world behavior, and correct problems before promoting the website widely |

### Soft Launch

Share the website with a small group of:

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

- [ ] Live website
- [ ] First external feedback
- [ ] Corrected launch issues
- [ ] Final public version

---

## Phase 9 — Public Rollout

| | |
|---|---|
| **Estimated Duration** | Week 10 |
| **Goal** | Begin using the website as TNT Capital's official institutional platform |

### Public Rollout Actions

- [ ] Announce the website through LinkedIn
- [ ] Share the two existing research pieces
- [ ] Publish the Vietnam 2045 page
- [ ] Introduce the TNT Capital Doctrine
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

> Build the website as a **content platform with institutional pages**, not as a collection of manually coded static pages.

The backend can remain lightweight. The important foundation is:

| Principle | Description |
|-----------|-------------|
| **Structured content** | Content stored in defined types, not hardcoded HTML |
| **Reusable components** | Consistent UI elements across all pages |
| **Bilingual support** | English and Vietnamese content from the start |
| **Public/private separation** | Clear control over what is visible publicly |
| **Easy publication management** | Add articles without a developer |
| **Easy expansion** | Add portfolio, ventures, and team without rebuilding |

This gives TNT Capital a simple first website without forcing a complete rebuild as the institution grows.

---

## Phase Summary

| Phase | Focus | Duration |
|-------|-------|----------|
| **1** | Foundation and Scope | Week 1 |
| **2** | Content Development | Weeks 2–3 |
| **3** | Design System and Page Design | Weeks 3–4 |
| **4** | Technical Foundation | Week 4 |
| **5** | English MVP Build | Weeks 5–6 |
| **6** | Vietnamese Version | Week 7 |
| **7** | Testing and Refinement | Week 8 |
| **8** | Controlled Launch | Week 9 |
| **9** | Public Rollout | Week 10 |

---

*Document version: MVP*  
*Last updated: June 2026*  
*TNT Capital — Internal Use*
