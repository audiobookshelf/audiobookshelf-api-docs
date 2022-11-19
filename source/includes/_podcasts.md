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
`enclosure` | [Podcast Episode Enclosure](#podcast-episode-enclosure) Object or null | `null` | The podcast episode download information.
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


## Check for New Podcast Episodes

```shell
curl "https://abs.example.com/api/podcasts/li_bufnnmp4y5o2gbbxfm/checknew" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "episodes": [
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
    }
  ]
}
```

This endpoint checks for new episodes for a podcast, which the server downloads, and returns the podcast episode feed data.

### HTTP Request

`GET http://abs.example.com/api/podcasts/<ID>/checknew`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the podcast library item.

### Optional Query Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`limit` | Integer | `3` | The maximum number of new episodes to download. If `0`, all episodes will be downloaded.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
403 | Forbidden | The user is not allowed to access the library item. An admin user is required to check for new podcast episodes. |
404 | Not Found | No library item with the given ID exists. |
500 | Internal Server Error | The library item is not a podcast. The podcast must have an RSS feed URL. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`episodes` | Array of [Podcast Feed Episode](#podcast-feed-episode) | The new podcast episodes that will be downloaded.


## Get Podcast Episode Downloads

```shell
curl "https://abs.example.com/api/podcasts/li_bufnnmp4y5o2gbbxfm/downloads" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "downloads": [
    {
      "id": "epdl_pgv4d47j6dtqpk4r0v",
      "episodeDisplayTitle": "2 - Glow Cloud",
      "url": "https://www.podtrac.com/pts/redirect.mp3/dovetail.prxu.org/_/126/cb1dd91f-5d8d-42e9-ba22-14ff335d2cbb/2_Glow_Cloud.mp3",
      "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
      "isDownloading": false,
      "isFinished": false,
      "failed": false,
      "startedAt": null,
      "createdAt": 1668122813409,
      "finishedAt": null
    }
  ]
}
```

This endpoint retrieves the episodes currently in the download queue for the podcast.

### HTTP Request

`GET http://abs.example.com/api/podcasts/<ID>/downloads`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the podcast library item.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
403 | Forbidden | The user is not allowed to access the library item. |
404 | Not Found | No library item with the given ID exists. |
500 | Internal Server Error | The library item is not a podcast. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`downloads` | Array of [Podcast Episode Download](#podcast-episode-download) | The episodes currently in the download queue for the podcast.


## Clear a Podcast's Episode Download Queue

```shell
curl "https://abs.example.com/api/podcasts/li_bufnnmp4y5o2gbbxfm/clear-queue" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint clears a podcast's episode download queue.

### HTTP Request

`GET http://abs.example.com/api/podcasts/<ID>/clear-queue`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the podcast library item.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
403 | Forbidden | The user is not allowed to access the library item. An admin user is required to clear a podcast's episode download queue.
404 | Not Found | No library item with the given ID exists.
500 | Internal Server Error | The library item is not a podcast.


## Search a Podcast's Feed for Episodes

```shell
curl "https://abs.example.com/api/podcasts/li_bufnnmp4y5o2gbbxfm/search-episode?title=Pilot" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "episodes": [
    {
      "episode": {
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
      "levenshtein": 4
    }
  ]
}
```

This endpoint searches a podcast's feed for an episode with the given title.

### HTTP Request

`GET http://abs.example.com/api/podcasts/<ID>/search-episode`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the podcast library item.

### Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
`title` | String | The podcast episode title to search for.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
403 | Forbidden | The user is not allowed to access the library item. |
404 | Not Found | No library item with the given ID exists. |
500 | Internal Server Error | The library item is not a podcast. The podcast must have an RSS feed URL. `title` is a required parameter. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`episodes` | Array of [Podcast Search Episode](#podcast-search-episode) (See Below) | The matching podcast episodes.

#### Podcast Search Episode

Attribute | Type | Description
--------- | ---- | -----------
`episode` | [Podcast Feed Episode](#podcast-feed-episode) Object | The podcast episode feed data.
`levenshtein` | Integer | The [Levenshtein distance](https://en.wikipedia.org/wiki/Levenshtein_distance) between the search title and the podcast episode's title.


## Download Podcast Episodes

```shell
curl -X POST "https://abs.example.com/api/podcasts/li_bufnnmp4y5o2gbbxfm/download-episodes" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '[{"episodeType": "full", "title": "2 - Glow Cloud", "subtitle": "A mysterious, glowing cloud makes its way across Night Vale. Plus, new Boy Scouts hierarchy, community events calendar, and a PTA bake sale for a great cause! Weather: \"The Bus is Late\" by Satellite High, satellite-high.com Music: Disparition,...", "description": "\n        <p>A mysterious, glowing cloud makes its way across Night Vale. Plus, new Boy Scouts hierarchy, community events calendar, and a PTA bake sale for a great cause!</p>\n\n<p>Weather: \"The Bus is Late\" by Satellite High, <a target=\"_blank\">satellite-high.com</a></p>\n\n<p>Music: Disparition, <a target=\"_blank\">disparition.info</a></p>\n\n<p>Logo: Rob Wilson, <a target=\"_blank\">silastom.com</a></p>\n\n<p>Produced by Night Vale Presents. Written by Joseph Fink and Jeffrey Cranor. Narrated by Cecil Baldwin. More Info: <a target=\"_blank\">welcometonightvale.com</a>, and follow <a target=\"_blank\">@NightValeRadio</a> on Twitter or <a target=\"_blank\">Facebook</a>.</p>\n      ", "enclosure": {"url": "https://www.podtrac.com/pts/redirect.mp3/dovetail.prxu.org/_/126/cb1dd91f-5d8d-42e9-ba22-14ff335d2cbb/2_Glow_Cloud.mp3", "type": "audio/mpeg", "length": "19937018"}, "pubDate": "Sun, 01 Jul 2012 12:00:00 -0000", "publishedAt": 1341144000000}]'
```

This endpoint downloads new episodes for a podcast to the server.

### HTTP Request

`POST http://abs.example.com/api/podcasts/<ID>/download-episodes`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the podcast library item.

### Parameters

Provided an array of objects with the following parameters for each episode to download.

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`season` | String | `''` | The season of the podcast episode, if known.
`episode` | String | `''` | The episode of the season of the podcast, if known.
`episodeType` | String | `''` | The type of episode that the podcast episode is.
`title` | String | `''` | The title of the podcast episode.
`subtitle` | String | `''` | The subtitle of the podcast episode.
`description` | String | `''` | A HTML encoded, description of the podcast episode.
`enclosure` | [Podcast Episode Enclosure](#podcast-episode-enclosure) Object or null | `null` | The podcast episode download information.
`pubDate` | String | `''` | When the podcast episode was published.
`publishedAt` | Integer | `0` | The time (in ms since POSIX epoch) when the podcast episode was published.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
400 | Bad Request | The provided array must have a non-zero length.
403 | Forbidden | The user is not allowed to access the library item. An admin user is required to download new podcast episodes.
404 | Not Found | No library item with the given ID exists.
500 | Internal Server Error | The library item is not a podcast.


## Update a Podcast Episode

```shell
curl -X PATCH "https://abs.example.com/api/podcasts/li_bufnnmp4y5o2gbbxfm/episode/ep_lh6ko39pumnrma3dhv" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"subtitle": "A really cool podcast episode."}'
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
  "updatedAt": 1668853355724,
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
    "episodes": [
      {
        "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
        "id": "ep_lh6ko39pumnrma3dhv",
        "index": 3,
        "season": "",
        "episode": "",
        "episodeType": "full",
        "title": "1 - Pilot",
        "subtitle": "A really cool podcast episode.",
        "description": "<div><br>Pilot Episode. A new dog park opens in Night Vale. Carlos, a scientist, visits and discovers some interesting things. Seismic things. Plus, a helpful guide to surveillance helicopter-spotting.<br><br></div><div><br>Weather: \"These and More Than These\" by Joseph Fink<br><br></div><div><br>Music: Disparition, disparition.info<br><br></div><div><br>Logo: Rob Wilson, silastom.com<br><br></div><div><br>Produced by Night Vale Presents. Written by Joseph Fink and Jeffrey Cranor. Narrated by Cecil Baldwin. More Info: welcometonightvale.com, and follow @NightValeRadio on Twitter or Facebook.<br><br></div>",
        "enclosure": {
          "url": "https://www.podtrac.com/pts/redirect.mp3/dovetail.prxu.org/_/126/1fadf1ad-aad8-449f-843b-6e8bb6949622/1_Pilot.mp3",
          "type": "audio/mpeg",
          "length": "20588611"
        },
        "pubDate": "Fri, 15 Jun 2012 12:00:00 -0000",
        "audioFile": {
          "index": 1,
          "ino": "22587",
          "metadata": {
            "filename": "1 - Pilot.mp3",
            "ext": ".mp3",
            "path": "/podcasts/Welcome to Night Vale/1 - Pilot.mp3",
            "relPath": "1 - Pilot.mp3",
            "size": 23653735,
            "mtimeMs": 1667326682557,
            "ctimeMs": 1667326682557,
            "birthtimeMs": 1667326679508
          },
          "addedAt": 1667326682605,
          "updatedAt": 1668234380150,
          "trackNumFromMeta": null,
          "discNumFromMeta": null,
          "trackNumFromFilename": null,
          "discNumFromFilename": null,
          "manuallyVerified": false,
          "invalid": false,
          "exclude": false,
          "error": null,
          "format": "MP2/3 (MPEG audio layer 2/3)",
          "duration": 1454.18449,
          "bitRate": 128000,
          "language": null,
          "codec": "mp3",
          "timeBase": "1/14112000",
          "channels": 2,
          "channelLayout": "stereo",
          "chapters": [],
          "embeddedCoverArt": "mjpeg",
          "metaTags": {
            "tagAlbum": "Welcome to Night Vale",
            "tagArtist": "Night Vale Presents",
            "tagGenre": "Podcast",
            "tagTitle": "1 - Pilot",
            "tagDate": "2012",
            "tagEncoder": "Lavf58.45.100"
          },
          "mimeType": "audio/mpeg"
        },
        "audioTrack": {
          "index": 1,
          "startOffset": 0,
          "duration": 1454.18449,
          "title": "1 - Pilot.mp3",
          "contentUrl": "/s/item/li_bufnnmp4y5o2gbbxfm/1 - Pilot.mp3",
          "mimeType": "audio/mpeg",
          "metadata": {
            "filename": "1 - Pilot.mp3",
            "ext": ".mp3",
            "path": "/podcasts/Welcome to Night Vale/1 - Pilot.mp3",
            "relPath": "1 - Pilot.mp3",
            "size": 23653735,
            "mtimeMs": 1667326682557,
            "ctimeMs": 1667326682557,
            "birthtimeMs": 1667326679508
          }
        },
        "publishedAt": 1339761600000,
        "addedAt": 1667326679503,
        "updatedAt": 1667428186431,
        "duration": 1454.18449,
        "size": 23653735
      }
    ],
    "autoDownloadEpisodes": false,
    "autoDownloadSchedule": "0 0 * * 1",
    "lastEpisodeCheck": 1667326662087,
    "maxEpisodesToKeep": 0,
    "maxNewEpisodesToDownload": 3,
    "size": 23653735
  },
  "libraryFiles": [
    {
      "ino": "22587",
      "metadata": {
        "filename": "1 - Pilot.mp3",
        "ext": ".mp3",
        "path": "/podcasts/Welcome to Night Vale/1 - Pilot.mp3",
        "relPath": "1 - Pilot.mp3",
        "size": 23653735,
        "mtimeMs": 1667326682557,
        "ctimeMs": 1667326682557,
        "birthtimeMs": 1667326679508
      },
      "addedAt": 1667326682561,
      "updatedAt": 1667326682561,
      "fileType": "audio"
    },
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
  "size": 23706728
}
```

This endpoint updates a podcast episode and returns the library item.

### HTTP Request

`PATCH http://abs.example.com/api/podcasts/<ID>/episode/<EpisodeID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the podcast library item.
EpisodeID | The ID of the podcast episode.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`index` | Integer | The index of the podcast episode.
`season` | String | The season of the podcast episode, if known.
`episode` | String | The episode of the season of the podcast, if known.
`episodeType` | String | The type of episode that the podcast episode is.
`title` | String | The title of the podcast episode.
`subtitle` | String | The subtitle of the podcast episode.
`description` | String | A HTML encoded, description of the podcast episode.
`enclosure` | [Podcast Episode Enclosure](#podcast-episode-enclosure) Object | The podcast episode download information.
`pubDate` | String | When the podcast episode was published.
`audioFile` | [Audio File](#audio-file) Object | The audio file for the podcast episode.
`publishedAt` | Integer | The time (in ms since POSIX epoch) when the podcast episode was published.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Library Item Expanded](#library-item-expanded)
403 | Forbidden | The user is not allowed to access the library item. A user with update permissions is required to update podcast episodes. |
404 | Not Found | No library item with the given ID exists, or no episode with the given ID exists. |
500 | Internal Server Error | The library item is not a podcast. |


## Delete a Podcast Episode

```shell
curl -X DELETE "https://abs.example.com/api/podcasts/li_bufnnmp4y5o2gbbxfm/episode/ep_lh6ko39pumnrma3dhv?hard=1" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
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
  "updatedAt": 1668853355724,
  "lastScan": 1668234374487,
  "scanVersion": "2.2.2",
  "isMissing": false,
  "isInvalid": false,
  "mediaType": "podcast",
  "media": {
    "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
    "metadata": {
      "title": "Welcome to Night Vale",
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
    "autoDownloadSchedule": "0 0 * * 1",
    "lastEpisodeCheck": 1667326662087,
    "maxEpisodesToKeep": 0,
    "maxNewEpisodesToDownload": 3
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
  ]
}
```

This endpoint deletes a podcast episode from the database. If providing the `hard` parameter, the file will be deleted as well.

### HTTP Request

`PATCH http://abs.example.com/api/podcasts/<ID>/episode/<EpisodeID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the podcast library item.
EpisodeID | The ID of the podcast episode.

### Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
`hard` | Binary | Whether to delete the podcast episode files from the server. `0` for false, `1` for true.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Library Item](#library-item)
403 | Forbidden | The user is not allowed to access the library item. A user with delete permissions is required to delete podcast episodes. |
404 | Not Found | No library item with the given ID exists, or no episode with the given ID exists. |
500 | Internal Server Error | The library item is not a podcast. |
