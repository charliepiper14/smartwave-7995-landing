# Smart Wave Solar: $7,995 landing page mockup

A high-converting landing page mockup for the Smart Wave Solar $7,995 offer, built by Heath Media.

It's a single self-contained file (`index.html`). The logo and award artwork are embedded, so there are no other assets to upload. Fonts load from Google Fonts.

## What's in the repo

```
smartwave-7995-landing/
├── index.html     The landing page
├── README.md      This file
├── .nojekyll      Tells GitHub Pages to serve the file as-is
└── .gitignore
```

## Put it on GitHub

```bash
cd smartwave-7995-landing
git init
git add .
git commit -m "Smart Wave Solar $7,995 landing page mockup"
git branch -M main
git remote add origin https://github.com/YOUR-ACCOUNT/smartwave-7995-landing.git
git push -u origin main
```

## Publish it with GitHub Pages

1. In the repo on GitHub, go to **Settings > Pages**.
2. Under **Build and deployment**, set Source to **Deploy from a branch**.
3. Choose branch **main** and folder **/ (root)**, then **Save**.
4. After a minute or two the page is live at `https://YOUR-ACCOUNT.github.io/smartwave-7995-landing/`.

To use a custom domain (for example `offer.smartwavesolar.com`), add it under **Settings > Pages > Custom domain** and point a CNAME record at `YOUR-ACCOUNT.github.io`.

## Preview locally

Open `index.html` in a browser, or run a quick local server:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## The mockup controls

The dark bar at the top is for review only. It lets you:

- show and hide the CRO notes explaining each section
- switch between **Version A** (standard) and **Version B** (pricing table test)

Remove the `<div class="demo">` block, the `.note` blocks and the Version B section before the page goes live.

## Before going live

- **Form submission.** The form is a working front end only. Nothing is sent. Connect the contact step to the CRM (NetSuite) or a form handler, and the booking step to the real calendar.
- **Tracking.** The page pushes these events to `window.dataLayer`, ready for Google Tag Manager:

  | Event | When it fires |
  |---|---|
  | `lp_step_complete` | Each form step is completed (`step`, `step_key`) |
  | `lp_lead` | Contact details submitted. Map this to the Meta Lead event, with Conversions API and deduplication |
  | `lp_disqualified` | Renter or mobile home screened out |
  | `lp_call_booked` | Call booked or "just call me" chosen. Map this to the Meta Schedule event |

  Add the GTM container snippet to the `<head>` and top of `<body>`.
- **Content to confirm with Smart Wave:** the phone number (currently the print ad number), 5,000+ installations, Inc. 5000, "No door knocking", real install photos for the grey photo areas, and Version B prices if that test runs.
- **Compliance:** keep the savings disclaimer, the promotional pricing note and the SMS consent text on the contact step.
