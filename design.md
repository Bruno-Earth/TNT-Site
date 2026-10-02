# TNT CAPITAL — Brand Identity
## Core Visual System v1.0

A practical visual foundation for the TNT Capital website and digital publishing system.

This document formalizes the typography, color hierarchy, section backgrounds, text pairings, interface treatments, and Elementor / frontend implementation rules derived from TNT’s existing green identity.

| Token | Hex |
| --- | --- |
| Dark Green | `#275317` |
| Military Green | `#4D6345` |
| TNT Mist | `#F5FFF9` |
| Koi Red | `#E0563A` |

**Status:** Finalized visual foundation for website implementation.  
**Source of truth** for colors, type, surfaces, buttons, and links across `PRD.md`, `planning.md`, `system.md`, and the live redesign.

**Not defined by this version:** logo construction, logo typography, photography, illustration, iconography, or motion language.

---

## 1. Purpose and Scope

TNT’s existing identity provides three core colors but did not define a complete digital visual system. This guide turns those anchors into a consistent website system without introducing a new brand direction.

The goal is not to make TNT look decorative. The goal is to make every page feel intentional, institutional, editorial, and recognizably TNT.

### What is locked in this version

- Typography families and hierarchy for English and Vietnamese
- Primary, secondary, light, neutral, and utility color roles
- H1–H5 scale, body scale, metadata, navigation, and button typography
- Section background system and approved text/background pairings
- Buttons, links, borders, dividers, and research/article typography
- Global font and color setup for WordPress/Elementor and for tokenized frontends (e.g. Tailwind CSS variables)

### What this guide does not invent

Logo font, photography style, illustration style, iconography, and motion remain intentionally open.

---

## 2. Existing Brand Foundation

| Color | Hex | Role | Usage priority |
| --- | --- | --- | --- |
| Dark Green | `#275317` | Primary brand color | Highest |
| Military Green | `#4D6345` | Secondary/support color | Secondary |
| TNT Mist | `#F5FFF9` | Light brand surface | Supporting |
| Koi Red | `#E0563A` | Line accent only | Restricted |

### Color hierarchy

- Use `#275317` for primary brand expression, major headings, primary buttons, and selected dark sections.
- Use `#4D6345` for secondary emphasis, hover states, small labels, diagrams, and supporting UI.
- Use `#F5FFF9` for light brand surfaces, dark-section body text, and subtle emphasis.
- Use `#E0563A` only for 1–2px lines, hairline rules, and hover underlines — never as type or a section fill.
- Do not add gold, blue, magenta, or another accent color simply to make the site feel more “financial.”

---

## 3. Typography System

| Family | Role |
| --- | --- |
| **Source Serif 4** | Display + H1–H3 + article titles + pull quotes |
| **Source Sans 3** | H4–H5 + body + UI + navigation + tables + metadata |

Both families are SIL OFL and support Vietnamese.

### Font roles

| Role | Typeface | Weight |
| --- | --- | --- |
| Display / Hero | Source Serif 4 | SemiBold 600 |
| H1–H3 | Source Serif 4 | SemiBold 600 |
| H4–H5 | Source Sans 3 | SemiBold 600 |
| Body / Lead | Source Sans 3 | Regular 400 |
| Navigation / Buttons | Source Sans 3 | SemiBold 600 |
| Metadata / Captions | Source Sans 3 | Medium 500 |
| Tables / Charts / Forms | Source Sans 3 | Regular 400 |

Do not substitute Be Vietnam Pro, Poppins, Segoe UI, Inter, or other faces for core UI.

---

## 4. Type Scale

