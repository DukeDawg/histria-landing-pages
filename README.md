# Histria Books — Email-Capture Landing Pages

Two self-contained, GitHub-Pages-ready landing pages for the Histria email-acquisition
campaign (see `../email-acquisition-campaign-plan-2026-06-11.md` and the FB ad package at
`../../ads/histria-books/forgotten-classics/it-girl-kit/conversion-lp-ads-2026-06-16.md`).

Both pages match the funnel in the plan: FB ad → landing page → email capture (MailerLite)
→ BookFunnel delivery → segmented drip. Each collects email + first name + the one
`What drew you in?` segmentation question so the list never becomes soup.

## The two pages

| File | Angle | Hook | Magnet |
|---|---|---|---|
| `it-girl-kit/index.html` | **Time-period** (Jazz Age / 1920s / Old Hollywood) | "Before influencers, there was 'It.'" — matches the live FB ad creative | The Original It Girl Kit (IT + Clara Bow — My Story) |
| `vintage-romance/index.html` | **Genre** (vintage romance + Regency mystery) | "Scandalous then. Delicious now." | Vintage Romance + Regency Mystery Sampler |

Pure HTML/CSS, no build step, no images required (Art Deco / romance styling is CSS-driven).
No real Clara Bow likeness is used — per the rights guardrail in the plan.

## Deploy to GitHub Pages

1. Push this `landing-pages/` folder (or copy it into a dedicated public repo).
2. Repo → Settings → Pages → deploy from branch, root.
3. URLs become `https://<user>.github.io/<repo>/it-girl-kit/` and `.../vintage-romance/`.
4. (Optional) point a Histria subdomain at it via CNAME.

## Before going LIVE — wiring checklist (placeholders are intentional)

Kurt still owes the MailerLite group structure and BookFunnel account (see plan blockers).
Until those exist, each form runs in **placeholder/demo mode**: it shows the thank-you state
so the page is fully demoable. Fill these three in both HTML files before running paid traffic:

1. **MailerLite** — replace `REPLACE_WITH_MAILERLITE_FORM_ACTION_URL` in the `<form data-ml-action="...">`
   with MailerLite's hosted-form POST URL, OR drop in MailerLite's official embed snippet.
   The hidden `source` field and the `interest` select already map to the plan's segmentation tags.
2. **BookFunnel** — set `BOOKFUNNEL_URL` in the inline `<script>` to the Kit/sampler delivery link.
   On submit the page redirects there; leave blank to use the built-in thank-you panel.
3. **Meta Pixel** — uncomment `fbq('init', 'YOUR_PIXEL_ID')` + `PageView` in `<head>` and set the
   Histria pixel ID. A `Lead` event already fires on submit for ad optimization.

## Segmentation tags emitted

`source` = `lp-it-girl-kit-period` or `lp-vintage-romance-genre`.
`interest` = one of: old-hollywood · forgotten-classics · vintage-romance · 1920s-style ·
historical-fiction · regency-mystery. Map these to MailerLite groups per the plan §5.

## Status

Internal draft for David's approval. Not sent to Kurt, not deployed, no live IDs wired.
Final book titles/covers on the genre page confirmed with Histria before launch.
