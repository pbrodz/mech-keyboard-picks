# Keywell &amp; Co. — Ergonomic Mechanical Keyboards for Programmers

A static niche comparison site: current top picks + a blog, built to test whether
a focused site can earn Google traffic. Pure HTML/CSS, no build step, hosted on
GitHub Pages.

## Pushing to GitHub Pages

1. Create an empty repo on GitHub (e.g. `mech-keyboard-picks`).
2. Push this directory's contents to the repo's `main` branch.
3. In the repo: **Settings → Pages → Deploy from a branch → `main` / `/ (root)`**.
4. Point your Porkbun domain at GitHub Pages:
   - Add a `CNAME` DNS record for your subdomain (e.g. `keyboards`) → `<your-github-username>.github.io`
   - Or `A` records for an apex domain (see GitHub's Pages docs for current IPs).
   - Replace the placeholder in the `CNAME` file at the repo root with your real
     domain, and replace `REPLACE-WITH-YOUR-DOMAIN` in `sitemap.xml` and `robots.txt`.
5. In **Settings → Pages**, add the custom domain and enforce HTTPS.

Every push to `main` redeploys automatically (usually within a minute or two).

## Adding a new blog post

1. Copy `blog/quiet-switches-office.html` to `blog/your-new-post.html`.
2. Update the `<title>`, meta description, `<h1>`, and `<time>` date.
3. Write the post. Keep the `disclaimer` box if you mention prices/specs.
4. Add it to the top of the list in `blog/index.html` **and** on the homepage
   (`index.html`, "From the Blog" section).
5. Add its URL to `sitemap.xml`.
6. Commit and push. Done.

Target one real search-style keyword per post in the title/H1
(e.g. "glove80 vs moonlander", "best tenting kit for split keyboard").

## Updating the top picks

- Edit the pick cards and the comparison table in `index.html`.
- Bump the "Last updated" date chip at the top of the page.
- If a pick is replaced, say so in a short blog post — Google likes fresh content,
  and readers like honesty.

## Enabling Cloudflare Web Analytics (private visitor counts)

1. Sign up at cloudflare.com → Web Analytics → add your site.
2. Copy your beacon token.
3. In every HTML file, find the commented-out snippet near `</body>`:
   `<!-- Cloudflare Web Analytics: paste your Cloudflare beacon token here -->`
   Uncomment it and replace `PASTE-YOUR-TOKEN-HERE` with your token.
4. Push. Visits appear in your private Cloudflare dashboard — nothing visible on the site.

## Google Search Console (the real traffic scoreboard)

1. Go to search.google.com/search-console, add your domain, verify ownership
   (DNS TXT record via Porkbun is simplest).
2. Submit `https://YOUR-DOMAIN/sitemap.xml` under Sitemaps.
3. After a few days you'll see real data: what people searched, impressions, clicks.

## File map

- `index.html` — homepage: top picks + comparison table + latest posts
- `about.html` — about page
- `blog/index.html` — blog listing
- `blog/*.html` — individual posts
- `styles.css` — the whole design (paper/forest-green theme)
- `sitemap.xml`, `robots.txt`, `CNAME` — SEO + Pages plumbing