| Style | Font | Weight | Desktop | Mobile | Line height |
| --- | --- | --- | --- | --- | --- |
| H1 | Source Serif 4 | 600 | 56 px | 38 px | 1.08 |
| H2 | Source Serif 4 | 600 | 44 px | 32 px | 1.12 |
| H3 | Source Serif 4 | 600 | 34 px | 27 px | 1.18 |
| H4 | Source Sans 3 | 600 | 26 px | 23 px | 1.25 |
| H5 | Source Sans 3 | 600 | 20 px | 19 px | 1.30 |
| Lead | Source Sans 3 | 400 | 21 px | 19 px | 1.55 |
| Body | Source Sans 3 | 400 | 18 px | 17 px | 1.65 |
| Body Small | Source Sans 3 | 400 | 16 px | 15 px | 1.55 |
| Navigation | Source Sans 3 | 600 | 15 px | 15 px | 1.20 |
| Caption / Meta | Source Sans 3 | 500 | 14 px | 14 px | 1.45 |
| Fine print | Source Sans 3 | 400 | 13 px | 13 px | 1.45 |

### Letter spacing

- H1: `-0.02em`
- H2: `-0.015em`
- H3: `-0.01em`
- H4–H5 and body: `0`
- Navigation / buttons / metadata: `+0.01em`

### Body size rule

Default reading size is **18 px desktop / 17 px mobile**. 14 px is reserved for metadata and captions.

---

## 5. Complete Color System

| Token | Hex | Class | Primary use |
| --- | --- | --- | --- |
| Primary / Dark Green | `#275317` | Core brand | Headings, primary buttons, dark sections |
| Secondary / Military Green | `#4D6345` | Core brand | Secondary emphasis, hover, labels |
| TNT Mist | `#F5FFF9` | Core brand | Light branded surface, light-on-dark copy |
| White | `#FFFFFF` | Utility | Primary neutral background, dark-section headings |
| Text Ink | `#202820` | Utility | Main body text |
| Text Gray | `#5F685F` | Utility | Secondary copy, dates, metadata |
| Surface Gray | `#F2F5F1` | Utility | Neutral section background |
| Border | `#DFE5DC` | Utility | Dividers, cards, tables |
| Koi Red | `#E0563A` | Line accent | Hover underlines, hairline rules |
| Koi Deep | `#C2452E` | Line accent | Hover/pressed state on a Koi line |
| Koi Wash | `#F8E8E3` | Line accent | Optional faint track behind a rule |

### Accessibility baseline (WCAG AA)

| Pairing | Contrast |
| --- | --- |
| `#275317` on `#FFFFFF` | 8.99:1 |
| `#275317` on `#F5FFF9` | 8.80:1 |
| `#202820` on `#FFFFFF` | 15.15:1 |
| `#5F685F` on `#FFFFFF` | 5.78:1 |
| `#F5FFF9` on `#275317` | 8.80:1 |
| `#FFFFFF` on `#4D6345` | 6.59:1 |

---

## 6. Section Background and Text Pairings

| Surface | Background | Heading | Body | Use |
| --- | --- | --- | --- | --- |
| White | `#FFFFFF` | `#275317` | `#202820` | Default reading and research sections |
| TNT Mist | `#F5FFF9` | `#275317` | `#202820` | Light branded sections / gentle emphasis |
| Soft Gray | `#F2F5F1` | `#275317` | `#202820` | Neutral separation / data-heavy blocks |
| Dark Green | `#275317` | `#FFFFFF` | `#F5FFF9` | High-emphasis hero, closing, selected feature sections |

### Military Green rule

`#4D6345` is **not** a fifth default section background. Use it for secondary state, small-area fill, chart color, hover, or supporting emphasis.

### Recommended page rhythm

`White → TNT Mist → White → Soft Gray → Dark Green → White`

Research pages should use more white. Homepage and vision pages can use more Mist and Dark Green.

---

## 7. Interface Treatments

### Buttons

| Type | Background | Text / Border | Hover |
| --- | --- | --- | --- |
| Primary | `#275317` | `#FFFFFF` | `#4D6345` |
| Secondary | Transparent | `#275317` border | `#F5FFF9` fill |
| On dark section | `#F5FFF9` | `#275317` | `#FFFFFF` |

Button label typeface is always **Source Sans 3 SemiBold 600**.

