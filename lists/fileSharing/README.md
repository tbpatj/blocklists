# fileSharing

**Purpose:** block one-click file hosts, anonymous/temporary upload sites, large-file transfer services, multihoster/debrid "premium leech" services and video file lockers (mega.nz, file.io, mediafire, dropmefiles, gofile, pixeldrain, anonfiles-style, wetransfer, catbox, 1fichier, ...).

**Entries:** 1294 (`domains.txt`, `hosts.txt`, `adblock.txt`; 1040 original + 254 added 2026-11-02) · 1333 in `domains-extended.txt` (main + 39 mainstream cloud-drive hosts)

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

## Expansion 2026-11-02 (+254 main, +6 extended)
- **Debrid supported-host lists** (public APIs, hoster entries only — streaming-site and link-protector sections ignored): Real-Debrid `/hosts/domains`, AllDebrid `/v4/hosts` (`hosts` group), Premiumize `/services/list`, TorBox `/webdl/hosters` (type `hoster`). 351 new names → manual removal of social/video/archive/booru/adult-tube/Google/Discord/Telegram/random-rotating domains → DoH → title check. Plus ~90 hand-curated temp-upload/transfer/regional hosts.
- **Notable adds:** clicknupload.* & clickndownload.* mirrors, katfile.*, turbobit/hitfile mirrors (hif.to family), rapidgator.asia/rg.to, k2share.cc, nitro.download/nitroflare.net, mixdrop.*, streamtape.* (+ tapecontent.net), voe.sx + mirrors, doodstream/dood.*, filemoon.sx/.to, vidhide.com, lulustream.com, vidoza.*, bunkr.* + cyberdrop.cr, pixeldrain.dev/.net, filedot.*, hubcloud.*, hubdrive.*, driveseed.org, filepress.*, webshare.cz, simfileshare.net, pillowcase.su, apkadmin.com, modsbase.com, sharemods.org, transfer.it (MEGA), TeraBox mirrors (1024terabox.com, terabox.app, 4funbox.com, gibibox.com, nephobox.com, freeterabox.com, teraboxlink.com, terasharelink.com, teraboxshare.com, momerybox.com, tibibox.com), mypikpak.com, Lanzou (lanzoux/lanzoui/lanzouw/lanzout/ilanzou.com), wenshushu.cn, firestorage.jp, axfc.net, fex.net, 0x0.st, x0.at, envs.sh, oshi.at, qu.ax, pomf.lain.la, tmp.ninja, tempfiles.ninja, send.vis.ee, fileditch.com, masv.io, wesendit.com, send.tresorit.com, transfer.pcloud.com, cloudup.com.
- **Extended only:** disk.yandex.net, disk.yandex.ru, koofr.eu, 123pan.com, 123684.com, filen.io.
- **Checked and rejected:** 60 NXDOMAIN; parked/casino/repurposed (heroupload.com toto, ifolder.com.ua & vidcloud.ru & xrfiles.ru casinos, turbobit.com/tourbit.com parked, turbobyte.net/mediafire.cc for sale, bdupload.in torrent proxy, dfiles.ru blog, gofile.me = Synology QuickConnect, cowtransfer.com now a design tool, dotup.org closed). See `build/fs_title_drop.txt` and `build/fs_exclude.txt`.
