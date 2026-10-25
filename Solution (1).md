# Assignment 7.4 — Solution: Modern Landing Page Header + Hero

## Project Structure
```
landing-header-hero/
├── index.html
├── style.css
└── images/
    └── hero.svg
```
The complete code is in the attached files. The key parts:

## 1. Header (logo | navigation | CTA button)
```css
.site-header { position: sticky; top: 0; z-index: 100; }       /* stays on top while scrolling */
.site-header__inner {
  display: flex;
  justify-content: space-between;   /* logo left, button right, links in the middle */
  align-items: center;              /* vertical centering */
  flex-wrap: wrap;                  /* wraps on small screens */
  gap: 16px;
}
```
The header contains the logo (`.logo`), the navigation (`ul.main-nav__list`, also a flex row) and the CTA button (`.button--small`, "Get started").

## 2 & 3. Hero: heading, paragraph, buttons and illustration
- Text block (`.hero__content`): eyebrow tag, `h1` (with a colored `span`), paragraph, two buttons (primary and outline) and a small note.
- Image block (`.hero__media`): `images/hero.svg`, an illustration I drew (dashboard window with a rocket), with a descriptive `alt`.

## 4 & 5. Side-by-side layout and alignment
```css
.hero__inner {
  display: flex;
  justify-content: space-between;
  align-items: center;     /* text and image share the same vertical center */
  flex-wrap: wrap;         /* image goes under the text on small screens */
  gap: 32px;
}
.hero__content { flex: 1 1 380px; }
.hero__media   { flex: 1 1 340px; display: flex; justify-content: center; }
```
The heading uses a fluid size, `font-size: clamp(2rem, 5vw, 3.2rem)`, so it shrinks on phones.

## 6. Footer and Sticky Section (earlier CSS concepts)
- **Sticky header:** `position: sticky` (Assignment 6.4). I verified that after scrolling 900px the header's top is still at `0`. On phones (≤ 720px) it becomes `position: static`, because a stacked header would cover too much of a small screen.
- **Footer:** dark background, flex row with brand, links and copyright (`justify-content: space-between`, `flex-wrap`), colors and spacing from CSS variables (`:root`, Assignment 5.4), and the box model for padding.

## 7. Layout at Different Widths
| Width | Hero layout | Horizontal overflow |
|-------|-------------|---------------------|
| 1280px | Text and image side by side | none |
| 800px | Image below the text | none |
| 375px | Image below the text, centered content, buttons centered | none |

## Submission
- ✅ Complete code for the header + hero section: `index.html`, `style.css`, `images/hero.svg` (attached)
- 📸 Optional screenshots (attached `screenshot-1280px.png`, `screenshot-800px.png` and `screenshot-375px.png` are references rendered by me)
