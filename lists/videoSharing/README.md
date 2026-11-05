# videoSharing

**Purpose:** block user-generated / video-sharing platforms (watch + upload) **and licensed video streaming services (SVOD, FAST/AVOD, live-TV/vMVPD, sports streaming)**, their brand-owned media/CDN/API hosts, and major regional versions.

**Entries:** 601 = 298 UGC (curated 2026-11-05) + 303 streaming (added 2026-11-05, America/Denver; snapshot of the UGC-only list kept at `build/vs_final_ugc_2026-11-05.txt`). Every host Cloudflare-DoH-checked (A/AAAA); homepage titles sampled for parked/for-sale/hijacked/off-topic rejects. See `build/vs_seed.txt`, `build/vs_doh.tsv`, `build/vs_exclude.txt`.

## Includes (notable)

- **YouTube:** youtube.com, youtu.be, youtube-nocookie.com, m/music/gaming/studio/tv.youtube.com, googlevideo.com, i/s/i1/i9.ytimg.com, yt3.ggpht.com / yt3.googleusercontent.com, youtubei/youtube/youtubeembeddedplayer.googleapis.com, youtubekids/youtubegaming/youtubeeducation, yt.be, plus brand-owned country TLDs (youtube.co.uk/.de/.fr/.nl/.pl/.be/.co.jp/.com.br/.com.au/.es/.it/.ca/.co.in/.com.mx/.ru/.com.tr/.ae/.co.za/… — title-checked redirects to YouTube).
- **X / Twitter:** x.com, twitter.com, mobile/api hosts, video.twimg.com, video-s.twimg.com, pbs/abs/ton.twimg.com (`t.co` omitted — link shortener).
- **Vimeo:** vimeo.com/.fr/.de/.tv, player.vimeo.com, vimeocdn.com, i/f.vimeocdn.com, vimeopro.com.
- **OFTV:** of.tv (OnlyFans’ free creator-video streaming app/site) + onlyfans.com + cdn3.onlyfans.com.
- **TikTok / Douyin / CapCut:** tiktok.com, m/vm/vt.tiktok.com, tiktokv.com, musical.ly, snssdk.com, bytedance.com/.net, douyin.com, capcut.com. *(Many `tiktokcdn*` / `muscdn` / `ibyteimg` apexes have no A/AAAA via DoH — omitted; see exclusions.)*
- **Twitch / Kick:** twitch.tv/.com, clips/m.twitch.tv, id.twitch.tv, static-cdn.jtvnw.net, static.twitchcdn.net, live-video.net, kick.com.
- **Dailymotion:** dailymotion.com/.fr, dai.ly, dmcdn.net, static1.dmcdn.net, dm-event.net, geo.dailymotion.com.
- **Alts:** rumble.com + rmbl.ws / 1a-1791.com / hugh.cdn.rumble.cloud; odysee.com, lbry.com/.tv, spee.ch; bitchute.com + static-3.bitchute.com; banned.video, brighteon.com; d.tube, dlive.tv, 3speak.tv; godtube.com; ganjingworld.com/ganjing.com.
- **Short share / screen video:** streamable.com, loom.com + cdn.loom.com, screencast.com, screencast-o-matic.com (ScreenPal).
- **PeerTube (popular public):** joinpeertube.org, framatube.org, peertube.tv, peertube.cpy.re, peertube.uno, peertube.ch, tilvids.com, makertube.net, video.blender.org, tube.tchncs.de, peer.tube, diode.zone, skeptikon.fr, veedeo.org, wiwi.video, pony.tube, spook.tube, thecool.tube. *(peertube.social hijacked — omitted.)*
- **CN:** bilibili.com/.tv/.cn, b23.tv, api/player.bilibili.com, i0/i1/s1/static.hdslb.com, upos-sz-mirrorcos.bilivideo.com, biliintl.com, acfun.cn; youku.com/.tv, ykimg.com, tudou.com; iqiyi.com, iqiyipic.com, qy.net; v.qq.com, video.qq.com; ixigua.com; kuaishou.com, ksapisrv.com, gifshow.com; douyin.com; 56.com, miaopai.com, huoshan.com, mgtv.com/hunantv.com, haokan.baidu.com, video.weibo.com.
- **JP:** nicovideo.jp, nico.ms, sp.nicovideo.jp; video.fc2.com; openrec.tv, twitcasting.tv, showroom-live.com, reality.app.
- **KR:** tv.naver.com, tv.kakao.com, play-tv.kakao.com; afreecatv.com → SOOP (sooplive.com/.co.kr); pandora.tv; flextv.co.kr; bigo.tv/.sg; weverse.io; 17.live; pandalive.co.kr.
- **RU/CIS:** rutube.ru; vk.com/.ru, vkvideo.ru, vkuservideo.com/.net, userapi.com; ok.ru, okcdn.ru, ok.me, mycdn.me; yappy.media/.ru.
- **IR:** aparat.com, cdn.aparat.com.
- **SEA/BR/IN short-form:** kwai.com/.com.br/.net, kwai-video.com; snackvideo.com; likee.com/.video; moj.app; chingari.io; sharechat.com; triller.co; clapperapp.com; lemon8.com / lemon8-app.com.
- **Adult UGC tubes (main set):** xvideos.com/.es/2 + xvideos-cdn.com; xnxx.com/.tv; pornhub.com/.org/premium + ei/cdn1d phncdn; xhamster.com/.desi + xhcdn/ahcdn; redtube, youporn, spankbang, eporner, tube8, txxx, tnaflix, drtuber, sunporno, hqporner, beeg, manyvids, porn.com, porntube, empflix, nuvid, thisvid, ashemaletube, gaytube, xxxbule, pornmd.
- **Live UGC:** younow.com, caffeine.tv, bigo.tv (plus KR/JP live above).
- **Meta video short-links only:** fb.watch, fbwat.ch (→ Facebook Watch). Full facebook.com / instagram.com / fbcdn / cdninstagram **not** listed.

