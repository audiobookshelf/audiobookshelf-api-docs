# Podcasts

## Create a Podcast

```shell
curl -X POST "https://abs.example.com/api/podcasts" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d $'{"libraryId": "lib_p9wkw2i85qy9oltijt", "folderId": "fol_crxarzs17jtw5k7ie9", "path": "/podcasts/Welcome to Night Vale", "media": {"metadata": {"title": "Welcome to Night Vale", "author": "Night Vale Presents", "description": "\\n      Twice-monthly community updates for the small desert town of Night Vale, where every conspiracy theory is true. Turn on your radio and hide. Never listened before? It\'s an ongoing radio show. Start with the current episode, and you\'ll catch on in no time. Or, go right to Episode 1 if you wanna binge-listen.\\n    ", "releaseDate": "2022-10-20T19:00:00Z", "genres": ["Science Fiction", "Podcasts", "Fiction"], "feedUrl": "http://feeds.nightvalepresents.com/welcometonightvalepodcast", "imageUrl": "https://is4-ssl.mzstatic.com/image/thumb/Podcasts125/v4/4a/31/35/4a3135d0-1fe7-a2d7-fb43-d182ec175402/mza_8232698753950666850.jpg/600x600bb.jpg", "itunesPageUrl": "https://podcasts.apple.com/us/podcast/welcome-to-night-vale/id536258179?uo=4", "itunesId": 536258179, "itunesArtistId": 718704794, "explicit": false, "language": null}}}'
```

> The above command returns JSON structured like this:

```json
{
  "id": "li_bufnnmp4y5o2gbbxfm",
  "ino": "652",
  "libraryId": "lib_p9wkw2i85qy9oltijt",
  "folderId": "fol_crxarzs17jtw5k7ie9",
  "path": "/podcasts/Welcome to Night Vale",
  "relPath": "Welcome to Night Vale",
  "isFile": false,
  "mtimeMs": 1668124892694,
  "ctimeMs": 1668124892694,
  "birthtimeMs": 1667326662083,
  "addedAt": 1667326662087,
  "updatedAt": 1668157565937,
  "lastScan": 1668234374487,
  "scanVersion": "2.2.2",
  "isMissing": false,
  "isInvalid": false,
  "mediaType": "podcast",
  "media": {
    "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
    "metadata": {
      "title": "Welcome to Night Vale",
      "titleIgnorePrefix": "Welcome to Night Vale",
      "author": "Night Vale Presents",
      "description": "\n      Twice-monthly community updates for the small desert town of Night Vale, where every conspiracy theory is true. Turn on your radio and hide. Never listened before? It's an ongoing radio show. Start with the current episode, and you'll catch on in no time. Or, go right to Episode 1 if you wanna binge-listen.\n    ",
      "releaseDate": "2022-10-20T19:00:00Z",
      "genres": [
        "Science Fiction",
        "Podcasts",
        "Fiction"
      ],
      "feedUrl": "http://feeds.nightvalepresents.com/welcometonightvalepodcast",
      "imageUrl": "https://is4-ssl.mzstatic.com/image/thumb/Podcasts125/v4/4a/31/35/4a3135d0-1fe7-a2d7-fb43-d182ec175402/mza_8232698753950666850.jpg/600x600bb.jpg",
      "itunesPageUrl": "https://podcasts.apple.com/us/podcast/welcome-to-night-vale/id536258179?uo=4",
      "itunesId": 536258179,
      "itunesArtistId": 718704794,
      "explicit": false,
      "language": null
    },
    "coverPath": "/metadata/items/li_bufnnmp4y5o2gbbxfm/cover.jpg",
    "tags": [],
    "episodes": [],
    "autoDownloadEpisodes": false,
    "autoDownloadSchedule": "0 * * * *",
    "lastEpisodeCheck": 1667326662087,
    "maxEpisodesToKeep": 0,
    "maxNewEpisodesToDownload": 3,
    "size": 52993
  },
  "libraryFiles": [
    {
      "ino": "10113",
      "metadata": {
        "filename": "cover.jpg",
        "ext": ".jpg",
        "path": "/podcasts/Welcome to Night Vale/cover.jpg",
        "relPath": "cover.jpg",
        "size": 52993,
        "mtimeMs": 1667326662178,
        "ctimeMs": 1667326662184,
        "birthtimeMs": 1667326662090
      },
      "addedAt": 1667327311529,
      "updatedAt": 1667327311529,
      "fileType": "image"
    }
  ],
  "size": 52993
}
```

This endpoint creates a podcast and returns it.

### HTTP Request

