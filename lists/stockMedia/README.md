# stockMedia

**Purpose:** block stock photo, stock vector and stock video/footage sites, their brand-owned country TLDs and image CDNs.

**Entries:** 326 (254 brand country-TLD/variant domains + 72 curated sites/CDNs); all re-checked live via DoH 2026-11-02.

## Sources
- Brand names from zrovihr/uBlockOrigin-Stock-Photo-Blocklist (`gen.py` brands/exact) — https://github.com/zrovihr/uBlockOrigin-Stock-Photo-Blocklist
- Free stock (unsplash, pexels, pixabay, videvo, mixkit, coverr, kaboompics, stocksnap, rawpixel, ...) and video stock (storyblocks/videoblocks, pond5, motionarray, videohive, artgrid, filmsupply, dissolve, videezy, ...) hand-curated, homepage titles checked.
- CDNs: as1/as2/t3/t4.ftcdn.net (Adobe Stock), ak.picdn.net + image.shutterstock.com, media.gettyimages.com, istockimg.com, images/plus.unsplash.com, images/videos.pexels.com, cdn.pixabay.com, images.pond5.com, st/static.depositphotos.com, c8.alamy.com, thumbs.dreamstime.com, previews.123rf.com, img.freepik.com, static.vecteezy.com.

## Country-TLD method
23 brands × 39 TLDs generated → DoH (476 live) → kept only if brand-owned: brand-protection DNS (MarkMonitor, CSC, Getty's own NS, phase8 [Alamy], trademarkarea [Dreamstime], EuroDNS [Can Stock]), same NS as the brand's .com, redirect to the brand, or matching brand homepage. Rejected same-name/parked sites, e.g. istockphoto.com.au, unsplash.fr, pixabay.org, superstock.com.au, stocksy.co.uk, storyblocks.org, gettyimages.hu/ro.

## Exclusions
adobe.com, canva.com, shopify.com (only burst.shopify.com), magnific (AI upscaler), reshot.com (retired), unsplash.it (picsum placeholder), foap/wirestock/picfair (contributor platforms), bigstock.com / stockio.com / lifeofvids.com (unverifiable).
Overlap with the AI list: creativefabrica.com, elements.envato.com.
