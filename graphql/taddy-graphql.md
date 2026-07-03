# Taddy GraphQL API

Taddy is a **native GraphQL API** for podcasts and comics. It gives developers
access to over 4 million podcasts and 200 million episodes, real-time full-text
search, automatically generated episode transcripts, chapters, iTunes metadata,
daily top charts, webcomic and creator data, and webhook notifications for new
or updated content.

**Endpoint:** `https://api.taddy.org` (single GraphQL endpoint, POST only)
**Documentation:** https://taddy.org/developers
**Intro / Getting Started:** https://taddy.org/developers/intro-to-taddy-graphql-api
**Schema:** https://ax0.taddy.org/docs/schema.graphql

## Authentication

Every request is an HTTP `POST` to `https://api.taddy.org` with:

| Header | Value |
| --- | --- |
| `Content-Type` | `application/json` |
| `X-USER-ID` | Your Taddy user ID (from the developer dashboard) |
| `X-API-KEY` | Your Taddy API key |

```bash
curl -s https://api.taddy.org \
  -H "Content-Type: application/json" \
  -H "X-USER-ID: YOUR_USER_ID" \
  -H "X-API-KEY: YOUR_API_KEY" \
  -d '{"query":"{ getPodcastSeries(name:\"The Daily\"){ uuid name itunesId totalEpisodesCount } }"}'
```

## Logical APIs (GraphQL operation groups)

Taddy exposes one schema; below the operations are grouped into the logical
APIs used in this catalog.

### 1. Podcast Search API

Full-text `search` across podcasts, episodes, comics, and creators.

```graphql
{
  search(
    term: "true crime"
    filterForTypes: [PODCASTSERIES]
    filterForCountries: [UNITED_STATES_OF_AMERICA]
    filterForGenres: [PODCASTSERIES_TRUE_CRIME]
    filterForHasTranscript: true
    sortBy: POPULARITY
    page: 1
    limitPerPage: 25
  ) {
    searchId
    podcastSeries {
      uuid
      name
      description
      imageUrl
      totalEpisodesCount
    }
  }
}
```

### 2. Podcast Series & Episodes API

```graphql
# Look up a series by name, uuid, rssUrl, or itunesId
{
  getPodcastSeries(name: "This American Life") {
    uuid
    name
    itunesId
    rssUrl
    description
    imageUrl
    language
    contentType
    totalEpisodesCount
    popularityRank
    episodes(sortOrder: LATEST, limitPerPage: 10) {
      uuid
      name
      datePublished
      audioUrl
      duration
    }
  }
}

# A single episode by uuid, or by guid + seriesUuidForLookup
{
  getPodcastEpisode(uuid: "d94e40cc-5b0e-4a6e-9a3f-2e1a3fd5e111") {
    uuid
    name
    datePublished
    audioUrl
    duration
    taddyTranscribeStatus
  }
}

# Batch lookups (up to 25 uuids) and latest episodes across many series
{
  getMultiplePodcastSeries(uuids: ["...", "..."]) { uuid name }
}
{
  getMultiplePodcastEpisodes(uuids: ["...", "..."]) { uuid name }
}
{
  getLatestPodcastEpisodes(uuids: ["...", "..."], page: 1, limitPerPage: 20) {
    uuid
    name
    datePublished
  }
}
```

### 3. Episode Transcripts API

Only ~1% of podcasts publish their own transcript, so Taddy auto-transcribes
episodes on demand.

```graphql
{
  getEpisodeTranscript(uuid: "d94e40cc-5b0e-4a6e-9a3f-2e1a3fd5e111") {
    id
    text
    speaker
    startTimecode
    endTimecode
  }
}
```

The same data is reachable from an episode via
`transcriptWithSpeakersAndTimecodes` and `transcriptUrlsWithDetails`.

### 4. Episode Chapters API

```graphql
{
  getEpisodeChapters(uuid: "d94e40cc-5b0e-4a6e-9a3f-2e1a3fd5e111") {
    id
    title
    startTimecode
  }
}
```

### 5. iTunes Info API

```graphql
{
  getItunesInfo(uuid: "podcast-uuid") {
    uuid
    itunesId
    baseArtworkUrl
    categories
    contentAdvisory
  }
}
```

### 6. Top Charts & Popular API

```graphql
{
  getTopChartsByCountry(
    taddyType: PODCASTSERIES
    country: UNITED_STATES_OF_AMERICA
    page: 1
    limitPerPage: 25
  ) {
    topChartsId
    podcastSeries { uuid name }
  }
}

{
  getTopChartsByGenre(
    taddyType: PODCASTSERIES
    genre: PODCASTSERIES_TECHNOLOGY
    page: 1
    limitPerPage: 25
  ) {
    topChartsId
    podcastSeries { uuid name }
  }
}

{
  getPopularContent(
    taddyType: PODCASTSERIES
    filterByLanguage: ENGLISH
    filterByGenres: [PODCASTSERIES_NEWS]
    page: 1
    limitPerPage: 25
  ) {
    popularityId
    podcastSeries { uuid name }
  }
}
```

### 7. Comics & Creators API

```graphql
{
  getComicSeries(name: "Adventures of God") {
    uuid
    name
    description
    coverImageUrl
    issues { uuid name }
  }
}

{
  getComicIssue(uuid: "issue-uuid") {
    uuid
    name
    datePublished
  }
}

{
  getCreator(name: "Some Creator") {
    uuid
    name
    bio
    avatarImageUrl
    totalContentCount
    content { ... on ComicSeries { uuid name } }
  }
}

{
  getMultipleCreators(uuids: ["...", "..."]) { uuid name }
}
```

### 8. Webhooks API

Taddy pushes real-time events to your registered webhook URL (configured in the
developer dashboard, available on the Business tier and above). Event types
include:

- `podcast.created`, `podcast.updated`, `podcast.deleted`, `podcast.new_episodes`
- `creator.created`, `creator.updated`, `creator.deleted`, `creator.new_content_released`
- `creatorcontent.created`, `creatorcontent.updated`, `creatorcontent.deleted`

Webhooks are HTTP `POST` callbacks from Taddy to your endpoint. They are not a
WebSocket transport — see `../review.yml`.

### 9. Account & Usage API

```graphql
{ getApiRequestsRemaining }
{ getTranscriptCreditsRemaining }
```

## Notes on modeling

- Taddy's GraphQL schema is real and public; the queries above are grounded in
  the Taddy developer docs. Field selections are illustrative subsets of the
  documented types (see `taddy-schema.graphql`).
- Enum member spellings (e.g. genre and country enum values) follow Taddy's
  documented `PODCASTSERIES_*` genre and ISO-country enum conventions; confirm
  exact enum members against `https://ax0.taddy.org/docs/schema.graphql`.
