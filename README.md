# AviAdi Enterprises Website

A single-page professional profile site for **AviAdi Enterprises**, centered on
founder **Ashok Mittal** (fintech entrepreneur — MD & CEO, BillMart FinTech;
Director, FynX Capital; Founder, PrestLoans).

🌐 **Live:** https://mittalakm.github.io/aviadi-website/
*(custom domain `www.aviadi.in` planned — see [DEPLOYMENT.md](DEPLOYMENT.md))*

## Sections

- **Hero** — positioning and call-to-action
- **About** — full professional profile, headshot, stats and current focus
- **Services** — financial advisory, advisor/board roles, NBFC & fintech guidance,
  startup mentoring, MSME financing
- **Recognition** — author, speaker, awards, and photos with national figures
- **Contact** — email, phone, LinkedIn

## Files

- `index.html` — the page content
- `styles.css` — all styling (colours via CSS variables in `:root`)
- `images/` — headshot and award photos

## Theme

Dark **Mustard & Charcoal**: warm charcoal backgrounds with a mustard-gold accent
(`#e6b73e`). All colours flow through the CSS variables at the top of `styles.css`,
so the theme can be changed by editing those values (plus the `.hero` gradient).

## Viewing locally

Open `index.html` directly in a web browser, or serve the folder with any static
file server and visit the printed URL, e.g.:

```bash
npx serve .
```

## Deploying

Hosted on **GitHub Pages** from the `main` branch. Any change merged to `main`
redeploys automatically within a minute or two. See [DEPLOYMENT.md](DEPLOYMENT.md)
for full details and the custom-domain setup.
