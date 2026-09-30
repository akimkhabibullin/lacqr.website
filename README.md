# Lacqr public website

This is a dependency-free static website intended for Lacqr's public legal and support pages. It can use a free Vercel-provided `*.vercel.app` address until Lacqr needs a custom domain.

## Pages

- `/` — landing page
- `/privacy/` — App Store privacy-policy URL (generated)
- `/terms/` — Terms of Use (generated)
- `/support/` — App Store support URL
- `/legal/` — legal index

`privacy/` and `terms/` are generated from `src/laqr/legal.ts` so the app and the
site never disagree. After editing `legal.ts`, run `npm run build:legal` and
redeploy.

## Local preview

From the repository root:

```bash
python3 -m http.server 4173 --directory website
```

Then open `http://localhost:4173`.

## Deploy with Vercel

1. Sign in to Vercel using the GitHub account that owns the website repository.
2. Select **Add New → Project**.
3. Import the `lacqr-website` repository.
4. Choose the **Hobby** plan only. Do not start a Pro trial or enter payment information if the goal is a zero-cost deployment.
5. Leave **Framework Preset** as `Other`.
6. If the repository contains these files at its top level, leave **Root Directory** unchanged. If the repository contains a surrounding `website` folder, set Root Directory to `website`.
7. Do not add a build command, output directory, or environment variables.
8. Select **Deploy**.
9. Vercel will assign a production address based on the project name, ending in `.vercel.app`. Copy the exact address shown in the project dashboard; do not guess it.

Every push to the production branch will create a new production deployment. Other branches receive preview deployments.

Vercel Hobby is currently $0 but is limited by Vercel's terms to personal and non-commercial use. If Lacqr becomes commercial or exceeds Hobby limits, move this dependency-free site to another static host or upgrade intentionally. Hobby projects are paused rather than automatically billed when included usage is exhausted.

## Production deployment

The production address is `https://lacqr-website.vercel.app`. Enter
`/privacy/` as the App Store privacy-policy URL and `/support/` as the support
URL. Open each in a private browser window to confirm before submitting.

Keep `lacqr.app@gmail.com` monitored; it's the only contact listed.

## Before publishing

- Have the privacy policy and terms reviewed by someone qualified.
- Whenever Lacqr's data practices change, update `src/laqr/legal.ts`, rebuild
  these pages, the iOS privacy manifest in `app.json`, and the App Store
  Connect privacy answers together.
