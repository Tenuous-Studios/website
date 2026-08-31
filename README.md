# tenuousstudios.com

Static site for Tenuous Studios. Plain HTML/CSS/JS — no build step, no
dependencies, no external requests.

## Layout

```
index.html      the whole site
CNAME           custom domain for GitHub Pages
images/         logos and screenshots (webp + jpg fallback)
```

## Deploying

Hosted on GitHub Pages, domain stays registered at Porkbun.

1. Push this repo to the Tenuous Studios GitHub org.
2. Settings → Pages → Source: **Deploy from a branch**, `main` / `/ (root)`.
3. Settings → Pages → Custom domain: `www.tenuousstudios.com`.
4. Tick **Enforce HTTPS** once the certificate issues (can take up to an hour).

### DNS at Porkbun

Remove the records pointing at Porkbun's website builder first, then add:

| Type  | Host  | Answer                  |
|-------|-------|-------------------------|
| CNAME | www   | `ORGNAME.github.io`     |
| A     | (apex)| `185.199.108.153`       |
| A     | (apex)| `185.199.109.153`       |
| A     | (apex)| `185.199.110.153`       |
| A     | (apex)| `185.199.111.153`       |

All four A records are needed — they're a load-balanced set, not alternatives.

Verify the domain under GitHub org Settings → Pages → Verified domains
*before* attaching it, so nobody else can claim it later.

## Adding a screenshot

1. Export at 1600px wide. Save both `.webp` and `.jpg` into `images/`.
2. Copy a `<figure class="slide">` block in `index.html`, swap the filenames,
   `alt` text, and `data-caption`.

That's it — the carousel dots and controls are generated from whatever slides
are present.

## Still to fill in

Search `index.html` for `TODO`:

- real contact email addresses
- real social profile URLs (currently placeholders)
- founding year in the press-kit fact sheet
- press-kit asset zips
