# System Design — TNT Capital Website

**Version:** 1.0  
**Status:** Provisional — subject to change as the build develops

---

## Table of Contents

1. [Project Summary](#1-project-summary)
2. [System Architecture](#2-system-architecture)
   - [2.1 MVP Architecture](#21-mvp-architecture)
   - [2.2 What Each Tool Does](#22-what-each-tool-does)
   - [2.3 Future Architecture Evolution](#23-future-architecture-evolution)
3. [Website Structure and Routing](#3-website-structure-and-routing)
   - [3.1 Main Routes](#31-main-routes)
   - [3.2 Language Behavior](#32-language-behavior)
   - [3.3 Main Navigation](#33-main-navigation)
4. [Content System](#4-content-system)
   - [4.1 Sanity Content Models](#41-sanity-content-models)
   - [4.2 Page Model](#42-page-model)
   - [4.3 Publication Model](#43-publication-model)
   - [4.4 Venture Model](#44-venture-model)
   - [4.5 Portfolio Model](#45-portfolio-model)
   - [4.6 Team Member Model](#46-team-member-model)
   - [4.7 Author Model](#47-author-model)
5. [Database Design](#5-database-design)
   - [5.1 Supabase Purpose](#51-supabase-purpose)
   - [5.2 Contact Submissions Table](#52-contact-submissions-table)
   - [5.3 Visibility Records Table](#53-visibility-records-table)
   - [5.4 Future Database Tables](#54-future-database-tables)
6. [Core System Flows](#6-core-system-flows)
7. [API and Integration Design](#7-api-and-integration-design)
8. [Admin System](#8-admin-system)
9. [Hosting and Infrastructure](#9-hosting-and-infrastructure)
10. [Security and Privacy](#10-security-and-privacy)
11. [Performance and Search Visibility](#11-performance-and-search-visibility)
12. [Scaling Strategy](#12-scaling-strategy)
13. [Risks and Mitigation](#13-risks-and-mitigation)
14. [Business and System Rules](#14-business-and-system-rules)
15. [MVP Technical Boundary](#15-mvp-technical-boundary)
16. [Final Architecture Principle](#16-final-architecture-principle)

---

## 1. Project Summary

The TNT Capital website is a bilingual institutional website designed to present TNT Capital's investment activity, research, ventures, team, and public portfolio.

The website has five primary functions:

1. Present TNT Capital as a credible long-term investment institution
2. Explain TNT's investment philosophy and activity
3. Publish research and articles
4. Present selected ventures and portfolio companies
5. Allow strategic partners, investors, founders, researchers, and other visitors to contact TNT

The website will launch as a relatively lightweight public platform. It will **not** initially include:

- User accounts
- Investor accounts
- Public fund reporting
- Live financial dashboards
- Complex private portals
- AI features
- Large-scale backend systems

> However, the technical foundation should make it possible to add these capabilities later without rebuilding the entire website.

---

## 2. System Architecture

### 2.1 MVP Architecture

The first version will use a content-focused architecture.

```
┌─────────────────────────────────────────────────────────────┐
│                        VISITOR                              │
│                                                             │
│        Desktop / Mobile / Tablet Web Browser                │
└─────────────────────────────┬───────────────────────────────┘
                              │ HTTPS
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                     FRONTEND LAYER                          │
│                                                             │
│  Next.js Website                                            │
│  TypeScript                                                 │
│  Tailwind CSS                                               │
│                                                             │
│  Responsibilities:                                          │
│  - Display pages                                            │
│  - Display articles                                         │
│  - Display ventures and portfolio entries                   │
│  - Handle English and Vietnamese routing                    │
│  - Display contact forms                                    │
└───────────────┬─────────────────────────────┬───────────────┘
                │                             │
                │ Content requests            │ Form submissions
                ▼                             ▼
┌───────────────────────────────┐   ┌─────────────────────────┐
│        SANITY CMS             │   │       SUPABASE          │
│                               │   │                         │
│ Public website content        │   │ Contact submissions     │
│ - Pages                       │   │ Private records         │
│ - Research                    │   │ Visibility settings     │
│ - Articles                    │   │ Future private features │
│ - Ventures                    │   │                         │
│ - Team                        │   │ PostgreSQL database     │
│ - Public portfolio            │   │                         │
└───────────────────────────────┘   └─────────────┬───────────┘
                                                  │
                                                  ▼
                                     ┌─────────────────────────┐
                                     │    EMAIL NOTIFICATION   │
                                     │                         │
                                     │ Notify TNT when a new   │
                                     │ contact form is sent    │
                                     └─────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│                  DEVELOPMENT AND HOSTING                    │
│                                                             │
│ GitHub                                                      │
│ - Stores website code                                       │
│ - Tracks changes                                            │
│ - Connects to Vercel                                        │
│                                                             │
│ Vercel                                                      │
│ - Hosts the website                                         │
│ - Builds new versions after GitHub updates                  │
│ - Provides deployment previews                              │
└─────────────────────────────────────────────────────────────┘
```

---

### 2.2 What Each Tool Does

#### Next.js

Next.js is the main website framework. It controls:

- Page structure
- Navigation
- English and Vietnamese routes
- Article pages
- Portfolio pages
- Contact pages
- Search-engine visibility
- Page loading

It allows the website to support both static institutional pages and regularly updated content.

#### TypeScript

TypeScript helps reduce coding errors. It defines what kind of information each part of the website expects.

For example, a publication may require:

| Field | Type |
|-------|------|
| Title | String |
| Summary | String |
| Date | Date |
| Language | English / Vietnamese |
| Category | Enum |
| Main content | Rich text |

If one of these fields is missing or incorrectly formatted, TypeScript can help identify the issue during development.

#### Tailwind CSS

Tailwind CSS controls the visual design of the website. It will be used for:

- Typography
- Spacing
- Layout
- Colors
- Responsive design
- Buttons, cards, forms, navigation

> The final styling should follow TNT Capital's future design system. Exact colors, typefaces, and visual rules are not yet permanently fixed.

#### Sanity

Sanity is the **public content management system**. It allows the website administrator to create and edit content without changing website code.

Sanity will manage:

- Homepage content
- Asset Management content
- Research and articles
- Vietnam 2045
- TNT Capital Doctrine
- Ventures
- Team members
- Public portfolio entries

> Sanity should be treated as the **source of truth** for public editorial content.

#### Supabase

Supabase provides the database for non-editorial data. It will initially manage:

- Contact form submissions
- Contact categories
- Submission status
- Public and private visibility records
- Future private data and authenticated features

> Supabase should **not** duplicate the full articles and page content stored in Sanity.

#### GitHub

GitHub stores the website code. It will be used to:

- Save the project
- Track code changes
- Restore earlier versions
- Manage development branches
- Connect the project to Vercel
- Review changes before launch

#### Vercel

Vercel hosts the website. It will:

- Publish the live website
- Automatically create new deployments
- Connect to GitHub
- Provide preview links before changes go live
- Manage the website's delivery to visitors

---

### 2.3 Future Architecture Evolution

The website should remain simple until additional systems are actually required.

```
Current Website
├── Public institutional website
├── Sanity content system
├── Supabase contact database
└── Basic analytics

Future Expansion
├── Publication search
├── Email subscription
├── Private investor access
├── Secure document storage
├── Portfolio reporting
├── Investor communication
├── Advanced analytics
└── Internal admin tools
```

> A custom backend should only be introduced when the website requires functions that Sanity, Supabase, and Next.js cannot handle cleanly.

---

## 3. Website Structure and Routing

### 3.1 Main Routes

The website will use language-based routing:

```
/en/
/vi/
```

Each main page will have an English and Vietnamese route:

**English**
```
/en
/en/asset-management
/en/thinking
/en/thinking/[article]
/en/ventures
/en/ventures/[venture]
/en/team
/en/contact
```

**Vietnamese**
```
/vi
/vi/quan-ly-tai-san
/vi/goc-nhin
/vi/goc-nhin/[article]
/vi/ventures
/vi/ventures/[venture]
/vi/doi-ngu
/vi/lien-he
```

> The exact Vietnamese URL names may be revised later. The main requirement is that each page has a clear language-specific route.

---

### 3.2 Language Behavior

English and Vietnamese content will be connected but edited separately:

```
Publication
├── English version
└── Vietnamese version
```

This means:

- English can be published before Vietnamese
- Vietnamese can be rewritten naturally
- One language can be updated without automatically changing the other
- A missing translation does not block publication
- The website can clearly indicate when another language version is unavailable

**When switching languages:**

- The visitor should remain on the equivalent page when possible
- If no equivalent translation exists, the visitor is taken to the closest relevant page
- The language preference remains consistent while browsing

---

### 3.3 Main Navigation

```
Home
Asset Management
Thinking
Ventures
Team
Contact
Language Selector
```

> There will be no separate About page. About-related content will appear within the Homepage, Team page, Institutional principles, and TNT Capital Doctrine.

---

## 4. Content System

### 4.1 Sanity Content Models

Sanity will store **structured public content**. Structured content means that each content type has defined fields instead of being stored as one large block of text.

---

### 4.2 Page Model

Used for major institutional pages.

| Field | Description |
|-------|-------------|
| Page title | Display title |
| URL slug | Clean URL identifier |
| Language | English / Vietnamese |
| Hero heading | Main headline |
| Hero description | Supporting introduction |
| Page sections | Structured content blocks |
| Search-engine title | SEO title tag |
| Search-engine description | SEO meta description |
| Featured image | Cover image |
| Publication status | Draft / Published / Archived |
| Last updated date | Date of last edit |

**Used for:** Homepage, Asset Management, Ventures overview, Team, Contact introduction

---

### 4.3 Publication Model

Used for research, articles, investment memos, essays, and market commentary.

| Field | Description |
|-------|-------------|
| Title | Publication title |
| URL slug | Clean URL identifier |
| Language | English / Vietnamese |
| Summary | Short description |
| Main content | Full article body |
| Author | Author reference |
| Publication date | Date published |
| Last updated date | Date of last edit |
| Category | See categories below |
| Topic tags | Filterable labels |
| Featured image | Cover image |
| Downloadable PDF | Optional file attachment |
| Related publications | Linked articles |
| Featured status | Homepage or category highlight |
| Publication status | Draft / Review / Published / Archived |
| English version reference | Link to English counterpart |
| Vietnamese version reference | Link to Vietnamese counterpart |

**Publication Categories:**

- Research
- Investment Memo
- Market Commentary
- Essay
- Founder's Note
- Vietnam 2045
- TNT Capital Doctrine

---

### 4.4 Venture Model

Used for publicly displayed TNT ventures.

| Field | Description |
|-------|-------------|
| Venture name | Full name |
| URL slug | Clean URL identifier |
| Language | English / Vietnamese |
| Short description | One-line summary |
| Full description | Detailed overview |
| Venture status | See options below |
| Website link | External URL |
| Logo | Venture logo image |
| Images | Supporting visuals |
| Industry | Sector classification |
| Geography | Market or location |
| TNT relationship | Role TNT plays |
| Featured status | Homepage highlight |
| Public visibility | Shown or hidden publicly |
| English version reference | Link to English counterpart |
| Vietnamese version reference | Link to Vietnamese counterpart |

**Venture Status Options:**

| Status | Meaning |
|--------|---------|
| Active | Currently operating |
| Developing | In progress, not yet launched |
| Portfolio | Supported company |
| Archived | No longer active |
| Private | Not shown publicly |

> Only approved public records should appear on the website.

---

### 4.5 Portfolio Model

Used for selected investments and companies that TNT chooses to display.

| Field | Description |
|-------|-------------|
| Company name | Full name |
| URL slug | Clean URL identifier |
| Language | English / Vietnamese |
| Company description | Investment description |
| Market type | See options below |
| Industry | Sector classification |
| Geography | Market or region |
| Website | External URL |
| Logo | Company logo |
| TNT relationship | Description of involvement |
| Public visibility | Shown or hidden publicly |
| Featured status | Homepage or section highlight |
| English version reference | Link to English counterpart |
| Vietnamese version reference | Link to Vietnamese counterpart |

**Market Type Options:**

| Type | Meaning |
|------|---------|
| Public Market | Publicly listed companies |
| Private Market | Private companies |
| Built by TNT | TNT-originated ventures |
| Supported by TNT | Companies TNT backs or advises |

> The categories should remain flexible because TNT's activity may evolve.

---

### 4.6 Team Member Model

| Field | Description |
|-------|-------------|
| Name | Full name |
| Role | Title or position |
| Biography | Professional background |
| Profile image | Photo |
| LinkedIn or professional link | External profile |
| Team category | See categories below |
| Display order | Position in listing |
| Public visibility | Shown or hidden publicly |
| English version | English biography |
| Vietnamese version | Vietnamese biography |

**Team Categories:**

| Category | Description |
|----------|-------------|
| Founder | The founding member |
| Team | Active team members |
| Advisor | Advisory board members |

> Empty categories should not appear publicly.

---

### 4.7 Author Model

| Field | Description |
|-------|-------------|
| Author name | Full name |
| Role | Title or position |
| Biography | Professional background |
| Profile image | Photo |
| Professional link | External profile |
| Public visibility | Shown or hidden publicly |

This allows publications to have consistent author information.

---

## 5. Database Design

### 5.1 Supabase Purpose

Supabase will **not** store the website's public page and article content. Its main purpose in the MVP is to store **operational data** that should not live inside Sanity.

---

### 5.2 Contact Submissions Table

```
contact_submissions
├── id
├── inquiry_type
├── name
├── email
├── organization
├── website
├── message
├── language
├── status
├── created_at
├── reviewed_at
└── internal_notes
```

**Inquiry Types:**

- Strategic Partnership
- Investment Opportunity
- Founder or Company Introduction
- Research Inquiry
- Media Inquiry
- General Inquiry

**Submission Status:**

| Status | Description |
|--------|-------------|
| New | Just received, not yet reviewed |
| Reviewing | Currently being evaluated |
| Responded | A response has been sent |
| Closed | Inquiry is resolved |
| Spam | Marked as spam, archived |

---

### 5.3 Visibility Records Table

This table may be used if TNT needs to manage additional internal visibility rules outside Sanity.

```
visibility_records
├── id
├── content_type
├── external_content_id
├── visibility_status
├── internal_note
├── created_at
└── updated_at
```

**Visibility Status:** Public / Private / Draft / Archived

> For the MVP, Sanity's own publication controls may already be sufficient. This Supabase table should only be implemented if a real need appears.

---

### 5.4 Future Database Tables

Possible future tables — **do not create in the MVP unless needed:**

- `newsletter_subscribers`
- `investor_users`
- `investor_documents`
- `document_access_logs`
- `portfolio_reports`
- `event_registrations`
- `analytics_events`
- `partnership_submissions`

---

## 6. Core System Flows

### 6.1 Publishing an Article

1. Administrator logs into Sanity
2. Administrator creates a publication
3. Administrator selects the language
4. Administrator adds title, summary, content, category, and date
5. Administrator optionally uploads a PDF
6. Administrator links the English and Vietnamese versions
7. Administrator previews the article
8. Administrator publishes the article
9. Sanity sends updated content to the website
10. Vercel displays the updated article

> The administrator should not need to edit code to publish a new article.

---

### 6.2 Publishing a Vietnamese Version Later

1. English article is already published
2. Administrator creates the Vietnamese version
3. Administrator links it to the English article
4. Vietnamese copy is written and reviewed separately
5. Vietnamese version is published
6. Language switch becomes available on both article pages

---

### 6.3 Contact Submission Flow

1. Visitor opens the Contact page
2. Visitor selects an inquiry category
3. Visitor completes the form
4. Website validates the information
5. Submission is saved in Supabase
6. Email notification is sent to TNT
7. Visitor receives a success message
8. Administrator reviews the submission
9. Submission status can be updated later

> If email delivery fails, the submission should still remain stored in Supabase.

---

### 6.4 Portfolio Visibility Flow

1. Administrator creates a portfolio entry
2. Entry defaults to **Draft** or **Private**
3. Administrator adds the company information
4. Administrator confirms that the entry is approved for public use
5. Visibility is changed to **Public**
6. Entry appears on the website

> Private entries must **never** be returned through public website requests.

---

### 6.5 Deployment Flow

1. Website code is stored in GitHub
2. Changes are made in a development branch
3. Changes are pushed to GitHub
4. Vercel creates a preview deployment
5. Preview is reviewed
6. Approved changes are merged into the main branch
7. Vercel deploys the updated live website

> Content changes inside Sanity should not require a full manual code deployment.

---

## 7. API and Integration Design

### 7.1 Sanity Content Requests

The frontend will request public content from Sanity:

```
GET homepage content
GET Asset Management page
GET all publications
GET publication by slug
GET publications by category
GET featured publications
GET ventures
GET venture by slug
GET public portfolio entries
GET team members
```

> These may be implemented through Sanity queries rather than custom API endpoints.

---

### 7.2 Contact API

The website should have one secure server-side contact endpoint:

```
POST /api/contact
```

**Responsibilities:**

- Validate the submitted information
- Reject missing or invalid fields
- Apply spam protection
- Save the submission to Supabase
- Send an email notification
- Return a success or failure response

> The Supabase database should not be directly writable from the public browser without proper security rules.

---

### 7.3 Analytics

The MVP should track:

| Metric | Description |
|--------|-------------|
| Page views | Overall visit count per page |
| Most-read publications | Top research and articles |
| English vs. Vietnamese usage | Language split |
| Contact form starts | Form open rate |
| Contact form completions | Submission rate |
| Most visited core sections | Navigation behaviour |
| Device type | Desktop / Mobile / Tablet |
| Referral source | Where visitors come from |

**Possible analytics providers:**

- Vercel Analytics
- Plausible
- Google Analytics

> The simplest privacy-conscious option should be selected during implementation.

---

## 8. Admin System

### 8.1 Administrator

The MVP will have **one administrator**. The administrator can:

- Create and edit pages
- Publish research
- Upload PDFs
- Manage translations
- Add ventures
- Add public portfolio entries
- Add team members
- Review contact submissions
- Control public visibility

---

### 8.2 Sanity Admin

The Sanity admin should be organized into clear sections:

```
Content
├── Pages
├── Publications
├── Ventures
├── Portfolio
├── Team
├── Authors
└── Settings
```

> The interface should avoid exposing unnecessary technical fields.

---

### 8.3 Supabase Admin

Supabase will be used mainly to review:

- Contact submissions
- Submission statuses
- Internal notes
- Future private data

The administrator may initially manage this directly through the Supabase dashboard. A custom TNT admin dashboard is **not required** for the MVP.

---

## 9. Hosting and Infrastructure

### 9.1 MVP Hosting

| Service | Purpose |
|---------|---------|
| **Vercel** | Next.js hosting, automatic deployments, preview deployments, website delivery, basic performance monitoring |
| **Sanity** | Public content storage, editorial management, images, articles, structured public records |
| **Supabase** | PostgreSQL database, contact submissions, future authentication, future private data |
| **GitHub** | Code storage, version history, collaboration, deployment connection |

---

### 9.2 Domain Structure

The final domain is expected to become the TNT Capital domain. Until the domain is purchased, the website may use a temporary Vercel domain.

**Recommended final structure:**

```
tntcapital.com
tntcapital.com/en
tntcapital.com/vi
```

The root domain may automatically direct visitors to:

- A default language
- A language selection page
- A language based on browser settings

> The final decision can be made during implementation.

---

### 9.3 Estimated MVP Cost

| Service | Expected Early Cost |
|---------|---------------------|
| Vercel | Free or low-cost plan |
| GitHub | Free |
| Sanity | Free or low-cost plan |
| Supabase | Free or low-cost plan |
| Domain | Annual registration cost |
| Email service | Free or low-cost plan |
| Analytics | Free or low-cost plan |

> The MVP should stay inexpensive because traffic, data storage, and backend activity will initially be low.

---

## 10. Security and Privacy

### 10.1 Content Security

- Draft content must not be publicly visible
- Private ventures must not appear in public queries
- Private portfolio entries must not appear publicly
- Sanity admin access must require authentication
- Supabase admin access must require authentication

### 10.2 Contact Security

- Contact form data should be validated
- Spam protection should be enabled
- Email addresses should not be exposed publicly
- Supabase access rules should prevent unauthorized reading
- Only approved administrators should view submissions

### 10.3 Environment Variables

Private credentials must not be written directly into the website code. They should be stored as environment variables:

- Sanity project credentials
- Supabase keys
- Email service keys
- Analytics credentials

> Public and private keys must be separated correctly.

### 10.4 Data Collection

The website should collect only necessary information. For contact submissions:

- Name
- Email
- Organization
- Website
- Message
- Inquiry type

> The website should not collect unnecessary personal or financial information.

---

## 11. Performance and Search Visibility

### 11.1 Performance Requirements

- Pages should load quickly
- Images should be compressed
- Articles should remain readable on mobile
- Fonts should be optimized
- Unnecessary scripts should be avoided
- Content should be cached where appropriate

### 11.2 Search-Engine Requirements

Each page and publication should include:

- Page title
- Description
- Language
- Canonical URL
- Publication date
- Author
- Social preview image
- Structured article information

> English and Vietnamese pages should clearly reference their alternate language versions.

### 11.3 Accessibility Requirements

- Clear heading structure
- Keyboard-accessible navigation
- Readable contrast ratios
- Descriptive image text
- Proper form labels and error messages
- Reduced-motion support
- Correct Vietnamese character support

---

## 12. Scaling Strategy

| Stage | Name | Includes |
|-------|------|----------|
| **Stage 1** | Institutional Website | Core pages, bilingual content, research publishing, ventures, portfolio, team, contact, basic analytics |
| **Stage 2** | Expanded Publishing | Search, article tags, more authors, email subscription, research downloads, research series, better portfolio filtering |
| **Stage 3** | Private Institutional Features | Investor login, secure documents, private reports, portfolio updates, investor communication, permission-controlled access |
| **Stage 4** | Advanced Platform | Custom backend, internal investment systems, data visualization, portfolio dashboards, research databases, automated reporting, advanced analytics |

> The website should not move to the next stage until a **real operational need** exists.

---

## 13. Risks and Mitigation

| Risk | Severity | Mitigation |
|------|----------|------------|
| Technical stack becomes too complex | 🔴 High | Keep the MVP limited to Next.js, Sanity, Supabase, GitHub, and Vercel |
| Sanity and Supabase duplicate data | 🟡 Medium | Store public editorial content in Sanity and operational data in Supabase |
| Private portfolio data becomes public | 🔴 High | Default all portfolio and venture entries to private or draft |
| English and Vietnamese versions become inconsistent | 🟡 Medium | Connect translations but edit and review them separately |
| Contact emails fail | 🟡 Medium | Store every submission in Supabase before sending email |
| Website appears larger than TNT actually is | 🔴 High | Only publish real activities, people, investments, and ventures |
| Developer learning slows the build | 🟡 Medium | Build one system at a time and avoid adding optional services early |
| Content creation delays launch | 🔴 High | Launch with a small amount of strong content rather than empty sections |
| Future private systems require a rebuild | 🟢 Low | Keep public content, operational data, and private data clearly separated |
| Design changes during development | 🟡 Medium | Use reusable layout components and avoid hardcoding visual rules throughout the site |

---

## 14. Business and System Rules

### BR-01: Institutional Accuracy

- Only real TNT activities may be published
- Empty departments must not appear
- Undeveloped capabilities must not be implied
- Private fund information must not be publicly disclosed
- Investment activity may be described without mentioning the fund

### BR-02: Publication Status

Every public content record must have one status:

| Status | Visible Publicly |
|--------|-----------------|
| Draft | No |
| Review | No |
| Published | Yes |
| Archived | No |

> Only **Published** content may appear publicly.

### BR-03: Translation Independence

- English and Vietnamese versions are edited separately
- One language may be published without the other
- Missing translations must be clearly indicated
- Automatic translation should not be used as the final published copy

### BR-04: Portfolio Visibility

- New portfolio entries default to **Private** or **Draft**
- Public visibility requires manual approval
- Private entries must never appear in public website queries
- Removing public visibility should immediately remove the entry from the website

### BR-05: Contact Submissions

- Every valid submission must be saved in Supabase
- Email notification should occur after successful storage
- A failed email must not delete the stored submission
- Spam submissions may be marked and archived

### BR-06: Content Ownership

| System | Source of Truth For |
|--------|---------------------|
| **Sanity** | Public website content |
| **Supabase** | Contact and operational records |

> The same full content should not be maintained in both systems.

### BR-07: Admin Access

- Only approved administrators may publish content
- Admin credentials must not be shared publicly
- Private credentials must remain outside the codebase
- Multi-user roles may be added later if the team expands

### BR-08: Design Consistency

- All pages should use shared design components
- The visual system should remain minimal and off-white focused
- Exact design tokens may change while the visual direction is still being developed
- Changes to core colors, typography, spacing, and components should be made centrally rather than page by page

---

## 15. MVP Technical Boundary

### The MVP requires:

- Next.js frontend
- TypeScript
- Tailwind CSS
- Sanity CMS
- Supabase contact database
- GitHub repository
- Vercel hosting
- Contact email notification
- Basic analytics
- English and Vietnamese routing
- Public and private visibility controls

### The MVP does **not** require:

- A separate custom backend
- A complex API gateway
- Microservices
- Redis
- Background job queues
- Elasticsearch
- User authentication
- Investor authentication
- AI integration
- Real-time systems
- Complex financial databases
- AWS infrastructure
- A custom admin dashboard

> The system should remain simple until TNT Capital develops a real need for additional infrastructure.

---

## 16. Final Architecture Principle

> The TNT Capital website should be built as a **scalable content platform**, not as a complex financial application.

The system should prioritize:

| Priority | Description |
|----------|-------------|
| **Institutional credibility** | Content and structure must reflect a serious institution |
| **Clear content structure** | Structured content types over freeform HTML |
| **Easy publishing** | No code changes needed to publish new content |
| **Bilingual support** | English and Vietnamese from the beginning |
| **Privacy** | Private data never exposed through public queries |
| **Simple administration** | One administrator, manageable tools |
| **Low initial cost** | Free or low-cost services at launch |
| **Future flexibility** | Architecture can grow without a full rebuild |

The architecture is intentionally **provisional**. The selected tools are appropriate for the current website but may be replaced if the build reveals a simpler or more suitable option.

The important requirement is not loyalty to a specific technology. The important requirement is maintaining a clear separation between:

```
Public website content      ←→  Sanity
Private operational data    ←→  Supabase
Website code                ←→  GitHub
Hosting                     ←→  Vercel
Future institutional systems ←→  TBD
```

---

*Document version: 1.0*  
*Status: Provisional*  
*Last updated: June 2026*  
*TNT Capital — Internal Use*
