# fileSharing

**Purpose:** block one-click file hosts, anonymous/temporary upload sites, large-file transfer services, multihoster/debrid "premium leech" services and video file lockers (mega.nz, file.io, mediafire, dropmefiles, gofile, pixeldrain, anonfiles-style, wetransfer, catbox, 1fichier, ...).

**Entries:** 1040 (`domains.txt`, `hosts.txt`, `adblock.txt`) · 1073 in `domains-extended.txt` (main + 33 mainstream cloud-drive hosts)

## Sources
| Source | Kept in final |
|---|---|
| cr-chsn1 gist `blocklist_och_streaming.txt`, **`[OCH / Multihoster]` section only** (Linkcrypter + Streaming sections dropped) — https://gist.github.com/cr-chsn1/f654df7ce3d7af77934185a77172dfca | 735 |
| UT1 `filehosting` (olbat/ut1-blacklists) — https://raw.githubusercontent.com/olbat/ut1-blacklists/master/blacklists/filehosting/domains | 371 |
| Hand-curated seeds (homepage titles checked 2026-11-02) | 84 |
(overlapping entries counted under every source that listed them)

## Process
1. Normalize (lowercase, strip `www.`, valid hostname, no IPs); Python-set dedupe.
2. Exclusions (`build/fs_exclude.txt`): imgur, istockphoto, alamy, freepik and ~165 image hosts (keyword + manual); social/video/doc platforms (dailymotion, soundcloud, scribd, issuu, slideshare, artstation, nexusmods...); ISPs/web hosts (free.fr, 1und1, 123-reg, OVH hosts); CDNs that would break other sites (llnwd.net, filesusr.com/Wix, dweb.link, baycdn); proxies/unblockers, warez/torrent index sites, usenet providers.
3. Cloudflare DoH: 399 NXDOMAIN/no-answer domains dropped (`build/fs_dead.txt`).
4. Homepage `<title>` fetch (≤64 KB/page, streamed, nothing retained): parked / for-sale / casino / togel / porn-repurposed and non-file-host pages dropped (`build/fs_title_drop.txt` + rule-based flags in `build/fs_flag.tsv`).
5. Mainstream cloud drives (Dropbox, Box, OneDrive/SkyDrive, Yandex Disk, pCloud, Baidu Pan, mail.ru cloud, ShareFile, ...) are only in `domains-extended.txt`.

## Notes
- Domains that resolve but returned TLS error / timeout / Cloudflare challenge are kept (DNS-live, homepage unverified).
- Dead examples: anonfiles.com, anonfile.com, bashupload.com, ge.tt (NXDOMAIN). 2shared.com → casino page; fastupload.io → for sale (excluded).
- Overlap with the AI list: terabox.com.
