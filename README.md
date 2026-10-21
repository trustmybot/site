# TrustMyBot site

Source of [trustmybot.org](https://trustmybot.org), served by GitHub Pages from `main` as is. Hand-written HTML, CSS and a little vanilla JS: no framework, no build step, no external requests.

| File | Purpose |
| --- | --- |
| `index.html` | The one-page site, including SEO meta tags, Open Graph tags, JSON-LD and the Auto/Light/Dark theme switch |
| `style.css` | Styles: dark by default, light under `prefers-color-scheme: light`, overridden by `data-theme` on `<html>` |
| `hero-auto.svg` | Animated hero that follows the system theme (dark by default); used for Auto and without JS |
| `hero-dark.svg` | Animated hero, dark only; used when Dark is chosen |
| `hero-light.svg` | Animated hero, light only; used when Light is chosen |
| `og.png` | 1200x630 social preview, a frame cut from the hero video |
| `favicon.svg` | Site icon |
| `404.html` | Page served for unknown paths |
| `robots.txt`, `sitemap.xml` | Crawler hints |
| `CNAME` | Custom domain for GitHub Pages |

## Theme

The page follows the browser's light/dark setting and renders dark when the browser gives no preference. The switch at the top right overrides it: Light or Dark is stored in `localStorage` under `theme`, Auto removes the key and follows the system again. A small script in `<head>` applies the stored choice before the stylesheet loads, so there is no flash of the wrong theme. The switch also swaps the hero image, because an SVG in `<img>` only sees the system preference. If storage is blocked the switch still works for the current page view; without JS the page follows the system.

## Hero images

`hero-auto.svg`, `hero-dark.svg` and `hero-light.svg` are generated in the private `tmb-brand` repo and copied here byte-identical from `hero/dist/`. Edit them there, then copy them over; do not edit them in this repo.
