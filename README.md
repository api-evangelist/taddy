# Taddy

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Taddy is a GraphQL API for podcasts and comics, giving developers access to over 4 million podcasts and 200 million episodes, plus real-time full-text search, automatically generated episode transcripts, chapters, iTunes metadata, daily top charts, webcomic and creator data, and webhook notifications for new or updated content. All queries hit a single GraphQL endpoint at https://api.taddy.org authenticated with X-USER-ID and X-API-KEY headers.

**Areas:** Podcasts · Comics · GraphQL · Search · Transcripts · Media · Content · Audio · Webhook · Episodes

## Taddy on APIs.io

Everything profiled for Taddy is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/taddy/](https://apis.io/providers/taddy/)** — or go straight to one of the APIs or properties below.

### APIs (9)

- [Taddy Podcast Search API](https://apis.io/apis/taddy/taddy-podcast-search-api/) — Blazing-fast full-text `search` query across all 4M+ podcasts and 200M+ episodes, with filters for country, genre, language, publish date, and whether a…
- [Taddy Podcast Series & Episodes API](https://apis.io/apis/taddy/taddy-podcast-series-episodes-api/) — Look up podcast series and episodes via getPodcastSeries, getPodcastEpisode, getMultiplePodcastSeries, getMultiplePodcastEpisodes, and…
- [Taddy Episode Transcripts API](https://apis.io/apis/taddy/taddy-transcripts-api/) — Retrieve episode transcripts with getEpisodeTranscript and the transcriptWithSpeakersAndTimecodes field, including per-line text, speaker names, and…
- [Taddy Episode Chapters API](https://apis.io/apis/taddy/taddy-episode-chapters-api/) — Fetch chapter markers for an episode via getEpisodeChapters and the chapters field, returning chapter titles and start timecodes for chapterized podcasts.
- [Taddy iTunes Info API](https://apis.io/apis/taddy/taddy-itunes-info-api/) — Resolve Apple Podcasts / iTunes metadata for a podcast with getItunesInfo and the itunesInfo field, including iTunes ID, base artwork URL, categories, and…
- [Taddy Top Charts & Popular API](https://apis.io/apis/taddy/taddy-top-charts-popular-api/) — Retrieve daily top charts and popular content with getTopChartsByCountry, getTopChartsByGenre, and getPopularContent, filterable by country, genre, and…
- [Taddy Comics & Creators API](https://apis.io/apis/taddy/taddy-comics-creators-api/) — Access webcomic and creator data via getComicSeries, getComicIssue, getCreator, and getMultipleCreators, covering comic series, individual issues, and the…
- [Taddy Webhooks API](https://apis.io/apis/taddy/taddy-webhooks-api/) — Real-time webhook notifications for new and updated content, delivering events such as podcast.created, podcast.updated, podcast.deleted,…
- [Taddy Account & Usage API](https://apis.io/apis/taddy/taddy-account-usage-api/) — Monitor plan consumption with getApiRequestsRemaining (monthly API request quota) and getTranscriptCreditsRemaining (monthly transcript credit allocation).

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### GraphQL (1)

GraphQL schemas.

- [Taddy GraphQL API](https://apis.io/graphqls/taddy/taddy-graphql/)

#### Collections (1)

Postman and Open Collection request collections.

- [Taddy GraphQL API](https://apis.io/collections/taddy/open-taddy/)

#### Security (1)

Authentication, trust centre, and vulnerability disclosure.

- [Taddy Domain Security](https://apis.io/security/taddy/taddy-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Taddy Plans Pricing](https://apis.io/plans/taddy/taddy-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Taddy Rate Limits](https://apis.io/rate-limits/taddy/taddy-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Taddy Finops](https://apis.io/finops/taddy/taddy-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://taddy.org/)
- [Documentation](https://taddy.org/developers)
- [Blog](https://taddy.org/blog)
- [GitHub](https://github.com/taddyorg)

## API Evangelist rating

**Kin Score 21.3** — emerging · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 71.4 |
| Contract quality | 35.1 |
| Contract governance | 0.0 |
| Operational transparency | 10.5 |
| Developer ergonomics | 19.0 |
| Access clarity | 7.9 |

**Agent readiness 13.6** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | — |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | — |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 5.9** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/taddy/](https://apis.io/providers/taddy/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Taddy: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/taddy/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
