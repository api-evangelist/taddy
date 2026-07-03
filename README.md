# Taddy (taddy)

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
