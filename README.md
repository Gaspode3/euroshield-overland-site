# EuroShield Overland — website draft

A working draft of the new EuroShield Overland website: a homepage plus 10 pages
(Who we are, What we do, Sponsors, Testimonials, How to donate, How to apply,
Merchandise, Members only, Associate links, Contact us). Sponsors and
Testimonials are hidden at launch (see below). Everything below applies to both language versions.

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
- **Links:** buttons and links marked `href="#"` (donate, shop, social media,
  associates) need real addresses.

## Hidden pages: Sponsors and Testimonials

There is no content for these pages yet, so they are removed from the header
menu, the homepage "Explore" tiles and the footer. Their
`<div class="page" id="sponsors">` and `<div class="page" id="testimonials">`
sections are still in `index.html`, each marked with the comment
"Hidden until there is content — add links back to nav/tiles/footer".

To bring a page back, add its link in three places:

1. Header menu: `<li><a href="#sponsors">Sponsors</a></li>`
2. Homepage tiles: `<a href="#sponsors">Sponsors<small>Who backs us</small></a>`
   (with 10 tiles, switch `.tiles` back to `repeat(5,1fr)` so the grid stays even)
3. Footer "About" list: `<li><a href="#sponsors">Sponsors</a></li>`

Do the same with `#testimonials` ("Letters from the road").

## Before going live

1. **Forms need an endpoint.** The site has three forms: How to apply
   (`data-form="apply"`), Contact us (`data-form="contact"`) and the members'
   special-service request (`data-form="special"`). There is no backend yet:
   each form has `action="#"` and, until that changes, shows
   "Form not connected yet (demo)" instead of sending. Set `action` to a form
   service URL (Formspree, Web3Forms, Netlify Forms, or the website builder's
   own forms). Look for the `FORM ENDPOINT` comments.
2. **Donations** go through **Donorbox**, run by the **US nonprofit**: replace
   the "[Donate online — Donorbox link]" button with the campaign link. Fill in
   the US and Ukrainian bank details and the tax-deductibility line on the
   Donate page. No crypto.
3. **Merchandise** is print-on-demand: the "Buy" buttons will link to a
   Printful / Printify / Fourthwall storefront, which handles checkout and
   shipping. Membership is **no longer sold in the shop**.
4. **Membership** has **2 tiers**. Members pay by making a donation of at least
   the tier minimum, and the board approves each member manually. Fill in the
   tier amounts on the Members only page.
5. **Members only** — the password (`member`) is a demo inside the page and is
   **not secure**. Real protection must come from the platform. The access
   method (Wix members area vs Discord roles) has not been decided yet.

## Previewing online (GitHub Pages)

Settings → Pages → Source: "Deploy from a branch" → Branch: `main` / root → Save.
The site will appear at `https://<owner>.github.io/euroshield-overland-site/`.
Note: GitHub Pages on a private repository requires a paid GitHub plan.
