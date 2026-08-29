# Madam Studio — madamstudio site

The public site for Madam Studio: a static one-pager with a sliding
"studio feed" showcasing work. Hosted on GitHub Pages, no backend, no
build step — edit HTML, commit, done.

## Adding a post to the feed

1. Drop the image into `img/`.
2. Open `index.html`, find `const FEED = [` (it has a how-to comment
   right above it), and add a new block at the **top** of the list:

   ```js
   { img: "img/your-picture.png",
     alt: "what's in the picture, for screen readers",
     date: "2026-09-14",
     title: "Short headline",
     note: "One or two lines about the piece." },
   ```

3. Commit. GitHub Pages redeploys on its own within a minute or two.

## Custom domain

When the domain is pointed here, put it (just the bare hostname, one
line) in a `CNAME` file at the repo root, and add these DNS records at
the registrar:

- `A` records for the apex: `185.199.108.153`, `185.199.109.153`,
  `185.199.110.153`, `185.199.111.153`
- `CNAME` record for `www` → `emailbottles-boop.github.io`

Then in the repo's Settings → Pages, enter the domain and turn on
**Enforce HTTPS** once the certificate is issued.
