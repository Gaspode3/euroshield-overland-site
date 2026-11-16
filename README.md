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

## Brand colours

Defined once, as CSS variables at the top of the `<style>` block in both files
(`index.html`, `uk/index.html`):

| Colour | HEX | Use |
| --- | --- | --- |
| Olive Green | `#445500` | header, page headings, buttons, links |
| Orange | `#FF6600` | Donate / Apply buttons, active menu underline, accent line under page headings |
| White | `#FFFFFF` | cards, form fields |
| Military Desert Tan (FS 33446) | `#B7A47A` | page background (approximate digital value) |

Two derived shades are also used: a darker olive `#2c3600` (link text, so it
stays readable on tan) and a light tan tint `#d7cdb6` (alternate sections).
White text on orange is too low-contrast, so orange buttons use dark text.
The small shield in the header is a placeholder; replace it with the official
logo SVG.

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
2. **Donations** are received mostly by **ESO USA** (the US nonprofit; bank
   account and PayPal already exist). Replace the "[Donate online — Donorbox
   link]" and PayPal buttons with real links, and fill in ESO USA's bank details.
   The PrivatBank accounts (UAH, EUR, maybe USD) sit in a separate, smaller
   "Donating from Ukraine" block. No crypto. ESO USA's 501(c)(3) status is
   **pending IRS approval** (effective date 30 Sep 2026): the Receipts text
   must not claim tax-deductibility until it is approved. Financial matters are
   handled by ESO USA's treasurer.
3. **Merchandise** is print-on-demand: the "Buy" buttons will link to a
   Printful / Printify / Fourthwall storefront, which handles checkout and
   shipping. Membership is **no longer sold in the shop**.
4. **Membership** has **2 tiers**. Members pay by making a donation of at least
   the tier minimum, and the board approves each member manually. Fill in the
   tier amounts on the Members only page.
5. **Members only** — members-only content lives in a **private Discord
   server** with one role per tier (Tier 1: behind-the-scenes media; Tier 2:
   also the live chat and the channel for questions for the videos). There is
   no login on the website: after a donation the board approves the member,
   sends a Discord invite and assigns the role. Set up the server and roles,
   and keep the invite link private. The special-service form on the page
   needs a form endpoint like the other forms.

## Previewing online (GitHub Pages)

Settings → Pages → Source: "Deploy from a branch" → Branch: `main` / root → Save.
The site will appear at `https://<owner>.github.io/euroshield-overland-site/`.
Note: GitHub Pages on a private repository requires a paid GitHub plan.