### Links

- Default in-body text link: `#275317` with underline.
- Do not invent a brighter “web blue” or bright green link color.
- In-body hover may shift to `#4D6345` while retaining underline or equivalent visible state.
- Header / nav hover: keep the label color unchanged. Draw a 1px underline in **Koi Red `#E0563A`**, offset about 4px. Never recolor the nav word itself to red.

### Koi Red rule

`#E0563A` is a **line accent**, not a fourth equal brand color and not a text color. Default weight is 1px (2px maximum). Do not use it for headings, body copy, buttons, or full-section backgrounds.

### Borders and dividers

- Standard solid border: `#DFE5DC`
- Opacity alternative: `rgba(39, 83, 23, 0.15)`
- Stronger divider: `rgba(39, 83, 23, 0.25)`

### Heading color rule

Light surface = `#275317` headings. Dark surface = `#FFFFFF` headings.

---

## 8. Research and Editorial System

| Element | Typeface | Size | Weight |
| --- | --- | --- | --- |
| Article title | Source Serif 4 | 56 px | 600 |
| Article subtitle / deck | Source Sans 3 | 21 px | 400 |
| Article body | Source Sans 3 | 18 px | 400 |
| Article H2 | Source Serif 4 | 36 px | 600 |
| Article H3 | Source Serif 4 | 28 px | 600 |
| Metadata | Source Sans 3 | 14 px | 500 |
| Pull quote | Source Serif 4 | 26 px | 400 italic |

Editorial constraints: controlled measure for long-form; serif for hierarchy not dense UI; green as structure not decoration; whitespace before boxes/shadows.

---

## 9. Global Implementation Tokens

**Primary design surface:** Framer (styles + components), edited with Cursor connected to the Framer project.  
**Final production host:** TNT’s WordPress server (publish / handoff after Framer approval).

Set Framer color and text styles from this document first. When moving to WordPress, map the same tokens into theme / Elementor globals — do not invent a second palette.

### Framer / Elementor Global Fonts

| Token | Typeface | Default weight |
| --- | --- | --- |
| Primary | Source Serif 4 | 600 |
| Secondary | Source Sans 3 | 600 |
| Text | Source Sans 3 | 400 |
| Accent | Source Sans 3 | 600 |

### Framer / Elementor / CSS Global Colors

| Token | Value |
| --- | --- |
| Primary | `#275317` |
| Secondary | `#4D6345` |
| Text | `#202820` |
| Accent | `#275317` |
| TNT Mist | `#F5FFF9` |
| Koi Red | `#E0563A` |
| White | `#FFFFFF` |
| Text Gray | `#5F685F` |
| Surface Gray | `#F2F5F1` |
| Border | `#DFE5DC` |

### Frontend CSS variable mapping (required)

When implementing with Tailwind or CSS variables, map semantic tokens to the brand roles above — do not redefine Secondary as Soft Gray or Accent as TNT Mist.

| CSS token | Must resolve to |
| --- | --- |
| `--primary` | `#275317` |
| `--secondary` (brand secondary) | `#4D6345` |
| `--accent` (brand accent) | `#275317` |
| `--foreground` / text ink | `#202820` |
| `--muted-foreground` / text gray | `#5F685F` |
| `--muted` / surface gray | `#F2F5F1` |
| mist / light brand surface | `#F5FFF9` |
| `--border` | `#DFE5DC` |
| `--ring` / focus | `#4D6345` |

Surface Gray and TNT Mist may be separate utility tokens; they must not replace Secondary or Accent brand roles.

### Font hosting

Prefer self-hosted WOFF2. Retain SIL OFL 1.1 notices. Do not embed font binaries in this guide.

---

## 10. Usage Rules and Governance

### Do

- Use Dark Green as the primary identity anchor.
- Use Source Serif 4 selectively at the top of the hierarchy.
- Use Source Sans 3 for functionality, long-form reading, and interface clarity.
- Keep section backgrounds to the four approved surfaces.
- Use white space and strong hierarchy before adding decoration.
- Test Vietnamese pages alongside English pages during implementation.

