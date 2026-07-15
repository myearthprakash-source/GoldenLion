GOLDEN LION — SELF-HOSTED BRAND FONTS
=====================================

The site is wired to use the licensed brand fonts as soon as you drop the
files into THIS folder (assets/fonts/). Until then it automatically falls back
to the closest free web fonts — Source Sans 3 (for Myriad Pro) and Cairo
(for GE Dinar One) — so the design already looks correct.

Drop these files here (woff2 preferred; .otf also works). Use these EXACT names:

  English — Myriad Pro
    MyriadPro-Regular.woff2   (or .otf)   -> weight 400
    MyriadPro-Semibold.woff2  (or .otf)   -> weight 600
    MyriadPro-Bold.woff2      (or .otf)   -> weight 700
    MyriadPro-Black.woff2     (or .otf)   -> weights 800–900 (headlines)

  Arabic — GE Dinar One
    GEDinarOne-Medium.woff2   (or .otf)   -> weights 400–600
    GEDinarOne-Bold.woff2     (or .otf)   -> weights 700–900

Tips
----
- .woff2 loads fastest on the web. To convert an .otf/.ttf to .woff2, use
  https://cloudconvert.com/ttf-to-woff2 (or fonttools: `pip install fonttools brotli`,
  then `fonttools ttLib.woff2 compress Font.otf`).
- You don't need every weight — any file you add takes over from the fallback
  for its weight; missing weights keep using Source Sans 3 / Cairo.
- No code change is needed after adding files. The @font-face rules live in
  index.html (top <style> block).
- Make sure you have a licence to embed Myriad Pro / GE Dinar One on a website.
