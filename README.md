# Groundworks Command — Legal Pages

Static HTML legal pages hosted on GitHub Pages so they have stable public URLs
for Intuit's QuickBooks app approval (and any future integrations that require
a privacy policy / EULA on file).

## Pages

- `index.html` — Landing page with links
- `privacy.html` — Privacy Policy
- `terms.html` — End-User License Agreement (Terms of Service)

## Final URLs

Served from `legal.groundworkcommand.com` via GitHub Pages + Wix DNS CNAME:

- Privacy Policy: `https://legal.groundworkcommand.com/privacy.html`
- EULA / ToS:    `https://legal.groundworkcommand.com/terms.html`

The `CNAME` file in this repo tells GitHub Pages to serve under this custom domain.

## Push to GitHub (one-time setup)

```bash
cd "/Applications/groundworks-legal-pages"
git init
git add .
git commit -m "Initial legal pages"

# Create a new repo on github.com named, e.g., "groundworks-legal" (public),
# then:

git remote add origin git@github.com:<your-github-username>/groundworks-legal.git
git branch -M main
git push -u origin main
```

## Enable GitHub Pages

1. Go to the repo on GitHub → **Settings** → **Pages** (left sidebar).
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Pick **Branch: main**, **Folder: / (root)**, and click **Save**.
4. Wait ~1 minute. Refresh the Pages settings page; you should see a green
   banner that says "Your site is live at https://<username>.github.io/groundworks-legal/".
5. Open both `/privacy.html` and `/terms.html` in a browser to confirm they
   load over HTTPS. Paste those URLs into the Intuit form.

## Updating later

Edit the HTML files, commit, push. Pages will rebuild automatically within a
minute or two.

## Notes for the future

- These templates are reasonable starting points for an internal-use platform
  with QBO + ServiceTitan + Stripe + Twilio integrations. If Groundworks
  Command ever offers the platform externally as a SaaS product, have an
  attorney review and update them.
- The "Last Updated" date appears at the top of each policy. Bump it whenever
  you make a material change.