### Do not

- Add gold, blue, magenta, or a new accent beyond Koi Red without a formal identity revision.
- Use Koi Red as type, a button fill, or a section background.
- Use Military Green and Dark Green interchangeably as equal primary colors.
- Use 14 px as default article body text.
- Use serif for navigation, forms, dense tables, or small UI labels.
- Create one-off heading colors or section backgrounds.
- Treat this guide as defining logo, photography, illustration, or motion rules.

### Decision hierarchy

1. Readability and accessibility  
2. Consistency with this system  
3. TNT core green hierarchy  
4. Editorial restraint  
5. Decorativeness  

---

## 11. One-Page Quick Reference

| Item | Value |
| --- | --- |
| Heading family | Source Serif 4 (H1–H3) |
| Functional heading | Source Sans 3 (H4–H5) |
| Body / UI | Source Sans 3 |
| Primary green | `#275317` |
| Secondary green | `#4D6345` |
| Light brand surface | `#F5FFF9` |
| Body text | `#202820` |
| Secondary text | `#5F685F` |
| Neutral surface | `#F2F5F1` |
| Border | `#DFE5DC` |
| Line accent | Koi Red `#E0563A` (underlines/rules only) |
| Body size | 18 px desktop / 17 px mobile |
| Primary button | `#275317` / `#FFFFFF` |
| On-dark button | `#F5FFF9` / `#275317` |
| Light-section heading | `#275317` |
| Dark-section heading | `#FFFFFF` |
| Dark-section body | `#F5FFF9` |

---

## 12. Live Redesign Alignment Notes

Audit of the current redesign preview ([methods-printable-fixes-addressing.trycloudflare.com](https://methods-printable-fixes-addressing.trycloudflare.com/)), checked against this guide.

### Already aligned

- Source Serif 4 + Source Sans 3 only (no third UI family)
- Primary `#275317`, Text Ink `#202820`, Border `#DFE5DC`, Text Gray `#5F685F`, Surface Gray `#F2F5F1`, TNT Mist `#F5FFF9`
- Dark Green hero with white / Mist type and on-dark Mist CTA (`#F5FFF9` / `#275317`)
- Secondary outlined CTA uses `#275317` border and text
- Body reading size near 17–18 px; H1 near display scale with negative letter-spacing

### Remaining gaps to fix in implementation

| Gap | Required by this guide |
| --- | --- |
| CSS `--secondary` mapped to Soft Gray `#F2F5F1` | Brand Secondary must be `#4D6345`; Soft Gray stays a surface utility |
| CSS `--accent` mapped to TNT Mist `#F5FFF9` | Brand Accent must be `#275317`; Mist stays a surface / on-dark text utility |
| Some H2 / card H3 titles set in Source Sans 3 | H2–H3 and article titles use Source Serif 4 600 |
| Article card chrome uses white/glass overlays and near-black label chips | Prefer approved surfaces (White / Mist / Soft Gray / Dark Green) and Text Ink / Mist text pairings |
| Destructive red `#8A2B1F` present for forms | Allowed as utility error only — not a brand accent |

### Current information architecture (live preview)

Primary nav / IA names on the redesign (use these labels in product docs going forward):

1. Vietnam 2045  
2. About  
3. Insights  
4. Investment Management  
5. Venture  
6. Manifesto  
7. Contact  

Legacy doc labels map as: Thinking → Insights; Asset Management → Investment Management; Ventures → Venture; TNT Capital Doctrine → Manifesto (confirm copy). Team content may live under About rather than as a top-level nav item.

---

## Appendix: Source and Licensing Notes

Existing TNT identity: `#275317` Dark Green; `#4D6345` Military Green; `#F5FFF9` mist; prior body font Segoe UI 14.

Typography: Google Fonts Source Serif 4 and Source Sans 3, SIL Open Font License 1.1, with Vietnamese subsets.
