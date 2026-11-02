# Sources & method

## Inputs (raw copies in `raw/`)
| Source | Candidate hosts | Hosts in final list* |
|---|---|---|
| lakey009/AI-Tools-List `AIToolsList.json` (19,466 AI tools with URL + description) | 19,116 | 4,040 |
| laylavish noai_hosts.txt (crypto/Tumblr sections skipped) | 1,099 | 668 |
| Hand-curated seed of major AI products/hostnames (`build/seed_major.txt`) | 516 | 470 |
| lumiworx HPT-Full-AI-List | 770 | 439 |
| christopherarter ai-blocklist-domains.txt | 717 | 422 |
| eudk/awesome-ai-tools | 515 | 241 |
| mahseema/awesome-ai-tools | 372 | 238 |
| steven2358/awesome-generative-ai | 249 | 197 |
| abixb/llm-hosts-blocklist | 235 | 164 |
| ikaijua/Awesome-AITools | 153 | 89 |
| Caesarovich/dns-blocklist-ai | 103 | 85 |
| e2b-dev/awesome-ai-agents | 268 | 73 |
| LiLittleCat/awesome-free-chatgpt | 469 | 61 |
| ksite ai-domian-blocklist | 76 | 59 |
| NgTech /ai | 25 | 25 |
| humanloop/awesome-chatgpt, ai-collection | 17 | 7 |
*A host can come from more than one source.

## Pipeline (`build/`)
1. `extract.py`: pulls hostnames from every source, normalizes them (lowercase, strips `www.`, valid FQDN check), and keeps the description text.
2. `classify.py`: uses the public suffix list with tldextract. Drops any host whose registrable domain is in `exclude.txt` (YouTube, Google, Microsoft, Bing, Apple, Amazon/AWS, Meta, GitHub, Adobe, Canva, social networks, news, stock photo, wiki/arXiv, CDNs, website builders, education/homework platforms, etc.). The exception is a dedicated AI subdomain hand-listed in the seed (e.g. `gemini.google.com`, `copilot.microsoft.com`, `firefly.adobe.com`). Also drops known false positives from upstream lists (ahrefs, duckduckgo, deepl, notion, grammarly, translate.googleapis.com, etc.).
3. `tier.py`: a host goes into the **core** tier if any of these is true:
   - It is in an AI-service list or the seed.
   - It is in laylavish/HPT/arter AND has an AI-named domain or an AI category (laylavish-only "AI content" sites with no AI signal go to extended).
   - It appears in two or more independent sources.
   - Its directory description matches a strong gen-AI category regex (chatbot/LLM, companion, deepfake/NSFW gen, image gen, video gen, music/voice, writing/homework/humanizer, coding, agents/LLM infra, AI directory) **and** does not match a B2B/"merely uses AI" regex (sales, CRM, SEO, marketing, HR, finance, legal, health, support, email, meetings, e-commerce...).
   - It has an AI-named domain plus a strong category.
   Everything else that is weakly AI goes to `domains-extended.txt`.
4. `doh.py`: DNS-over-HTTPS A-record check (Cloudflare, falling back to Google) on 14,204 candidates. Results: 11,699 ok, 1,884 NXDOMAIN, 393 no A record, 222 SERVFAIL. Only `ok` hosts are kept.
5. `ns.py`: NS lookup on 5,338 registrable domains. 428 parked or for-sale domains were removed (afternic, sedo, bodis, parkingcrew, dns-parking, above, atom, parity, etc.).
6. Manual review of core hosts that came only from the markdown lists: removed robotics firms, research blogs on github.io, badges/CDNs, news sites, general dev tools (`build/manual_drop.txt`).

No domains were invented. Every entry comes from a published source or the hand seed, and all were DNS-validated. (Seed entries that failed DNS or turned out parked were dropped automatically.)

## Run 2 (2026-11-02) — video/image expansion
Harvested AI video/image directories, roundups, GitHub awesome lists, SimilarSites lookalikes of known generators, and related NSFW/avatar lists. Homepage-fetched and content-classified candidates; DoH liveness + NS parked checks. Additions-only file: `new-domains-run2.txt` (7,240). User-reported gaps included: veed.io, elements.envato.com, easemate.ai, vid.ai, studio.abacus.ai, vidrush.ai, videogenai.app.


## Run 3 (2026-11-02) — adult / image / video expansion
Homepage-verified harvest from NSFW AI directories, undress/nudify lists, AIToolNet, Dang.ai, SimilarSites lookalikes, CommonCrawl keyword mining, and urlscan. DoH liveness + NS parked filtering. Additions: `new-domains-run3.txt` (7060). User-reported gaps included (script-checked). `gamegamblings.com` verified as AI adult video gallery and included.
