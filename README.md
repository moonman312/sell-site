# Sell A Hotel

Audience-specific landing site for **sellahotel.us**, bundling the Hotel Capital Stack diagnostic. Static — no build step.

## Files
- index.html — the landing page
- diagnostic.html — bundled copy of the diagnostic tool (self-contained)
- vercel.json — static config + security headers

## Contact form
The form posts to a Google Apps Script that logs each lead to the "MHS — Website Leads" Google Sheet
and emails you. One script URL is shared by all six sites. Set it once: see
`landing/SETUP-contact-form.md`, then replace `REPLACE_WITH_YOUR_APPS_SCRIPT_URL` in index.html
(or in landing/build.js, then rebuild) with your deployed Web-app URL.

## Deploy (run from this folder)
```bash
git init && git add . && git commit -m "Sell A Hotel site"
git branch -M main
gh repo create moonman312/sell-site --public --source=. --remote=origin --push
vercel && vercel --prod
```

## Domains for this project (add in Vercel → Settings → Domains)
- Primary: **sellahotel.us**
- sellahotel.us → set to **Redirect to** sellahotel.us
- hotel-selling.com → set to **Redirect to** sellahotel.us

Point each domain's nameservers (GoDaddy) to Vercel, or add an apex A record `@ -> 76.76.21.21`.
