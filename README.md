# Translation Compare – Deploy on Render

This folder is ready to deploy as a **Static Site** on [Render](https://render.com).

## Files
- `index.html` – the app (single file)
- `render.yaml` – optional Blueprint to auto-create the Static Site
- *(optional)* add `favicon.ico`, `404.html` as needed

## Option A — Fastest (Dashboard: Static Site)
1) Push these files to a new GitHub repo (root).  
2) In Render Dashboard: **New → Static Site**.  
3) Connect the repo, choose your branch.  
4) **Build Command:** *(leave empty)*  
5) **Publish Directory:** `.`  
6) Add env var (optional but recommended): `SKIP_INSTALL_DEPS=true`  
7) Click **Create Static Site**.

Your site will be served from `https://<name>.onrender.com` with free CDN & TLS. On every push, a new deploy runs.

## Option B — Blueprint (IaC)
Commit `render.yaml`, then in Render Dashboard: **New → Blueprint** and select the repo.
The blueprint includes:
- `runtime: static`
- `staticPublishPath: .`
- `headers` example for `Cache-Control` on `index.html`

## Notes
- If you put assets in a subfolder (e.g. `/assets`), just commit them—they're deployed too.
- You can configure more headers in the dashboard or in `render.yaml`.
- To add a custom domain: Render → your site → **Settings → Custom Domains**.

Enjoy!
