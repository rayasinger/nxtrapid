# NXT Rapid — Landing Site

Static one-page landing site for **NXT Rapid** (Digital Studio & Rapid Prototyping).

> `index.html` here is the working v1 prototype, used as a **swap-in placeholder**. When the Claude Design **v2** export is ready, replace `index.html` (and drop the logo into `assets/`) and push again — the deploy pipeline stays the same.

## Deploy to GitHub Pages — Option A (simplest, no CI)

From an empty local folder containing these files:

```bash
git init -b main
git add .
git commit -m "NXT Rapid landing site"
git remote add origin https://github.com/<YOUR-USER>/nxtrapid.git
git push -u origin main
```

Then on GitHub: **Settings → Pages → Build and deployment → Source: “Deploy from a branch” → Branch: `main` / `/ (root)` → Save.**
Your testable link appears within a minute or two at:
`https://<YOUR-USER>.github.io/nxtrapid/`

## Deploy to GitHub Pages — Option B (GitHub Actions, included)

This repo ships `.github/workflows/deploy.yml`. If you instead set **Settings → Pages → Source: “GitHub Actions”**, every push to `main` auto-builds and deploys. No branch selection needed.

## Swapping in the Claude Design v2 build

1. Export the design from Claude Design (or copy the compiled HTML).
2. Replace `index.html` with the v2 HTML.
3. Put referenced assets in `assets/` (e.g. `assets/nxt-rapid-logo.png`) and confirm the paths in the HTML are relative (`assets/...`, not absolute).
4. If the design relies on `support.js`, include it alongside and keep the `<script src="support.js">` reference relative.
5. Commit and push — Pages redeploys automatically.

## Notes
- `.nojekyll` is included so GitHub Pages serves files as-is (no Jekyll processing).
- The site is fully static — no build step, no server, no environment variables.
- Custom domain later: add a `CNAME` file with `nxtrapid.com` and point DNS at GitHub Pages.
