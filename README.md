# EuroShield Overland — website draft

A working draft of the new EuroShield Overland website: a homepage plus 10 pages
(Who we are, What we do, Sponsors, Testimonials, How to donate, How to apply,
Merchandise, Members only, Associate links, Contact us).

The English version is `index.html`, the Ukrainian version is `uk/index.html`;
the EN / UA button in the menu switches between them. Open either file in any
browser to view it — no installation needed. When you change content, update
both files.

## How to fill in the content

- **Text:** everything in `[square brackets]` is a placeholder. Replace it with
  your own text.
- **Photos:** put images into the `media/` folder. Each placeholder looks like
  `<div class="ph"><span>Photo: campfire</span></div>` — replace it with
  `<img class="ph" src="media/campfire.jpg" alt="Campfire at camp">`.
- **Homepage video:** add a short muted clip (10–20 seconds, under ~10 MB) as
  `media/hero.mp4`. Until then a dark background is shown instead.
- **Links:** buttons and links marked `href="#"` (donate, registration form,
  sponsors, social media) need real addresses.

## Before going live

1. **Members only** — the password (`member`) is a demo inside the page and is
   **not secure**. Real protection must come from the hosting / website builder
   (for example Squarespace or Wix member pages, or server-side auth).
2. **Shop** — the "Buy" buttons need a real checkout: Shopify Buy Button, Stripe
   Payment Links, or the website builder's own store.
3. **Donations** — add real payment links and bank details on the Donate page.

## Previewing online (GitHub Pages)

Settings → Pages → Source: "Deploy from a branch" → Branch: `main` / root → Save.
The site will appear at `https://<owner>.github.io/euroshield-overland-site/`.
Note: GitHub Pages on a private repository requires a paid GitHub plan.
