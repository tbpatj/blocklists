# New category blocklists (rebuilt 2026-11-02, America/Denver)

Four **separate** lists (not merged into the AI list). Each folder: `domains.txt`, `hosts.txt` (`0.0.0.0 host`), `adblock.txt` (`||host^`), `README.md`. HaGeZi-style headers with `Category:` and Homepage https://github.com/tbpatj/blocklists.

| Category | Entries | Main sources |
|---|---|---|
| fileSharing | 1040 (+ `domains-extended.txt` 1073) | cr-chsn1 OCH/Multihoster section (735), UT1 filehosting (371), curated (84); DoH + homepage-title filtered |
| linkSharing | 119 | lorien/awesome-pastebins (91), curated (45) |
| gifs | 48 | hand-curated platforms + CDNs |
| stockMedia | 326 | brand-owned ccTLDs for zrovihr stock brands (254) + curated free/video stock + CDNs (72) |

Verification: Cloudflare DoH for every candidate; homepage `<title>` fetch (≤64 KB/page, threaded, streamed) to drop parked / for-sale / casino-repurposed domains; dedupe/membership with Python sets.
fileSharing is 15 lower than the first run (1055) because the rebuild's fresh title check caught 14 more HugeDomains "for sale"/parked domains and 1 casino redirect.

Publish layout: `lists/<category>/{domains,hosts,adblock}.txt` + README (`domains-extended.txt` optional for fileSharing). `raw/` and `build/` are working files (not for publishing).

Cross-list overlap: none between the four. With the AI list: terabox.com (fileSharing), creativefabrica.com + elements.envato.com (stockMedia).
