# Golden Lion Sport Center — Website

A premium single-page website for Golden Lion Sport Center (Karate club).
Black & gold theme, bilingual (English / Arabic), with a cinematic preloader,
gold-dust particle hero, marquee ticker, scroll animations, 3D tilt effects,
an autoplay dojo video, a mobile menu, WhatsApp click-to-chat (the contact
form opens WhatsApp pre-filled), and social links.

## Structure

```
golden-lion-website/
├── index.html          ← the entire site, self-contained (open in any browser)
└── assets/
    ├── logo.png
    ├── about-achievement.jpg
    ├── team.jpg
    ├── kids.jpg
    ├── grading.jpg
    ├── video-poster.png
    └── dojo-intro.mp4
```

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

## Customizing contact details

Edit them directly in `index.html`:

- **WhatsApp**: search for `wa.me/97466718487` (appears in the floating
  button, the contact section, and the form-submit script) and replace the
  number (digits only, international format).
- **Social links**: the Facebook / YouTube / TikTok links are placeholders —
  search for `facebook.com`, `youtube.com`, `tiktok.com` in the footer.
- **Phone / email / address**: search for `+974 6671 8487`,
  `train@goldenlion.club`, and `Main Hall` in the contact section.

## Replacing photos / video

Drop your own files into `assets/` using the **same filenames**, or update the
`src=""` paths in `index.html`. Recommended: keep the dojo video vertical
(9:16) to match the framed player.

## Fonts

Fonts load from Google Fonts (Anton, Archivo, Manrope, Cairo) over the internet.
No setup required.
