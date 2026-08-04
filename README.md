# Taddy (taddy)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Taddy is a **GraphQL API** for podcasts and comics. It gives developers access to over 4 million podcasts and 200 million episodes, plus real-time full-text search, automatically generated episode transcripts, chapters, iTunes metadata, daily top charts, webcomic and creator data, and webhook notifications for new or updated content. Every operation is an HTTP `POST` to a single GraphQL endpoint at `https://api.taddy.org`, authenticated with `X-USER-ID` and `X-API-KEY` headers.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/taddy/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/taddy/refs/heads/main/apis.yml)

## Tags

- Podcasts
- Comics
- GraphQL
- Search
- Transcripts
- Media
- Content

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## GraphQL

Taddy is a native GraphQL API — there is no REST surface, so this repo uses `graphql/` rather than `openapi/`.

- **Endpoint:** `https://api.taddy.org` (POST)
- **Headers:** `Content-Type: application/json`, `X-USER-ID`, `X-API-KEY`
- **Schema (authoritative):** [https://ax0.taddy.org/docs/schema.graphql](https://ax0.taddy.org/docs/schema.graphql)
- **Local docs:** [graphql/taddy-graphql.md](graphql/taddy-graphql.md) — [GraphQL SDL](graphql/taddy-schema.graphql)

## APIs

The single Taddy GraphQL schema is grouped below into logical APIs by operation.

### Taddy Podcast Search API

Blazing-fast full-text `search` across all 4M+ podcasts and 200M+ episodes, with filters for country, genre, language, publish date, and whether a transcript is available, sortable by exactness or popularity.

- **Human URL:** [https://taddy.org/developers/podcast-api/search](https://taddy.org/developers/podcast-api/search)
- **Base URL:** `https://api.taddy.org`

### Taddy Podcast Series & Episodes API

Look up podcast series and episodes via `getPodcastSeries`, `getPodcastEpisode`, `getMultiplePodcastSeries`, `getMultiplePodcastEpisodes`, and `getLatestPodcastEpisodes`, keyed by Taddy uuid, name, RSS URL, or iTunes ID.

- **Human URL:** [https://taddy.org/developers/podcast-api/get-podcast-series](https://taddy.org/developers/podcast-api/get-podcast-series)
- **Base URL:** `https://api.taddy.org`

### Taddy Episode Transcripts API

Retrieve episode transcripts with `getEpisodeTranscript` and the `transcriptWithSpeakersAndTimecodes` field — per-line text, speaker names, and start/end timecodes — backed by Taddy's automatic transcription of episodes that lack a publisher transcript.

- **Human URL:** [https://taddy.org/developers/podcast-api/episode-transcripts](https://taddy.org/developers/podcast-api/episode-transcripts)
- **Base URL:** `https://api.taddy.org`

### Taddy Episode Chapters API

Fetch chapter markers for an episode via `getEpisodeChapters` and the `chapters` field.

- **Human URL:** [https://taddy.org/developers/podcast-api](https://taddy.org/developers/podcast-api)
- **Base URL:** `https://api.taddy.org`

### Taddy iTunes Info API

Resolve Apple Podcasts / iTunes metadata for a podcast with `getItunesInfo` and the `itunesInfo` field.

- **Human URL:** [https://taddy.org/developers/podcast-api](https://taddy.org/developers/podcast-api)
- **Base URL:** `https://api.taddy.org`

### Taddy Top Charts & Popular API

Retrieve daily top charts and popular content with `getTopChartsByCountry`, `getTopChartsByGenre`, and `getPopularContent`.

- **Human URL:** [https://taddy.org/developers/podcast-api](https://taddy.org/developers/podcast-api)
- **Base URL:** `https://api.taddy.org`

### Taddy Comics & Creators API

Access webcomic and creator data via `getComicSeries`, `getComicIssue`, `getCreator`, and `getMultipleCreators`.

- **Human URL:** [https://taddy.org/developers](https://taddy.org/developers)
- **Base URL:** `https://api.taddy.org`

### Taddy Webhooks API

Real-time webhook notifications for new and updated content (`podcast.created`, `podcast.updated`, `podcast.deleted`, `podcast.new_episodes`, plus creator/creatorcontent events). Delivered as outbound HTTP POST callbacks; available on the Business tier and above.

- **Human URL:** [https://taddy.org/developers](https://taddy.org/developers)
- **Base URL:** `https://api.taddy.org`

### Taddy Account & Usage API

Monitor plan consumption with `getApiRequestsRemaining` (monthly API request quota) and `getTranscriptCreditsRemaining` (monthly transcript credits).

- **Human URL:** [https://taddy.org/developers/intro-to-taddy-graphql-api](https://taddy.org/developers/intro-to-taddy-graphql-api)
- **Base URL:** `https://api.taddy.org`

## Collections

- [Postman Collection](collections/taddy.postman_collection.json) — GraphQL POST requests
- [Open Collection](collections/taddy.opencollection.json) — GraphQL POST requests

## Plans & Pricing

Request-metered monthly tiers: **Free** ($0, 500 requests/mo), **Pro** ($75/mo, 100k requests + 100 transcripts), **Business** ($150/mo, 350k requests + 2,000 transcripts + webhooks). Extra transcripts sell in 3,000-credit packs ($75/mo), and higher request volumes (e.g. 1M/mo for $250) are available on request. Notably, Taddy permits storing/caching API data on your own servers.

- [Plans](plans/taddy-plans-pricing.yml)
- [Rate Limits](rate-limits/taddy-rate-limits.yml)
- [Fin Ops](finops/taddy-finops.yml)

## Common Properties

- [GitHub Organization](https://github.com/taddyorg)
- [LinkedIn](https://www.linkedin.com/company/taddy)
- [Website](https://taddy.org/)
- [Documentation](https://taddy.org/developers)
- [Plans](plans/taddy-plans-pricing.yml)
- [Rate Limits](rate-limits/taddy-rate-limits.yml)
- [Fin Ops](finops/taddy-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
