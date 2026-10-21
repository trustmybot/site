# TrustMyBot site

Source of [trustmybot.org](https://trustmybot.org), served by GitHub Pages from `main` as is. Hand-written HTML, CSS and a little vanilla JS: no framework, no build step, no external requests.

The page is intentionally words-light: the animated hero carries the story, and the text is limited to the title, two buttons, the install commands and the footer.

| File | Purpose |
| --- | --- |
| `index.html` | The one-page site, including SEO meta tags, Open Graph tags, JSON-LD and the sun/moon theme toggle |
| `style.css` | Styles: dark by default, light under `prefers-color-scheme: light`, overridden by `data-theme` on `<html>` |
| `hero-auto.svg` | Animated hero that follows the system theme (dark by default); used until the first toggle and without JS |
| `hero-dark.svg` | Animated hero, dark only; used after toggling to dark |
| `hero-light.svg` | Animated hero, light only; used after toggling to light |
| `og.png` | 1200x630 social preview, a frame cut from the hero video |
| `favicon.svg` | Site icon |
| `404.html` | Page served for unknown paths |
| `robots.txt`, `sitemap.xml` | Crawler hints |
| `CNAME` | Custom domain for GitHub Pages |

## Theme

The page follows the browser's light/dark setting and renders dark when the browser gives no preference. The sun/moon icon button in the footer, right of the links, shows the theme on screen (moon while dark, sun while light), flips to the other theme on click, and stores the choice in `localStorage` under `theme`; from then on the page no longer follows the system until that key is cleared. CSS picks the icon with the same rules as the palette, so it is correct before the script runs and without JS. A small script in `<head>` applies the stored choice before the stylesheet loads, so there is no flash of the wrong theme. The toggle also swaps the hero image, because an SVG in `<img>` only sees the system preference. If storage is blocked the toggle still works for the current page view; without JS the page follows the system.

## Hero images

`hero-auto.svg`, `hero-dark.svg` and `hero-light.svg` are generated in the private `tmb-brand` repo and copied here byte-identical from `hero/dist/`. Edit them there, then copy them over; do not edit them in this repo.
