# Vivek Ambariya — Portfolio

A single-page, scroll-driven portfolio. Static HTML, CSS and vanilla JavaScript —
no build step, no framework, no dependencies to install.

**Live:** _enable GitHub Pages on this repo to publish it_

---

## Running it locally

The page loads a video and a stylesheet over relative paths, so it needs to be
served over HTTP rather than opened directly from the filesystem:

```bash
python3 -m http.server 8080
```

Then open <http://127.0.0.1:8080>.

## What's in here

```
index.html                     the whole page — markup and inline layout styles
support.js                     scroll-progress, theme toggle, section reveals,
                               and the WORKIZO booking-lifecycle walkthrough
_ds/modernist-.../styles.css   design tokens + component classes
uploads/                       hero image, intro video, résumé PDF
```

## Design system

Colour, type and spacing all resolve from CSS custom properties in
`_ds/modernist-…/styles.css`. Retune the palette there and the whole page follows.

**Palette** — [Color Hunt](https://colorhunt.co/palette/524646a8a492fcf2e5ec5b38)

| Token | Value | Role |
| --- | --- | --- |
| `--color-bg` | `#FCF2E5` | page ground |
| `--color-text` | `#524646` | body ink |
| `--color-accent` | `#EC5B38` | accent — fills, rules, callouts |
| `--color-accent-2` | `#A8A492` | secondary; muted text in dark mode |

Two derived tokens keep text legible on top of those colours, since the accent
is too light to carry small text on cream at only 3.1:1:

| Token | Light | Dark | Role |
| --- | --- | --- | --- |
| `--acc-ink` | `#972A0D` | `#FE9176` | accent-toned text on the page ground (7.2:1) |
| `--color-on-accent` | `#251A1A` | `#251A1A` | ink sitting on an accent fill (4.9:1) |

The neutral, accent and secondary ramps are each nine steps generated in OKLCH
on one shared lightness scale, so the same step of any role carries the same
visual weight.

Both themes were checked against WCAG AA across every text node on the page:
**no failures in either theme.**

## Accessibility

- Light and dark themes, following `prefers-color-scheme` with a manual toggle
- Motion honours `prefers-reduced-motion`
- Skip-to-content link, semantic landmarks, visible focus states

---

Built with [Superdesign](https://superdesign.dev). Typeface: Archivo.
