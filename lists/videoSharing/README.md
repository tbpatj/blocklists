# videoSharing

**Purpose:** block user-generated / video-sharing platforms (watch + upload), their brand-owned media/CDN/API hosts, and major regional versions — not SVOD/licensed streaming catalogs.

**Entries:** 298 (curated 2026-11-05, America/Denver). Every host Cloudflare-DoH-checked (A/AAAA); homepage titles sampled for parked/for-sale/hijacked/off-topic rejects. See `build/vs_seed.txt`, `build/vs_doh.tsv`, `build/vs_exclude.txt`.

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

## Borderline (kept — Timothy may want to drop)

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

- **SVOD:** Netflix, Disney+, Hulu, Max, Prime Video, Paramount+, Peacock, Apple TV+, Crunchyroll, Funimation, Crave, Hotstar, WeTV (wetv.*), iq.com (iQIYI intl), MX Player, Abema/TVer/Wavve/TVING/Coupang Play, etc.
- **Other categories:** giphy/tenor/coub/redgifs → `gifs`; mega/mediafire/pixeldrain → `fileSharing`; stock footage → `stockMedia`.
- **t.co** — Twitter link shortener (skip per brief).
- **Parked/hijacked:** joshapp.com, snack.com (not SnackVideo), navertv.com (use tv.naver.com), **peertube.social** (Garuda88 gambling), xgvideo.com (spam redirect).
- **Too broad:** weibo.com (kept video.weibo.com), fc2.com (kept video.fc2.com), facebook.com/instagram.com/fbcdn.net/cdninstagram, qq.com/yandex.ru apexes, bunny.net/mux.com/Brightcove/Kaltura/Panopto/JW Player enterprise OVPs.
- **CDN apexes with no A/AAAA via Cloudflare DoH** (subdomains kept where LIVE): ytimg.com, tiktokcdn.com (+ -us/-eu/-in), jtvnw.net, ttvnw.net, twitchcdn.net, bilivideo.com, hdslb.com, phncdn.com, ypncdn.com, dmxleo.com, muscdn.com, ibyteimg.com, ttlivecdn.com, ttwstatic.com. For suffix-style blockers you may want to add those apexes manually.
- **Dead services omitted:** LiveLeak, Justin.tv, Vine, Metacafe, Veoh, Periscope, V Live, Mixer, etc.
- Full reject log: `categories/build/vs_exclude.txt` + `vs_dead.txt`.

## Sources

- Wikipedia [List of online video platforms](https://en.wikipedia.org/wiki/List_of_online_video_platforms) / Comparison of video hosting services
- NextDNS services lists (youtube, vimeo, tiktok), Ghostery tracker DB (tiktok_cdn, twitch_cdn), v2ray domain-list-community (twitch)
- PeerTube instance directory (instances.joinpeertube.org) — top public instances by users
- Local UT1 `audio-video` snapshot under `/workspace/bl/` (seed cross-check only; not bulk-imported)
- Hand curation for regional CN/JP/KR/RU/IR/SEA/IN/BR + adult tubes + brand CDNs
