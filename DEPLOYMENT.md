# Deployment

## Current setup

- **Host:** GitHub Pages
- **Source:** `main` branch, root (`/`)
- **Live URL:** https://mittalakm.github.io/aviadi-website/
- **Auto-deploy:** every push/merge to `main` rebuilds and redeploys automatically
  (usually live within 1–2 minutes).
- **Repository visibility:** public (required for free GitHub Pages).

## Custom domain — www.aviadi.in (planned, not yet connected)

As of this writing the site is **only** live at the `github.io` URL above.
`www.aviadi.in` is **not** connected yet.

### Key fact: where aviadi.in DNS is managed

`aviadi.in` uses custom nameservers **`ns1.aviadi.in` / `ns2.aviadi.in`**, served by
**`securehostdns.com`** (the existing hosting provider; the domain currently points
to `195.250.21.147`). This means DNS is **NOT** managed in GoDaddy's DNS panel even
if the domain is registered at GoDaddy — records must be changed at the
authoritative DNS host (securehostdns.com / the current web host), **or** the
nameservers must first be switched to GoDaddy.

### Step 1 — DNS records to add (at the authoritative DNS host)

| Type  | Name / Host | Value                |
|-------|-------------|----------------------|
| CNAME | `www`       | `mittalakm.github.io`|
| A     | `@` (apex)  | `185.199.108.153`    |
| A     | `@` (apex)  | `185.199.109.153`    |
| A     | `@` (apex)  | `185.199.110.153`    |
| A     | `@` (apex)  | `185.199.111.153`    |

Also **remove** the old `www` and `@` records pointing to `195.250.21.147`.

> Caution: pointing aviadi.in at GitHub means any existing site on
> `195.250.21.147` stops serving for this domain. If aviadi.in has email (MX) or
> other DNS records, leave those untouched — only change the `www`/`@` web records.

### Step 2 — GitHub side (do this AFTER DNS points to GitHub)

Setting the custom domain makes the `github.io` URL redirect to it, so only do this
once DNS resolves to GitHub (otherwise the site is briefly unreachable on both URLs).

1. Repo → **Settings → Pages → Custom domain** → enter `www.aviadi.in` → Save
   (this commits a `CNAME` file to the repo root).
2. Wait for GitHub's DNS check to pass, then tick **Enforce HTTPS** (the TLS
   certificate is issued automatically).
3. Verify the site loads at https://www.aviadi.in.

## Reverting to private

To take the site offline / make the repo private again: Settings → Pages → unpublish,
and Settings → General → Danger Zone → Change visibility → Private. (GitHub Pages on a
private repo requires a paid plan.)
