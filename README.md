# InfiniPop — deploy notes

This folder is ready to push to GitHub and connect to Cloudflare. See the
chat for the full walkthrough; quick reference below.

## What's in here
- `index.html` — the whole site (HTML/CSS/JS, self-contained).
- `wrangler.jsonc` — tells Cloudflare "this is a static site, serve these
  files directly." No build step, no framework, nothing else needed.

## First deploy
1. Push this folder to a new GitHub repo (e.g. `infinipop`).
2. Cloudflare dashboard → **Workers & Pages** → **Create** →
   **Import a repository** → connect GitHub → pick the repo → Deploy.
3. You'll get a live URL like `infinipop.<yourname>.workers.dev` within a
   minute or two.

## Custom domain
Worker's page → **Domains & Routes** → **Add** → enter your domain.
(Domain needs to be using Cloudflare's nameservers first — add it under
**Websites** if it isn't already.)

## Future updates
Edit `index.html`, commit, push to GitHub — Cloudflare redeploys
automatically within a minute or two. No manual redeploy step.

## When AdSense approves the site
1. Add the AdSense `<script>` snippet to `<head>` in `index.html`.
2. Replace each `your ad here` placeholder `<div class="ad-slot">` with
   the matching `<ins class="adsbygoogle">` unit (sizes are noted in the
   HTML comment near the top of the file).
3. Add an `ads.txt` file at the root of this same folder with the line
   AdSense gives you, commit, push.
