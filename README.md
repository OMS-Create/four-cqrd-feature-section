# Frontend Mentor - Four card feature section solution

This is a solution to the [Four card feature section challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/four-card-feature-section-weK1eFYK). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
  - [AI Collaboration](#ai-collaboration)
- [Author](#author)

---

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size

### Screenshot

![Four card feature section — desktop view](./screenshot.jpg)

### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

---

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties (design tokens for color palette)
- CSS Grid — `grid-template-areas` for named region layout
- Flexbox — card internals for icon positioning
- Fluid typography and spacing with `clamp()`
- Google Fonts — [Poppins](https://fonts.google.com/specimen/Poppins) (weights: 200, 400, 600)
- Mobile-first responsive breakpoint at `600px`

### What I learned

The biggest takeaway from this challenge was how well **`grid-template-areas`** communicates layout intent. Naming regions like `supervisor-card`, `team-card`, etc. makes the two-row spanning of the side cards immediately readable:

```css
.grid-card {
  grid-template-areas:
    "supervisor-card team-card calculator-card"
    "supervisor-card karma-card calculator-card";
}
```

I also got hands-on with **`clamp()`** for fluid sizing. Instead of hard breakpoints for every spacing value, a single `clamp()` expression handles the full range from mobile to desktop:

```css
html {
  font-size: clamp(14px, 1.2vw + 0.5rem, 16px);
}
```

Finally, using **`display: flex; flex-direction: column`** inside each card, combined with `margin-top: auto` and `align-self: flex-end` on the icon, was a clean solution for pushing the icon to the bottom-right corner regardless of how tall the card text is:

```css
.s-icon {
  align-self: flex-end;
  margin-top: auto;
}
```

### Continued development

- **Mobile-first workflow** — this project was built desktop-first. I want to practice writing the mobile layout as the base and layering desktop styles on top with `min-width` queries.
- **CSS Subgrid** — exploring `subgrid` to align content rows across cards without relying on fixed heights or flex tricks.
- **Accessibility** — testing the full color-contrast ratios using real tooling.

### Useful resources

- [MDN: grid-template-areas](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas) — the clearest reference for named grid regions and spanning.
- [CSS Tricks: A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/) — go-to cheat sheet for grid property behaviour.
- [MDN: clamp()](https://developer.mozilla.org/en-US/docs/Web/CSS/clamp) — understanding the min, preferred, and max arguments for fluid design.

### AI Collaboration

- **Tool used:** Claude (Anthropic)
- **How I used it:** Getting the desktop three-column spanning layout and the mobile `repeat(1, minmax(0, 1fr))` single-column reflow right in a single pass — with inline comments explaining every change so I could follow and learn the reasoning.
- **What I'd do differently:** Start with a rough attempt first before asking for help, so the AI's explanations connect more directly to mistakes I'd already made and tried to debug.

---

## Author

- Frontend Mentor — [@OMichaels](https://www.frontendmentor.io/OMS-Create)
- GitHub — [OMS-Create](https://github.com/OMS-Create)
