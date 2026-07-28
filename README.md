# Lacqr public website

This is a dependency-free static website intended for Lacqr's public legal and support pages. It can use a free Vercel-provided `*.vercel.app` address until Lacqr needs a custom domain.

## Pages

- `/` — public landing page
- `/privacy/` — App Store privacy-policy URL
- `/terms/` — public Terms of Use
- `/support/` — App Store support URL and contact information
- `/delete-account/` — account-deletion instructions
- `/privacy-choices/` — App Store privacy-choices/data-rights URL
- `/upload-rules/` — user-facing content rules
- `/copyright/` — copyright reporting and counter-notice process
- `/security/` — public security and responsible-reporting page
- `/legal/` — legal and policy index

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

The verified production address is `https://lacqr-website.vercel.app`. Public release URLs are:

- `https://lacqr-website.vercel.app/privacy/`
- `https://lacqr-website.vercel.app/support/`
- `https://lacqr-website.vercel.app/terms/`
- `https://lacqr-website.vercel.app/delete-account/`
- `https://lacqr-website.vercel.app/privacy-choices/`
- `https://lacqr-website.vercel.app/upload-rules/`
- `https://lacqr-website.vercel.app/copyright/`
- `https://lacqr-website.vercel.app/security/`
- `https://lacqr-website.vercel.app/legal/`

Do not enter a guessed URL in App Store Connect. Open every final URL in a private browser window and verify that it returns the intended page over HTTPS.

The support, privacy, and security contact is `lacqr.app@gmail.com`. Keep the mailbox monitored, protect it with two-step verification, and update every public and in-app reference together if it changes.

## Before publishing

- Verify that `lacqr.app@gmail.com` receives mail and that replies are monitored.
- Have qualified counsel review the legal operator identity, governing law, age requirements, retention statement, and territory-specific terms.
- Remove the visible legal-review callout from `terms/index.html` only after that review is complete.
- Confirm that the public policy still exactly matches the production app and Supabase behavior.
- Test every link over HTTPS without being signed in.
- Enter `https://lacqr-website.vercel.app/privacy/` as the App Store privacy-policy URL.
- Enter `https://lacqr-website.vercel.app/support/` as the App Store support URL.

Whenever Lacqr's data practices change, update the app policy, this website, the iOS privacy manifest, and App Store Connect disclosures together.
