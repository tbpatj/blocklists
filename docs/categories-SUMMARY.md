# New category blocklists (rebuilt 2026-11-02, expanded 2026-11-02 evening, America/Denver; videoSharing added 2026-11-05)

Five **separate** lists (not merged into the AI list). Each folder: `domains.txt`, `hosts.txt` (`0.0.0.0 host`), `adblock.txt` (`||host^`), `README.md`. HaGeZi-style headers with `Category:` and Homepage https://github.com/tbpatj/blocklists.

| Category | Entries | Main sources |
|---|---|---|
| fileSharing | 1294 (+ `domains-extended.txt` 1333) | cr-chsn1 OCH/Multihoster section (735), UT1 filehosting (371), curated (84); **2026-11-02 expansion +254**: Real-Debrid / AllDebrid / Premiumize / TorBox public hoster lists + curated temp-upload/transfer/regional hosts |
| linkSharing | 281 | lorien/awesome-pastebins (91), curated (45); **expansion +162**: privatebin.info/directory public instances, paste clones, Telegraph mirrors, anonymous notepads |
| gifs | 133 | hand-curated platforms + CDNs; **expansion +85**: GIF CDN/API hosts, reaction/NSFW GIF sites, multi-language animated-GIF galleries, GIF makers/converters, Coub |
| stockMedia | 626 | brand-owned ccTLDs for zrovihr stock brands (254) + curated (72); **expansion +300**: 40 brands × 85 TLDs ownership-checked, CDNs, paid/editorial + regional (JP/KR/CN/RU/DE) agencies, neutraltone/awesome-stock-resources free stock, vector/icon/PNG-cutout sites |
| videoSharing | 601 | hand-curated 2026-11-05 (America/Denver): user-generated video-sharing **and** licensed streaming (SVOD, FAST/AVOD, live-TV). UGC includes YouTube, X/Twitter, Vimeo, of.tv, TikTok, Twitch (already in the first 298), regional tubes, and adult UGC tubes. Streaming adds Netflix, Disney+, Hulu, Max, Prime Video, Peacock, Paramount+, Crunchyroll, Tubi/Pluto, and other regional streamers (+303). Cloudflare DoH (A/AAAA) plus homepage title checks. See `lists/videoSharing/README.md`. |

Verification: Cloudflare DoH for every candidate; homepage `<title>` fetch (≤64 KB/page, threaded, streamed) to drop parked / for-sale / casino-repurposed domains; dedupe/membership with Python sets.
fileSharing is 15 lower than the first run (1055) because the rebuild's fresh title check caught 14 more HugeDomains "for sale"/parked domains and 1 casino redirect.

Publish layout: `lists/<category>/{domains,hosts,adblock}.txt` + README (`domains-extended.txt` optional for fileSharing). `raw/` and `build/` are working files (not for publishing).

Cross-list overlap: none between the five. With the AI list `domains.txt` (not merged): terabox.com (fileSharing); clipart-library.com, creativefabrica.com, elements.envato.com, icons8.com, stockcake.com (stockMedia). videoSharing does not overlap the AI core list or `domains-extended.txt`.

Expansion details: see `EXPANSION-2026-11-02.md`. Working files for the expansion: `build/exp/` (candidates, DoH results, titles) and `raw/exp/` (debrid host API dumps, PrivateBin directory, awesome-stock-resources).