## Streaming expansion (2026-11-05, America/Denver) — +303 hosts

Requested: "add streaming platforms like twitch.tv and others". **Twitch was already on the list** (twitch.tv/.com, clips/m/id.twitch.tv, static-cdn.jtvnw.net, static.twitchcdn.net, live-video.net) along with Kick, DLive, YouNow, SOOP, etc. This pass adds licensed video streaming. Every new host is Cloudflare-DoH LIVE (A/AAAA) and homepage-title checked. Build files: `build/vs_streaming_seed.txt`, `vs_streaming_doh.tsv`, `vs_streaming_titles.tsv`, `vs_streaming_final.txt` (+ `vs_streaming_final_doh.tsv`), rejects appended to `vs_exclude.txt`.

- **Netflix:** netflix.com/.net/.ca/.co.uk, nflxvideo.net, nflxext.com (+assets.), nflximg.com, nflxsearch.net, api-global/ichnaea/secure.netflix.com.
- **Disney+ / Star+:** disneyplus.com/.co.uk, disneyplus.disney.co.jp, disneystreaming.com, dssott.com, disney.api/disney.content/global.edge.bamgrid.com, prod-ripcut-delivery/prod-static/appconfigs.disney-plus.net, starplus.com.
- **Hulu:** hulu.com, hulu.tv, huluad.com, play/discover.hulu.com, ib/assets.huluim.com.
- **Max / HBO:** max.com, play.max.com, hbomax.com, play.hbomax.com, hbo.com, hbogoasia.com, art-gallery.api.hbo.com, default.any-any.prd.api.max.com / .discomax.com, discoveryplus.com.
- **Prime Video / Freevee:** primevideo.com/.co.uk, amazonvideo.com, atv-ps/atv-ps-eu/atv-ps-fe/atv-ext.amazon.com (Prime Video API hosts only — **not** amazon.com), freevee.com.
- **Paramount+ / Showtime / BET+ / Pluto TV:** paramountplus.com/.com.br, paramount.plus, pplusstatic.com, vod-gcs-cedexis.cbsaavideo.com, cbsios-vh.akamaihd.net, showtime.com, sho.com, bet.plus, pluto.tv, plutotv.com, service-stitcher.clusters.pluto.tv, images.pluto.tv.
- **Peacock:** peacocktv.com, peacock.com, ovp/play.ovp.peacocktv.com.
- **Apple TV+:** tv.apple.com, play/play-edge/hls/hls-svod.itunes.apple.com (video playback hosts — **not** apple.com).
- **FAST / AVOD / other US:** youtubetv.com (tv.youtube.com was already listed), tubi.tv, tubitv.com, adrise.tv (+s./uapi. — Tubi CDN/API), therokuchannel.roku.com/.com, plex.tv + watch.plex.tv, xumo.tv/.com, distro.tv, crackle.com, vudu.com / fandangoathome.com, kanopy, mubi, criterionchannel, shudder, britbox, acorn.tv, amcplus, wetv.com (WE tv), starz, mgmplus/epixnow, curiositystream, magellantv, gaia, fox.com/foxone.com.
- **vMVPD / live TV:** sling.com/.tv + watch.sling.com, dishanywhere.com, fubo.tv/fubotv.com/fubo.com, stream.directv.com, directvstream.com, philo.com, frndlytv.com.
- **Sports:** plus.espn.com, espnplus.com, dazn.com, nflgamepass.com, nflplus.com, mlb.tv, nhl.tv, fifaplus.com, f1tv.formula1.com, flosports.tv, fite.tv/trillertv.com, willow.tv, connect.beinsports.com, tod.tv.
- **Anime:** crunchyroll.com/.co (+static./imgsrv.), vrv.co, funimation.com, animelab.com (all now redirect to Crunchyroll), hidive.com, retrocrush.tv.
- **India:** hotstar.com (+hses.), secure-media.hotstarext.com, jiohotstar.com, jiocinema.com, jiotv.com, voot.com, zee5.com, sonyliv.com, mxplayer.in, mxplay.com, erosnow.com, altbalaji.com/altt.co.in/kutingg.com, aha.video, sunnxt.com, hoichoi.tv.
- **East/SE Asia:** wetv.vip, iq.com, viki.com + api.viki.io, viu.com, viu.tv, iflix.com; JP: abema.tv + api.abema.io, tver.jp, unext.jp/video.unext.jp, hulu.jp/.co.jp, fod.fujitv.co.jp, tv.dmm.com, lemino.docomo.ne.jp, telasa.jp, paravi.jp, www.nhk-ondemand.jp; KR: wavve.com, tving.com, coupangplay.com, watcha.com; TW/HK/SG/ID/PH: catchplay.com, linetv.tw, myvideo.net.tw, hamivideo.hinet.net, mytvsuper.com, nowe.com, mewatch.sg, vidio.com, iwant.ph, iwanttfc.com.
- **RU:** hd.kinopoisk.ru, ivi.ru/.tv, okko.tv, premier.one, more.tv, start.ru, wink.ru, kion.ru.
- **CA/AU/NZ:** crave.ca, gem.cbc.ca, stan.com.au/stan.au/play.stan.com.au, binge.com.au, kayosports.com.au, foxtel.com.au, 7plus/9now/10play.com.au, iview.abc.net.au, tvnz.co.nz, threenow.co.nz, neontv.co.nz, skygo.co.nz.
- **UK:** itv.com/itvx.com (ITVX), channel4.com, my5.tv/channel5.com, stv.tv/player.stv.tv, nowtv.com/.co.uk, BBC iPlayer media hosts only (ibl.api.bbci.co.uk, vod-dash-uk-live / vod-hls-uk-live.akamaized.net).
- **EU:** skyshowtime.com, nowtv.it, wowtv.de, canalplus.com/mycanal.fr/canal-plus.com, movistarplus.es, atresplayer.com, mitele.es, filmin.es/.pt/.com, raiplay.it, mediasetinfinity/mediasetplay.mediaset.it, timvision.it, joyn.de, rtlplus.de, zdf.de, ardmediathek.de, magentatv.de, waipu.tv, zattoo.com, arte.tv, france.tv, tf1.fr/tf1plus.fr, m6.fr/6play.fr, molotov.tv, videoland.com, npostart.nl, vtm.be/vtmgo.be/goplay.be/play.tv, viaplay.com, play.tv2.no, tv2play.dk, cmore.se/tv4play.se, svtplay.se, tv.nrk.no, areena.yle.fi, ruutu.fi, opto.sic.pt, player.pl, cda.pl, polsatboxgo.pl, vod.tvp.pl, voyo.cz/.ro, ivysilani.cz.
- **LatAm / MENA / Africa:** globoplay.globo.com/globoplay.com, telecine.com.br, clarovideo.com, vix.com, mercadoplay.com, shahid.mbc.net/shahid.net, osnplus.com, weyyak.com, starzplay.com/.ae, irokotv.com.

