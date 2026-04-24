# snuggles-legal

Static HTML for the Snuggles Privacy Policy and SMS Terms pages, hosted on GitHub Pages at `snuggles.fussion.app`.

## Live URLs

- https://snuggles.fussion.app/privacy/
- https://snuggles.fussion.app/terms/

## Files

- `CNAME` — GitHub Pages custom-domain marker (do not delete).
- `style.css` — shared styles for both pages.
- `index.html` — landing page with links to Privacy and Terms.
- `privacy/index.html` — full Privacy Policy (includes the SMS Terms section at the bottom with anchor `#sms-terms`).
- `terms/index.html` — standalone SMS Terms page.

Both pages are plain HTML with no build step. Edit the `.html` files directly; they go live after `git push`.

## One-time setup (do this once)

1. **Create a public GitHub repo** named `snuggles-legal` under the GitHub account/org you want (e.g., `fussionapps/snuggles-legal`).
2. From this directory:
   ```
   git init
   git add .
   git commit -m "Initial privacy + SMS terms pages"
   git branch -M main
   git remote add origin git@github.com:<OWNER>/snuggles-legal.git
   git push -u origin main
   ```
3. **Enable GitHub Pages**: repo &rarr; Settings &rarr; Pages &rarr; Source: `Deploy from a branch`, Branch: `main`, Folder: `/` (root). Save.
4. **Add the custom domain in GitHub Pages**: same Pages page &rarr; Custom domain &rarr; enter `snuggles.fussion.app` &rarr; Save. (The `CNAME` file is already in the repo, so this just confirms it.)
5. **Add the DNS record in Squarespace**: Domains &rarr; `fussion.app` &rarr; DNS &rarr; Add record:
   - **Type:** `CNAME`
   - **Host:** `snuggles`
   - **Data:** `<OWNER>.github.io`  (e.g., `fussionapps.github.io` &mdash; no `/snuggles-legal` suffix)
6. Wait a few minutes for DNS. Then in GitHub Pages settings, tick **Enforce HTTPS** once the cert shows as provisioned (can take up to an hour).
7. Visit https://snuggles.fussion.app/privacy/ and https://snuggles.fussion.app/terms/ in an incognito window to confirm they load with a green padlock.

## Updating the policy

1. Edit the relevant `.html` file.
2. Update the **Last updated** date in the `<div class="updated">` element.
3. `git commit -am "Update privacy policy — <summary>"` and `git push`.
4. Changes are live within ~1 minute.
