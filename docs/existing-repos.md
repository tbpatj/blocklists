# Prior art: existing AI/LLM domain blocklists (checked 2026-11-01, America/Denver)

**Bottom line:** HaGeZi has no AI category and has turned one down. Several AI lists exist, but none is a large, maintained, HaGeZi-style list of AI-first products (all of them are roughly 1,100 entries or fewer). The best ones are worth merging, and this build merges them all.

| Repo | Format | Size (raw lines / usable domains) | Last activity | Focus / quality notes |
|---|---|---|---|---|
| **HaGeZi** – https://github.com/hagezi/dns-blocklists | many | n/a | active | **No AI category.** Issue #7859 "New Category: Anti-AI" (2025-10-30) was closed by hagezi: DNS can only block AI service domains. He pointed to laylavish's list instead. |
| **laylavish/uBlockOrigin-HUGE-AI-Blocklist** – https://github.com/laylavish/uBlockOrigin-HUGE-AI-Blocklist | uBO, uBlacklist, hosts (`noai_hosts.txt`) | ~1,100 unique hosts (2,220 lines incl. www. dupes) | last push 2025-10-02; 5.8k★, ~200 open issues | Built to **clean AI images out of image-search results**. It has many AI art/gen sites plus AI content farms, nudify sites, and some mixed sites. It misses many chatbots (gemini, grok etc., per the HaGeZi issue). Not well maintained now. |
| **lumiworx/HPT-AI-Blocklist** (Codeberg) – https://codeberg.org/lumiworx/HPT-AI-Blocklist | hosts, split by category (Audio, DevTools, Explicit, Google/Apple apps, Malicious, .art, etc.) | ~1,150 listed (~770 usable domains, plus path entries) | updated 2026-10-31; 12★ | Mostly derived from laylavish, with sensible category split files. Actively maintained. |
| **christopherarter/AI-Parental-Block-List** – https://github.com/christopherarter/AI-Parental-Block-List | hosts + plain domains | ~1,000 (717 plain domains) | 2026-08; 1★ | Parental-control use case. Rebuilt weekly from an upstream source (looks laylavish/HPT-derived). Includes some non-AI stock sites (123rf.com, etc.). |
| **Caesarovich/dns-blocklist-ai** – https://github.com/Caesarovich/dns-blocklist-ai | AdGuard + Pi-hole | 103 | 2025-03; 8★ | Built for schools/exams; major chatbots + clones. Includes some false positives (ahrefs.com, duckduckgo.com, search.brave.com, deepl.com). |
| **abixb/llm-hosts-blocklist** – https://github.com/abixb/llm-hosts-blocklist | hosts | ~235 | 2025-08; 7★ | Good **API/endpoint** coverage (api.openai.com, bedrock, googleapis AI endpoints, copilot-proxy). Also blocks general things (cloud.google.com, translate/vision googleapis, notion, grammarly, deepl). |
| **ralf.kirchner/ai-domian-blocklist** – https://dev.ksite.de/ralf.kirchner/ai-domian-blocklist | AdGuard | ~76 | — | German; major chatbots. Blocks all of Notion and Khan Academy. |
| **NgTech Categorized-Web-Filter-Blocklists /ai** – https://git.ngtech.co.il/NgTech-LTD/Categorized-Web-Filter-Blocklists | plain | 25 | — | Tiny; top chatbots only. |
| **Stevoisiak/Stevos-AI-Blocklist** – https://github.com/Stevoisiak/Stevos-AI-Blocklist | uBO/AdGuard **cosmetic** | ~6k rules | active 2026; 832★ | **Not a domain list.** It hides AI *features* inside sites (Google AI Overviews, YouTube Ask, Copilot buttons, Grok buttons). Complements a DNS list well. |
| **GloomyD/blocklists** (`ia-seo`) – https://github.com/GloomyD/blocklists | uBlacklist/NextDNS | ~few hundred | 2026-10 | French AI-generated **SEO spam/content-farm** sites, not AI products. |
| **FranklyRocks/OnlyHuman** (recommended by hagezi) – https://github.com/FranklyRocks/OnlyHuman | browser filter | — | — | Content-level AI filtering in the browser, not DNS. |
| **aitoolsblocklist.com / npm `aiblocklist`** – https://www.aitoolsblocklist.com | commercial feed | claims 11,850–20,000+ domains, 18 categories | daily | **Commercial/paid** data feed for DNS vendors. Not an open HaGeZi-style list. |
| AdGuard HostlistsRegistry issue #647 – https://github.com/AdguardTeam/HostlistsRegistry/issues/647 | "Blocked services" | handful | 2026-01 | AdGuard Home's built-in Blocked Services now cover ChatGPT, Claude, DeepSeek, etc. Only the big names. |

Data sources (not blocklists) used for harvesting:
- **lakey009/AI-Tools-List**: https://github.com/lakey009/AI-Tools-List. `AIToolsList.json` has 19,466 AI tools with website URL and description (last push 2025-06).
- Awesome lists: steven2358/awesome-generative-ai, mahseema/awesome-ai-tools, ikaijua/Awesome-AITools, eudk/awesome-ai-tools, humanloop/awesome-chatgpt, e2b-dev/awesome-ai-agents, LiLittleCat/awesome-free-chatgpt (ChatGPT mirror/clone sites).