### Streaming borderline (kept — Timothy may want to drop)

| Host | Why borderline |
|---|---|
| hbo.com, starz.com, amcplus.com, wetv.com, fox.com | Network brand sites that are now primarily streaming front-ends. |
| itv.com, channel4.com, channel5.com, tf1.fr, m6.fr, zdf.de, france.tv, arte.tv | Broadcaster apexes whose homepage *is* the streaming player, but also carry some news/corporate pages. |
| plex.tv | Also the account/sign-in hub for personal Plex Media Servers — blocking it breaks self-hosted Plex too (plex.direct deliberately **not** listed). |
| canalplus.com, foxtel.com.au, magentatv.de, waipu.tv, zattoo.com | Pay-TV operators / IPTV; their sites mix streaming with subscription sales. |
| atv-ps*.amazon.com, play*/hls*.itunes.apple.com | Video-only subdomains of amazon.com / apple.com; may also affect purchased iTunes movies. |
| cda.pl | Mixed UGC + licensed VOD. |
| mlb.tv, nhl.tv, nflgamepass.com | Redirect to league/DAZN pages; streams themselves partly run on league domains not listed. |

### Streaming limits / skipped

- **CDN zones with no apex A/AAAA** (DNS-only blockers miss them; suffix/wildcard blockers like Pi-hole regex, NextDNS, AdGuard can add them manually): `nflxso.net`, `nflximg.net`, `aiv-cdn.net`, `aiv-delivery.net`, `pv-cdn.net`, `bamgrid.com`, `disney-plus.net`, `hulustream.com`, `huluim.com`, `hbomaxcdn.com`, `discomax.com`, `cbsaavideo.com`, `hotstarext.com`, `daznservices.com`, `dazn-api.com`, `plutotv.net`, `abema.io`, `dmm.tv`. The adblock-format `||domain^` rule matches subdomains, so adding these apexes to `adblock.txt` users' custom rules is effective.
- **Path-only services (can't be DNS-blocked without the parent):** BBC iPlayer (`bbc.co.uk/iplayer`), DRTV (`dr.dk/drtv`), SBS On Demand (`sbs.com.au/ondemand`), NBA League Pass (`nba.com/watch`), MLB.TV app traffic on mlb.com, ESPN app on espn.com. Parent domains omitted as too broad.
- **Too broad / not streaming:** amazon.com, apple.com, m.media-amazon.com, bbc.co.uk/bbc.com/bbci.co.uk, espn.com/espncdn.com, nba.com/mlb.com/nfl.com/fifa.com/foxsports.com, sky.com, directv.com, dstv.com, kinopoisk.ru (film database), fast.com (Netflix speed test), hoopladigital.com (books-first), vizio.com, trueid.net, link.theplatform.com (shared Comcast/CBS).
- **Dead / shut down / parked:** Salto, Pantaya, KKTV (sunset), GYAO!, HBO Go EU, Redbox, Showmax (no A), blim, foxtelgo, espnplayer.com, hbonow/hbogo.com, nbaleaguepass.com (parked), wetv.tv (parked), now.tv (parked), friday.tw (shopping, not friDay Video).
- **Audio-first music streaming** (Spotify, Apple Music, Deezer, Tidal, etc.) intentionally not added.

## Borderline — UGC set (kept — Timothy may want to drop)

| Host | Why borderline |
|---|---|
| onlyfans.com | Broader than of.tv (photos + paywall); kept because creator video sharing is core. |
| fb.watch / fbwat.ch | Video-specific Meta short-links; do **not** pull in all of Facebook/Instagram. |
| nebula.tv / watchnebula.com / floatplane.com | Creator subscription platforms (SVOD-ish) but UGC creator video. |
| capcut.com | Editor with share links (requested if distinct). |
| lemon8.com / lemon8-app.com | ByteDance lifestyle app with video; lighter than TikTok. |
| live-video.net | Amazon property used heavily by Twitch CDN. |
| bytedance.com | Corporate apex; kept with TikTok infra hosts used by common TikTok blocklists. |
| v.qq.com / video.qq.com | Tencent Video mixes licensed + UGC. |
| mgtv.com / hunantv.com / pptv.com / 56.com | CN platforms with mixed licensed/UGC catalogs. |
| newgrounds.com | Games/Flash + video hosting. |
| schooltube.com / teachertube.com / watchknowlearn.org | Educational UGC video. |
| weverse.io | K-pop fan platform with video, not a pure tube. |
| gab.com omitted; social-only. |

## Excluded / dead

- ~~SVOD~~ — previously excluded; **now included** (see Streaming expansion above).
- **Other categories:** giphy/tenor/coub/redgifs → `gifs`; mega/mediafire/pixeldrain → `fileSharing`; stock footage → `stockMedia`.
- **t.co** — Twitter link shortener (skip per brief).
- **Parked/hijacked:** joshapp.com, snack.com (not SnackVideo), navertv.com (use tv.naver.com), **peertube.social** (Garuda88 gambling), xgvideo.com (spam redirect).
- **Too broad:** weibo.com (kept video.weibo.com), fc2.com (kept video.fc2.com), facebook.com/instagram.com/fbcdn.net/cdninstagram, qq.com/yandex.ru apexes, bunny.net/mux.com/Brightcove/Kaltura/Panopto/JW Player enterprise OVPs.
- **CDN apexes with no A/AAAA via Cloudflare DoH** (subdomains kept where LIVE): ytimg.com, tiktokcdn.com (+ -us/-eu/-in), jtvnw.net, ttvnw.net, twitchcdn.net, bilivideo.com, hdslb.com, phncdn.com, ypncdn.com, dmxleo.com, muscdn.com, ibyteimg.com, ttlivecdn.com, ttwstatic.com. For suffix-style blockers you may want to add those apexes manually.
- **Dead services omitted:** LiveLeak, Justin.tv, Vine, Metacafe, Veoh, Periscope, V Live, Mixer, etc.
- Full reject log: `categories/build/vs_exclude.txt` + `vs_dead.txt`.

## Sources

- Streaming pass: hand-curated brand domains + known media/API hosts (NextDNS/v2ray-style service lists as reference), each DoH + homepage-title verified 2026-11-05

- Wikipedia [List of online video platforms](https://en.wikipedia.org/wiki/List_of_online_video_platforms) / Comparison of video hosting services
- NextDNS services lists (youtube, vimeo, tiktok), Ghostery tracker DB (tiktok_cdn, twitch_cdn), v2ray domain-list-community (twitch)
- PeerTube instance directory (instances.joinpeertube.org) — top public instances by users
- Local UT1 `audio-video` snapshot under `/workspace/bl/` (seed cross-check only; not bulk-imported)
- Hand curation for regional CN/JP/KR/RU/IR/SEA/IN/BR + adult tubes + brand CDNs
