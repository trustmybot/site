# TrustMyBot site

Source of [trustmybot.org](https://trustmybot.org), served by GitHub Pages from `main` as is. Hand-written HTML and CSS: no framework, no build step, no external requests.

| File | Purpose |
| --- | --- |
| `index.html` | The one-page site, including SEO meta tags, Open Graph tags and JSON-LD |
| `style.css` | Styles, with dark and light themes via `prefers-color-scheme` |
| `hero.svg` | Animated hero image |
| `og.png` | 1200x630 social preview, a frame cut from the hero video |
| `favicon.svg` | Site icon |
| `404.html` | Page served for unknown paths |
| `robots.txt`, `sitemap.xml` | Crawler hints |
| `CNAME` | Custom domain for GitHub Pages |

`hero.svg` is generated in the private `tmb-brand` repo and copied here byte-identical from `hero/dist/hero-auto.svg`. Edit it there, then copy it over; do not edit it in this repo.
