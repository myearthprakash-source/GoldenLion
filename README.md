# Golden Lion Sport Center — Website

A premium single-page website for Golden Lion Sport Center (Karate club).
Black & gold theme, bilingual (English / Arabic), with scroll animations,
3D tilt effects, an autoplay dojo video, WhatsApp click-to-chat, and social links.

## Structure

```
golden-lion-website/
├── index.html          ← the site (open directly in any browser)
├── support.js          ← runtime that powers index.html
└── assets/
    ├── logo.png
    ├── founder.jpg              ← Founder & Head Coach portrait (centerpiece)
    ├── founder-group.jpg        ← used in the About section
    ├── coaches-spar.jpg / founder-spar.jpg / founder-student.jpg   ← "Meet the senseis"
    ├── student-*.jpg            ← gallery (kid, blackbelt, jersey, kick, kata, red)
    ├── tournament1–9.jpg        ← "Built for the arena" (Karate1 Premier League)
    ├── video-poster.png
    ├── dojo-intro.mp4
    └── new asset/               ← original untouched uploads (large RAW/MP4 — not used by the site)
```

## Sections

Hero · About · **Founder & Head Coach** (centered feature built around `founder.jpg`) ·
Video · Programs · Meet the Senseis · Gallery · **Built for the Arena** (competition) ·
**Pro Shop** (gear & dress for sale) · Schedule · Contact.

It is a **static site** — no build step, no dependencies to install.

## Run locally

Just open `index.html` in a browser, or serve the folder:

```bash
npx serve .
# or
python3 -m http.server 8000
```

## Deploy to Vercel (via Git)

1. Create a new Git repo and push this folder's contents to it:
   ```bash
   git init
   git add .
   git commit -m "Golden Lion Sport Center website"
   git branch -M main
   git remote add origin <your-repo-url>
   git push -u origin main
   ```
2. Go to https://vercel.com → **Add New… → Project** → import your repo.
3. Framework Preset: **Other**. Leave Build Command empty and Output Directory
   as the project root. (Vercel serves `index.html` automatically.)
4. Click **Deploy**. Done.

> If you push this `golden-lion-website` folder as a subfolder of your repo,
> set Vercel's **Root Directory** to `golden-lion-website` in project settings.

### Or deploy without Git

```bash
npm i -g vercel
cd golden-lion-website
vercel
```

## The Pro Shop (`#shop`)

Nine products — gi & uniforms, sparring gear, belts and club apparel — plus a
discounted starter bundle. Each product is drawn as inline gold line-art SVG,
so the section needs **no product photography** to look finished.

- **Prices / copy / sizes**: edit the `<article class="gl-shop-card">` blocks
  directly in `index.html` (search for `PRO SHOP`).
- **Ordering**: every `ORDER →` button becomes a WhatsApp deep-link at runtime,
  pre-filled with that product's name and price. The message is built in
  `componentDidMount` from the card's `data-order-name` / `data-order-price`
  attributes and the `whatsappNumber` prop — so adding a product only means
  copying a card and setting those two attributes.
- **Category filter**: the chips filter on each card's `data-cat`
  (`uniform` · `sparring` · `belts` · `apparel`). Add a category by adding a
  chip with a matching `data-cat`.
- **Adding real photos later**: swap the `<svg class="gl-shop-art">` for an
  `<img>` with the same class and `aspect-ratio:4/3` — the hover zoom and
  sheen keep working.

## Customizing contact details

The WhatsApp number/message and the Instagram / Facebook / YouTube / TikTok
links currently use placeholders. Edit them directly in `index.html`:

- **WhatsApp**: search for `whatsappNumber` and `whatsappMessage` defaults
  (digits only, international format, e.g. `971501234567`).
- **Social links**: search for `instagramUrl`, `facebookUrl`, `youtubeUrl`,
  `tiktokUrl` and replace the placeholder URLs.
- **Phone / email / address**: search for `+971 50 123 4567`,
  `train@goldenlion.club`, and `Main Hall` in the contact section.

## Replacing photos / video

Drop your own files into `assets/` using the **same filenames**, or update the
`src=""` paths in `index.html`. Recommended: keep the dojo video vertical
(9:16) to match the framed player.

## Fonts

Brand fonts — **Myriad Pro** (English) and **GE Dinar One** (Arabic). Both are
licensed fonts, so they are *self-hosted*: drop the files into `assets/fonts/`
using the names in that folder's `README.txt` and they activate automatically.

Until the licensed files are added, the site falls back to the closest free
web fonts loaded from Google Fonts — **Source Sans 3** (a near-identical open
Myriad Pro cousin) and **Cairo** for Arabic — so it already looks correct.

Font stacks are defined once as CSS variables (`--gl-en`, `--gl-display`,
`--gl-ar`) in the top `<style>` block of `index.html`.
