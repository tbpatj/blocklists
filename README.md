# AI / LLM generative-AI domain blocklist

A DNS and hosts blocklist, in the style of community lists such as [HaGeZi](https://github.com/hagezi/dns-blocklists), for sites whose **primary product is generative AI or an LLM**.

This repository is an independent project. It is not affiliated with HaGeZi.

Built 2026-11-01 (America/Denver). The core lists contain **4,879** live hostnames. A separate extended list contains **6,335** lower-confidence hosts; review that file before you use it.

## What it blocks

Chatbots and LLM frontends (including clones and mirrors), AI companions and roleplay, AI image, video, music, and voice/TTS/voice-cloning generators, AI writing, essay, homework, and humanizer tools, AI coding products, AI avatar, face-swap, and deepfake tools, LLM APIs and playgrounds, and AI tool directories.

## Lists

| File | Entries | Use |
|---|---|---|
| [lists/domains.txt](lists/domains.txt) | 4,879 | Plain domains, one per line. Pi-hole domain lists, AdGuard Home, NextDNS, GL-iNet, Technitium, Blocky. |
| [lists/hosts.txt](lists/hosts.txt) | 4,879 | `0.0.0.0 domain`. OS hosts file, Pi-hole, AdGuard Home, dnsmasq. |
| [lists/adblock.txt](lists/adblock.txt) | 4,879 | `\|\|domain^`. AdGuard Home, AdGuard DNS, uBlock Origin, Brave. Also blocks subdomains. |
| [lists/domains-extended.txt](lists/domains-extended.txt) | 6,335 | **Lower confidence. Review before use.** Live hosts that are B2B AI SaaS or products that only include AI as a feature. |

Paste a raw URL into Pi-hole, AdGuard Home, NextDNS, or uBlock Origin:

- Domains: <https://raw.githubusercontent.com/tbpatj/blocklists/main/lists/domains.txt>
- Hosts: <https://raw.githubusercontent.com/tbpatj/blocklists/main/lists/hosts.txt>
- Adblock: <https://raw.githubusercontent.com/tbpatj/blocklists/main/lists/adblock.txt>
- Extended (review first): <https://raw.githubusercontent.com/tbpatj/blocklists/main/lists/domains-extended.txt>

## How to use

**Pi-hole.** Settings → Adlists → add the raw URL of [hosts.txt](lists/hosts.txt) or [domains.txt](lists/domains.txt) → Update gravity (`pihole -g`).

**AdGuard Home.** Filters → DNS blocklists → Add blocklist → paste the raw URL of [adblock.txt](lists/adblock.txt) (covers subdomains) or [hosts.txt](lists/hosts.txt).

**uBlock Origin.** Filter lists → Import → paste the raw URL of [adblock.txt](lists/adblock.txt).

**NextDNS.** Denylist → add the raw URL of [domains.txt](lists/domains.txt).

**Hosts file.** Append [hosts.txt](lists/hosts.txt) to `/etc/hosts` or `C:\Windows\System32\drivers\etc\hosts`, then flush the DNS cache.

## Left out on purpose

YouTube (`youtube.com`, `googlevideo.com`, `ytimg.com`) and sites that only use AI as a feature stay off this list. Also left out: `google.com`, `bing.com`, `microsoft.com`, `apple.com`, `amazon.com` and AWS, Meta/Facebook/Instagram, X/Twitter, Reddit, Discord, GitHub, Wikipedia, Notion, Adobe, Canva, Figma, Grammarly, DeepL, Duolingo, Khan Academy, Chegg, Brainly, Quizlet, stock-photo and art-community sites (DeviantArt, ArtStation, Pixiv, Shutterstock, Freepik), news and tech-press sites, and CDN, cloud, and website-builder roots.

On those platforms, only dedicated AI hostnames are listed. Examples: `gemini.google.com`, `aistudio.google.com`, `notebooklm.google.com`, `labs.google`, `copilot.microsoft.com`, `sydney.bing.com`, `designer.microsoft.com`, `firefly.adobe.com`, `meta.ai`, `grok.com`, `copilot-proxy.githubusercontent.com`, `api.githubcopilot.com`, Bedrock endpoints, and AI-specific `googleapis.com` endpoints.

## Caveats

Path-based AI features on an otherwise allowed site (`bing.com/create`, `x.com/i/grok`, `github.com/copilot`, Google AI Overviews, YouTube Ask) need a cosmetic filter list. [Stevo's AI Blocklist](https://github.com/Stevoisiak/Stevos-AI-Blocklist) is the one to pair with this list.

`huggingface.co` and `replicate.com` are on the core list. Blocking them can break apps and dev tools that download models. Delete those lines if you need model downloads.

AI-first coding products are included, including `cursor.com`, `windsurf.com`, and `lovable.dev`. Delete those lines if you still want those tools.

The long tail has a small false-positive rate (about 1–3%), mostly tiny GPT-wrapper sites classified from a directory description.

[lists/domains-extended.txt](lists/domains-extended.txt) is lower confidence. Read it before you subscribe to it.

## Category counts

Core list, 4,879 hostnames:

| Category | Hosts |
|---|---|
| Chatbot / LLM frontends and GPT wrappers | 1,400 |
| From curated lists (mixed categories) | 905 |
| Writing / homework / humanizer / detector | 721 |
| Image generation / AI photo | 642 |
| Music / voice / TTS / voice cloning | 252 |
| Agents / LLM APIs and infra | 238 |
| Video generation / avatars / dubbing | 233 |
| AI companions / roleplay chat | 207 |
| AI coding / app builders | 188 |
| Deepfake / face swap / NSFW gen | 83 |
| AI tool directories | 10 |

3,979 of the core hostnames appear in none of the smaller open lists this build started from. Full counts: [docs/stats.txt](docs/stats.txt).

## Prior art

Several open AI domain lists already exist. Each is smaller (roughly 100 to 1,100 domains) and aimed at a narrower job, such as image-search cleanup or school exam filters. This list merges those open lists and extends them with AI-tool directories. HaGeZi has no AI category. Credits and notes: [docs/existing-repos.md](docs/existing-repos.md). How the list was built: [docs/sources.md](docs/sources.md).

## License

[MIT](LICENSE). To suggest an add or a removal, see [CONTRIBUTING.md](CONTRIBUTING.md).
