---
title: Portfolio Design System
description: Visual tokens and component guidance for Naufal Rifqi's portfolio.
tags:
  - design
  - portfolio
  - reference
---

# Portfolio Design System

A practical visual reference for keeping the portfolio consistent across the landing page, project cards, case studies, and contact experience. Values below reflect the current portfolio design.

## Visual direction

The portfolio pairs editorial typography with a warm, paper-like canvas and restrained terracotta accents. It should feel personal, thoughtful, and clear, with enough contrast and whitespace to let case study content lead.

Use warm neutrals as the foundation. Reserve terracotta for emphasis and interaction; use forest green only for positive availability or supporting accents. Keep layouts spacious and composition-led, with thin dividers and a few deliberate card surfaces. Light and dark themes share the same hierarchy and accent logic.

## Color

| Token | Light | Dark | Use |
| --- | --- | --- | --- |
| Ink | `#0f0e0c` | `#f0ede6` | Main text, dark surfaces, primary button |
| Paper | `#f4f0e8` | `#141210` | Main page background |
| Cream | `#ede8dc` | `#1e1c19` | Secondary surface, section background, controls |
| Terracotta | `#c8401a` | `#c8401a` | Main accent, links, active and hover states |
| Forest | `#3a5a40` | `#3a5a40` | Availability indicator and positive supporting accent |
| Muted | `#7a776e` | `#9a9690` | Secondary labels and metadata |
| Card | `#ffffff` | `#1e1c19` | Cards, floating panels |
| Border | `rgba(15,14,12,.10)` | `rgba(240,237,230,.10)` | Dividers, outlines, card boundaries |

### Color use

- Maintain readable contrast between text and its surface; do not use muted text for essential information.
- Keep accent usage selective. Avoid turning large page areas terracotta.
- Use the forest accent for availability or positive status, not as a second primary brand color.
- In dark theme, keep surfaces near-black and warm. Do not invert the light palette mechanically.
- Use subtle, low-opacity borders to separate content without boxing in every section.

## Typography

| Role | Typeface | Size / behavior | Weight and treatment |
| --- | --- | --- | --- |
| Display and headings | DM Serif Display | Fluid; hero scales from roughly `2.8rem` to `5.5rem`; section titles remain expressive and compact | 400; use italic serif for selected emphasis |
| Body and controls | DM Sans | Body copy around `1rem`, with generous line-height | 300–500 |
| Navigation | DM Sans | Compact, around `.82rem` | 500, uppercase, `.04em` tracking |
| Eyebrow and metadata | DM Sans | Small, around `.68–.75rem` | 500, uppercase, increased tracking |
| Project titles | DM Serif Display | Clear, editorial headings sized to the project hierarchy | 400 |

Use DM Serif Display for the portfolio wordmark, hero name, section headings, and project titles. Use DM Sans for paragraphs, navigation, labels, buttons, and form controls. Let the serif carry the personality; keep the sans-serif practical and legible. Headlines use close tracking, while body copy stays open and easy to read.

## Layout and spacing

- Use a 12-column grid for the portfolio work gallery, with consistent gaps around `1.25rem`.
- Hero is a two-column split on wide screens, with copy and imagery given equal visual weight.
- Sections use responsive vertical padding: `clamp(4rem, 10vw, 8rem)`; horizontal gutters are approximately `4vw`.
- Keep section headers aligned to the content grid. Pair a clear title with a small section number or eyebrow and a thin bottom divider.
- Use CSS Grid and Flexbox to adapt cards and content. Skill cards use an auto-fitting grid with a minimum width near 260px.
- Navigation height is 68px on desktop and 60px on small screens. Account for the fixed navigation when placing page anchors and hero content.
- Keep case study reading widths narrower than the overall page grid. Let diagrams and image galleries expand when the material benefits from it.
- Maintain generous space between distinct sections and tighter spacing within related groups.

### Responsive behavior

| Range | Guidance |
| --- | --- |
| 1200px and up | Two-column hero and full navigation; use the 12-column work layout. |
| 768–1199px | Retain a spacious composition while reducing grid complexity and gaps as needed. |
| 767px and below | Switch to compact navigation and a single-column content flow; use 60px navigation and restore the system cursor. |
| 374px and below | Reduce small-screen spacing and type carefully to prevent overflow. |

