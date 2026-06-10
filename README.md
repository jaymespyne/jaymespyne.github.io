# jaymespyne.com

Static personal academic site: home, about, publications, and an embedded CV.
Plain HTML/CSS, no build step. Hosted on GitHub Pages.

## Files

- `index.html` — landing page
- `about.html` — bio
- `publications.html` — publication list
- `media.html` — "In the Media" coverage + op-eds
- `cv.html` — embeds `cv.pdf`
- `cv.pdf` — your CV (already included; replace this file to update it)
- `style.css` — shared styles
- `favicon.svg` — browser-tab icon (oxblood "jp" monogram)
- `robots.txt`, `sitemap.xml` — search-engine hints
- `CNAME` — custom domain config (`www.jaymespyne.com`)

## Editing

Everything is plain text. Open any `.html` file, change the words, save.
No tooling required. To preview locally, just double-click `index.html`.

## Update your CV

The CV page embeds `cv.pdf` automatically. To replace it, upload a new
`cv.pdf` (exact name) over the old one. If your sitemap or publication list
changes, edit `publications.html` / `media.html` by hand the same way.

---

# Deploying to GitHub Pages + pointing your domain

You drive the clicks; this is the exact sequence.

## 1. Create the repo

1. Go to https://github.com/new
2. Repository name: `jaymespyne.github.io` is simplest (any name works, but this
   one serves at your username root). Set it **Public**.
3. Create the repository.

## 2. Upload these files

1. On the new repo page, click **uploading an existing file**.
2. Drag in **every** file from this folder: all the `.html` files
   (`index`, `about`, `publications`, `media`, `cv`), `style.css`,
   `favicon.svg`, `robots.txt`, `sitemap.xml`, `CNAME`, and `cv.pdf`.
3. Commit.

## 3. Turn on Pages

1. Repo **Settings** → **Pages** (left sidebar).
2. Under **Build and deployment**, Source = **Deploy from a branch**.
3. Branch = `main`, folder = `/ (root)`. Save.
4. Wait ~1 minute; the site goes live at `https://<username>.github.io`.

## 4. Point jaymespyne.com at GitHub (yes, this works)

GitHub Pages supports custom domains with free HTTPS. You set DNS records at
your **domain registrar** (where you bought jaymespyne.com — likely Wix, since
the site is on Wix now, or wherever the domain itself is registered).

> Important: if the **domain** is registered through Wix, you may need to either
> transfer the domain out or use Wix's DNS settings. The site content moves to
> GitHub regardless; only the DNS records need to point at GitHub.

### A. At your registrar's DNS settings, add:

For the apex `jaymespyne.com`, four **A** records pointing at GitHub:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

For `www`, one **CNAME** record:

```
www  →  <username>.github.io
```

(Replace `<username>` with your GitHub username.)

### B. Back in GitHub → Settings → Pages → Custom domain:

1. Enter `www.jaymespyne.com` and Save. (The `CNAME` file already does this, but
   confirm it shows here.)
2. Wait for the DNS check to pass (can take minutes to a few hours).
3. Tick **Enforce HTTPS** once it becomes available.

That's it — `https://www.jaymespyne.com` now serves the GitHub site.

## Notes / cautions

- DNS changes can take up to 24–48 hours to fully propagate.
- Don't delete the Wix site until the GitHub version is confirmed live on the
  domain, so you always have a fallback.
- I can't create the GitHub repo or change DNS for you — those require your
  login and registrar access — but I can walk you through any step live.