`POST http://abs.example.com/api/podcasts`

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`path` | String | The path of the new podcast library item on the server.
`folderId` | String | The ID of the folder to put the new podcast library item in.
`libraryId` | String | The ID of the library the new podcast item will belong to.
`media` | [New Podcast Parameters](#new-podcast-parameters) Object (See Below) | The created library item's podcast media.
`episodesToDownload` | Array of [Podcast Episode Parameters](#podcast-episode-parameters) (See Below) | Podcast episodes to download and add to the new podcast.

#### New Podcast Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`metadata` | [New Podcast Metadata Parameters](#new-podcast-metadata-parameters) Object (See Below) | See Below | The podcast's metadata.
`coverPath` | String or null | `null` | The absolute path on the server of the cover file.
`autoDownloadEpisodes` | Boolean | `false` | Whether the server will automatically download podcast episodes according to the schedule.
`autoDownloadSchedule` | String | The "Podcast Episode Schedule" server setting. | The [cron expression](https://en.wikipedia.org/wiki/Cron#CRON_expression) for when to automatically download new podcast episodes.

#### New Podcast Metadata Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`title` | String or null | `null` | The title of the podcast.
`author` | String or null | `null` | The author of the podcast.
`description` | String or null | `null` | The description for the podcast.
`releaseDate` | String or null | `null` | The release date of the podcast.
`genres` | Array of String | `[]` | The podcast's genres.
`feedUrl` | String or null | `null` | A URL of an RSS feed for the podcast.
`imageUrl` | String or null | `null` | A URL of a cover image for the podcast.
`itunesPageUrl` | String or null | `null` | A URL of an iTunes page for the podcast.
`itunesId` | Integer or null | `null` | The iTunes ID for the podcast.
`itunesArtistId` | Integer or null | `null` | The iTunes Artist ID for the author of the podcast.
`explicit` | Boolean | `false` | Whether to mark the podcast as explicit.
`language` | String or null | `null` | The language of the podcast.

#### Podcast Episode Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`season` | String | `''` | The season of the podcast episode, if known.
`episode` | String | `''` | The episode of the season of the podcast, if known.
`episodeType` | String | `''` | The type of episode that the podcast episode is.
`title` | String | `''` | The title of the podcast episode.
`subtitle` | String | `''` | The subtitle of the podcast episode.
`description` | String | `''` | A HTML encoded, description of the podcast episode.
`pubDate` | String | `''` | When the podcast episode was published.
`publishedAt` | Integer | `0` | The time (in ms since POSIX epoch) when the podcast episode was published.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Library Item Expanded](#library-item-expanded)
400 | Bad Request | The given library ID or folder ID does not exist, the podcast already exists, or the podcast's path is invalid. |
500 | Internal Server Error | An admin user is required to create podcasts. |


## Get a Podcast's Feed

```shell
curl -X POST "https://abs.example.com/api/podcasts/feed" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"rssFeed": "http://feeds.nightvalepresents.com/welcometonightvalepodcast"}'
```

> The above command returns JSON structured like this:

```json
{
  "podcast": {
    "metadata": {
      "image": "https://f.prxu.org/126/images/1f749c5d-c83a-4db9-8112-a3245da49c54/nightvalelogo-web4.jpg",
      "categories": [
        "Fiction:Science Fiction"
      ],
      "feedUrl": "http://feeds.nightvalepresents.com/welcometonightvalepodcast",
      "description": "\n      <p>Twice-monthly community updates for the small desert town of Night Vale, where every conspiracy theory is true. Turn on your radio and hide. Never listened before? It's an ongoing radio show. Start with the current episode, and you'll catch on in no time. Or, go right to Episode 1 if you wanna binge-listen.</p>\n    ",
      "descriptionPlain": "\n      Twice-monthly community updates for the small desert town of Night Vale, where every conspiracy theory is true. Turn on your radio and hide. Never listened before? It's an ongoing radio show. Start with the current episode, and you'll catch on in no time. Or, go right to Episode 1 if you wanna binge-listen.\n    ",
      "title": "Welcome to Night Vale",
      "language": "en",
      "explicit": "false",
      "author": "Night Vale Presents",
      "pubDate": "Thu, 17 Nov 2022 16:04:42 -0000",
      "link": "http://welcometonightvale.com"
    },
    "episodes": [
      ...,
      {
        "title": "1 - Pilot",
        "subtitle": "Pilot Episode. A new dog park opens in Night Vale. Carlos, a scientist, visits and discovers some interesting things. Seismic things. Plus, a helpful guide to surveillance helicopter-spotting. Weather: \"These and More Than These\" by Joseph Fink Music:...",
        "description": "\n        <p>Pilot Episode. A new dog park opens in Night Vale. Carlos, a scientist, visits and discovers some interesting things. Seismic things. Plus, a helpful guide to surveillance helicopter-spotting.</p>\n\n<p>Weather: \"These and More Than These\" by Joseph Fink</p>\n\n<p>Music: Disparition, <a target=\"_blank\">disparition.info</a></p>\n\n<p>Logo: Rob Wilson, <a target=\"_blank\">silastom.com</a></p>\n\n<p>Produced by Night Vale Presents. Written by Joseph Fink and Jeffrey Cranor. Narrated by Cecil Baldwin. More Info: <a target=\"_blank\">welcometonightvale.com</a>, and follow <a target=\"_blank\">@NightValeRadio</a> on Twitter or <a target=\"_blank\">Facebook</a>.</p>\n      ",
        "descriptionPlain": "\n        Pilot Episode. A new dog park opens in Night Vale. Carlos, a scientist, visits and discovers some interesting things. Seismic things. Plus, a helpful guide to surveillance helicopter-spotting.\n\nWeather: \"These and More Than These\" by Joseph Fink\n\nMusic: Disparition, disparition.info\n\nLogo: Rob Wilson, silastom.com\n\nProduced by Night Vale Presents. Written by Joseph Fink and Jeffrey Cranor. Narrated by Cecil Baldwin. More Info: welcometonightvale.com, and follow @NightValeRadio on Twitter or Facebook.\n      ",
        "pubDate": "Fri, 15 Jun 2012 12:00:00 -0000",
        "episodeType": "full",
        "season": "",
        "episode": "",
        "author": "",
        "duration": "21:02",
        "explicit": "",
        "publishedAt": 1339761600000,
        "enclosure": {
          "url": "https://www.podtrac.com/pts/redirect.mp3/dovetail.prxu.org/_/126/1fadf1ad-aad8-449f-843b-6e8bb6949622/1_Pilot.mp3",
          "type": "audio/mpeg",
          "length": "20588611"
        }
      },
      ...
    ]
  }
}
```

This endpoint takes a podcast's RSS feed and returns the feed's data.

### HTTP Request

`POST http://abs.example.com/api/podcasts/feed`

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`rssFeed` | String | A URL of an RSS feed for the podcast.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
400 | Bad Request | The `rssFeed` parameter is required. |
404 | Not Found | The podcast RSS feed request failed or had invalid response data. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`podcast` | [Podcast Feed](#podcast-feed) Object | The requested podcast feed data.


## Get Podcast Feeds from OPML

```shell
curl -X POST "https://abs.example.com/api/podcasts/opml" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d $'{"opmlText": "<?xml version=\'1.0\' encoding=\'UTF-8\' standalone=\'yes\' ?><opml version=\'1.0\'><head><title>Pocket Casts Feeds</title></head><body><outline type=\'rss\' text=\'Welcome to Night Vale\' xmlUrl=\'http://feeds.nightvalepresents.com/welcometonightvalepodcast\' /></body></opml>"}'
```

> The above command returns JSON structured like this:

```json
{
  "feeds": [
    {
      "metadata": {
        "image": "https://f.prxu.org/126/images/1f749c5d-c83a-4db9-8112-a3245da49c54/nightvalelogo-web4.jpg",
        "categories": [
          "Fiction:Science Fiction"
        ],
        "feedUrl": "http://feeds.nightvalepresents.com/welcometonightvalepodcast",
        "description": "\n      <p>Twice-monthly community updates for the small desert town of Night Vale, where every conspiracy theory is true. Turn on your radio and hide. Never listened before? It's an ongoing radio show. Start with the current episode, and you'll catch on in no time. Or, go right to Episode 1 if you wanna binge-listen.</p>\n    ",
        "descriptionPlain": "\n      Twice-monthly community updates for the small desert town of Night Vale, where every conspiracy theory is true. Turn on your radio and hide. Never listened before? It's an ongoing radio show. Start with the current episode, and you'll catch on in no time. Or, go right to Episode 1 if you wanna binge-listen.\n    ",
        "title": "Welcome to Night Vale",
        "language": "en",
        "explicit": "false",
        "author": "Night Vale Presents",
        "pubDate": "Thu, 17 Nov 2022 16:04:42 -0000",
        "link": "http://welcometonightvale.com"
      },
      "numEpisodes": 280
    }
  ]
}
```

This endpoint takes OPML text and returns the contained RSS feeds' data.

### HTTP Request

`POST http://abs.example.com/api/podcasts/opml`

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`opmlText` | String | OPML text containing podcast RSS feeds.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
400 | Bad Request | The `opmlText` parameter is required. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`feeds` | Array of [Podcast Feed Minimized](#podcast-feed-minimized) | The podcast feeds retrieved from the RSS feeds in the OPML text.

Or if there is an error (i.e. no RSS feeds were in the OPML text): 

Attribute | Type | Description
--------- | ---- | -----------
`error` | String | The error that occurred.
