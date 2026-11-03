# Category list expansion — 2026-11-02 (America/Denver)

Four **separate** lists grown; nothing merged into the AI list. Same formats/headers as before (`domains.txt`, `hosts.txt` `0.0.0.0 host`, `adblock.txt` `||host^`, README; HaGeZi-style header with `Category:` + Homepage https://github.com/tbpatj/blocklists).

| Category | Old | New | Net new |
|---|---|---|---|
| gifs | 48 | **133** | +85 |
| linkSharing | 119 | **281** | +162 |
| stockMedia | 326 | **626** | +300 |
| fileSharing | 1040 | **1294** | +254 |
| fileSharing `domains-extended.txt` | 1073 | **1333** | +260 (254 main + 6 cloud drives) |

## Method
Candidates → normalize/dedupe against all four lists + existing exclude/dead files → Cloudflare DoH (A/AAAA) → homepage `<title>` + final-URL fetch (`build/title.py`) → manual review (parked / for-sale / DropCatch / casino / repurposed / off-topic dropped). Brand ccTLDs additionally needed brand ownership (MarkMonitor/CSC/brand NS via `build/ns.py`, redirect to brand, or brand homepage). Wildcard DNS checked for giphy/redgifs/tenor/klipy/ezgif/gifyu/coub/alamy/123rf/ftcdn/picdn/flaticon (none wildcard; depositphotos.com is wildcard, so only st2 was added). Cross-list overlap between the four: 0.

## Sources
- gifs: hand research (GIF sites/makers/keyboards, reaction-GIF sites, ES/DE/NL/RU/CN animated-GIF galleries, glitter-GIF sites), CDN/API hostnames of existing platforms.
- linkSharing: https://privatebin.info/directory/ (public root-path instances), web search for pastebin alternatives (nullpaste, voidpaste, cloakbin, droptext), hastebin forks, project pastebins, Telegraph mirrors, notepad/self-destructing note sites.
- stockMedia: neutraltone/awesome-stock-resources, 40-brand × 85-TLD generation with ownership check, known agency/CDN hostnames, regional agencies, PNG-cutout/clipart sites.
- fileSharing: public debrid hoster APIs (Real-Debrid, AllDebrid, Premiumize, TorBox — hoster entries only) + curated temp-upload/transfer/regional hosts.

## Notable new domains (samples)
- **gifs:** heypster.com, gifbox.me, coub.com, mrgif.com, reactiongifs.us, gifs.alphacoders.com, gifmania.com, animaatjes.nl, gifsanimados.org, gifki.org, soogif.com, fabiaoqing.com, glitter-graphics.com, blingee.com, picasion.com, gickr.com, gifntext.com, gifrun.com, gifcap.dev, onlinegiftools.com, media.tenor.co, api.klipy.com, i.redgifs.com, media.gifdb.com, i.imgflip.com, s1-s7.ezgif.com.
- **linkSharing:** graph.org, te.legra.ph, teletype.in, write.as, txti.es, privnote.com, nullpaste.org, cloakbin.com, anonpaste.org, pastebin.ca, paste.org, hst.sh, srcb.in, mclo.gs, notepad.pw, ctxt.io, 0bin.ch, 0g.gg, privatebin.is, zerobin.no, paste.dismail.de, bin.nixnet.services (+ ~100 public PrivateBin instances).
- **stockMedia:** wireimage.com, filmmagic.com, turbosquid.com, rexfeatures.com, flaticon.com, thenounproject.com, vectorstock.com, vexels.com, pngwing.com, cleanpng.com, pxhere.com, freestocks.org, motionelements.com, artlist.io, imago-images.com, westend61.de, panthermedia.net, photo-ac.com, 699pic.com, hellorf.com, lori.ru, media.istockphoto.com, ak0.picdn.net, cdn.shutterstock.com, plus ~124 more brand ccTLDs (shutterstock/getty/istock/thinkstock/envato/pond5/...).
- **fileSharing:** streamtape.*, mixdrop.*, doodstream.com, filemoon.sx, voe.sx, bunkr.*, cyberdrop.cr, clicknupload.* mirrors, katfile.*, hif.to mirrors, TeraBox mirrors, lanzoux.com, wenshushu.cn, firestorage.jp, 0x0.st, qu.ax, pomf.lain.la, transfer.it, send.tresorit.com, masv.io.

## Dropped / rejected counts
| Category | Candidates checked | NXDOMAIN | Live but rejected (parked / for-sale / casino / repurposed / off-topic / not public) | Added |
|---|---|---|---|---|
| gifs | 272 | 87 | 100 | 85 |
| linkSharing | 322 | 44 | 116 | 162 |
| stockMedia | 3,138 (279 curated + 2,859 generated brand×TLD) | 2,266 | 572 | 300 |
| fileSharing | 360 (272 debrid-derived + 88 curated) | 60 | 46 (incl. 21 parked/casino/for-sale) | 254 (+6 extended) |

Notable rejections: giphy.net (parked), gifs.fr (for sale), gifok.net (betting), dollzmania.com (slots), klipy.ai (unrelated); privatebin.de & paste.ws (for sale), pastehub.net (seized), textdrop.net (casino), company-internal PrivateBins; **agefotostock.com (now a parked `/lander`)**, avopix.com (poker), xstockvideo.com (casino), 123rf.my/123rf.id/pond5.my (casino clones), unrelated same-name panthermedia/masterfile/artlist ccTLDs; heroupload.com (toto), ifolder.com.ua/vidcloud.ru/xrfiles.ru (casinos), gofile.me (Synology), cowtransfer.com (now a design tool).

Unchanged known exclusions: paste.ly / ren.ly NXDOMAIN (rentry used), gify.com (broker), gfycat.com (dead), reshot.com (retired), unsplash.it (placeholder service).

## Files to publish (→ `lists/<category>/` in tbpatj/blocklists)
- `gifs/{domains,hosts,adblock}.txt`, `gifs/README.md`
- `linkSharing/{domains,hosts,adblock}.txt`, `linkSharing/README.md`
- `stockMedia/{domains,hosts,adblock}.txt`, `stockMedia/README.md`
- `fileSharing/{domains,hosts,adblock,domains-extended}.txt`, `fileSharing/README.md`
