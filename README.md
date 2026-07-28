# Lacqr public website

This is a dependency-free static website intended for Lacqr's public legal and support pages. It can use a free Vercel-provided `*.vercel.app` address until Lacqr needs a custom domain.

## Pages

- `/` — public landing page
- `/privacy/` — App Store privacy-policy URL
- `/terms/` — public Terms of Use
- `/support/` — App Store support URL and contact information
- `/delete-account/` — account-deletion instructions

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

## After the first deployment

Send the exact production `https://…vercel.app` address back to Codex. It must then replace the unreleased `lacqr.app` values in the app, About screen, App Store readiness document, and public-link references. The deployed privacy and support URLs should look like:

- `https://YOUR-ACTUAL-PROJECT.vercel.app/privacy/`
- `https://YOUR-ACTUAL-PROJECT.vercel.app/support/`
- `https://YOUR-ACTUAL-PROJECT.vercel.app/terms/`
- `https://YOUR-ACTUAL-PROJECT.vercel.app/delete-account/`

Do not enter a guessed URL in App Store Connect. Open every final URL in a private browser window and verify that it returns the intended page over HTTPS.

The support email is still `hello@lacqr.app`. That address will not work until the domain and email service exist. Before App Store submission, either activate it or replace it everywhere with a real monitored address that does not expose an unwanted personal address.

## Before publishing

- Verify that `hello@lacqr.app` receives mail.
- Have qualified counsel review the legal operator identity, governing law, age requirements, retention statement, and territory-specific terms.
- Remove the visible legal-review callout from `terms/index.html` only after that review is complete.
- Confirm that the public policy still exactly matches the production app and Supabase behavior.
- Test every link over HTTPS without being signed in.
- Enter the final Vercel `/privacy/` address as the App Store privacy-policy URL.
- Enter the final Vercel `/support/` address as the App Store support URL.

Whenever Lacqr's data practices change, update the app policy, this website, the iOS privacy manifest, and App Store Connect disclosures together.