## Shape, borders, and depth

- Buttons use a subtle 4px radius; small form controls use 6px.
- Work cards and image blocks use an 8px radius. The portrait frame uses a 12px radius on its top corners.
- Pills use a full radius. Skill tags are nearly square with a 2px radius.
- Use thin, low-contrast borders as the default separation treatment.
- Floating hero details may use a soft shadow such as `0 8px 32px rgba(0,0,0,.08)`; reserve stronger elevation for elements that genuinely float above content.
- Prefer flat surfaces and borders over repeated shadows or layered glass effects.

## Components

### Navigation

Use a fixed, full-width bar with a translucent page-colored surface, backdrop blur, and a bottom divider. Desktop links are compact uppercase labels; the active or hovered link shifts to the ink color and gains a short terracotta underline. Include a clearly operable theme toggle. On mobile, use a full-screen menu below the bar and keep its colors theme-aware.

### Buttons and links

- **Primary:** ink background with paper text; on hover, switch to terracotta and lift by 2px.
- **Outline:** transparent background with an ink border; on hover, change border and text to terracotta and lift slightly.
- **Text action:** quiet uppercase or inline link; use terracotta for hover and focus emphasis.
- Preserve visible keyboard focus and adequate hit areas. Do not make hover the only indication of interactivity.

### Hero

Lead with a concise role or availability eyebrow, a large name or statement, short introductory copy, and one or two clear actions. The adjacent visual can be a portrait, project artifact, or authored placeholder. Floating metadata should be limited to one or two compact cards.

### Project cards

Use a consistent image ratio (typically 16:9), clear title, short description, and compact category or status metadata. Keep card surfaces light in light mode and warm charcoal in dark mode. Use hover motion sparingly; preserve clarity of project imagery and text.

### Case study content

Use a clear title hierarchy, readable paragraphs, and deliberate breathing room. Combine narrative with evidence: process steps, key screens, results, and concise statistics. Highlight important findings with a restrained accent surface rather than adding decorative elements.

### Forms and contact

Use clearly labeled fields, comfortable padding, and a visible focus border. Group related fields and keep the submit action visually prominent. Ensure errors, success messages, and required-field states are communicated in text as well as color.

### Motion and interaction

Use short transitions for color and control changes (about 0.2–0.3s). Larger page and content reveals can be slower (about 0.4–0.7s). Keep movement small and purposeful, and honor reduced-motion preferences. Custom cursor effects are desktop-only; standard system cursors remain on touch devices.

## Do and avoid

| Do | Avoid |
| --- | --- |
| Use warm off-white and near-black as the main surfaces. | Introduce cool gray surfaces that fight the warm palette. |
| Apply terracotta to meaningful emphasis and interactive states. | Use multiple competing accent colors or accent every heading. |
| Keep typography editorial and hierarchy obvious. | Use display type for long paragraphs or dense metadata. |
| Use whitespace and dividers to structure the page. | Put every section inside a bordered card. |
| Keep cards and motion restrained so the work remains the focus. | Add heavy shadows, large hover movement, or motion without purpose. |
| Check both themes and narrow screens when changing shared components. | Assume a light-theme-only change is safe for dark mode. |

## Implementation tokens

The current CSS custom properties are:

```css
:root {
  --ink: #0f0e0c;
  --paper: #f4f0e8;
  --cream: #ede8dc;
  --accent: #c8401a;
  --accent2: #3a5a40;
  --muted: #7a776e;
  --card: #ffffff;
  --border: rgba(15, 14, 12, 0.1);
  --serif: 'DM Serif Display', serif;
  --sans: 'DM Sans', sans-serif;
  --nav-h: 68px;
}

[data-theme="dark"] {
  --ink: #f0ede6;
  --paper: #141210;
  --cream: #1e1c19;
  --muted: #9a9690;
  --card: #1e1c19;
  --border: rgba(240, 237, 230, 0.1);
}

@media (max-width: 767px) {
  :root { --nav-h: 60px; }
}
```

Treat the existing CSS variables as the implementation source of truth. When changing a token, update every component-specific override that depends on it and check both theme modes.
