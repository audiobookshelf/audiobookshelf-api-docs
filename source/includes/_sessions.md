# Sessions

## Get All Sessions

```shell
curl "https://abs.example.com/api/sessions?user=root&itemsPerPage=1" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "total": 37,
  "numPages": 37,
  "page": 0,
  "itemsPerPage": 1,
  "sessions": [
    {
      "id": "play_4oq00chunexu9s03jw",
      "userId": "root",
      "libraryId": "lib_p9wkw2i85qy9oltijt",
      "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
      "episodeId": "ep_lh6ko39pumnrma3dhv",
      "mediaType": "podcast",
      "mediaMetadata": {
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
      "chapters": [],
      "displayTitle": "1 - Pilot",
      "displayAuthor": "Night Vale Presents",
      "coverPath": "/metadata/items/li_bufnnmp4y5o2gbbxfm/cover.jpg",
      "duration": 1454.18449,
      "playMethod": 0,
      "mediaPlayer": "html5",
      "deviceInfo": {
        "ipAddress": "192.168.1.118",
        "browserName": "Firefox",
        "browserVersion": "106.0",
        "osName": "Linux",
        "osVersion": "x86_64",
        "serverVersion": "2.2.3"
      },
      "date": "2022-11-13",
      "dayOfWeek": "Sunday",
      "timeListening": 15,
      "startTime": 596.779402,
      "currentTime": 611.590717,
      "startedAt": 1668330137087,
      "updatedAt": 1668330152157
    }
  ],
  "userFilter": "root"
}
```

This endpoint retrieves all listening sessions.

### HTTP Request

`GET https://abs.example.com/api/sessions`

### Optional Query Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`user` | String | | The ID of the user to filter listening sessions by.
`itemsPerPage` | Integer | `10` | The number of listening sessions to retrieve per page.
`page` | Integer | `0` | The page (0 indexed) to retrieve.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
404 | Not Found | An admin user is required to get all sessions. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`total` | Integer | The total number of listening sessions.
`numPages` | Integer | The total number of pages when using this `itemsPerPage` limit.
`itemsPerPage` | Integer | The provided `itemsPerPage` parameter.
`sessions` | Array of [Playback Session](#playback-session) | The requested listening sessions. If `user` was *not* provided, then the sessions will have an extra attribute, `user`, listed below.
`userFilter` | String | If provided, the `user` parameter.

#### Extra Attribute

Attribute | Type | Description
--------- | ---- | -----------
`user` | [Session User](#session-user) Object (See Below) | The user the playback session is for.

#### Session User

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the user.
`username` | String | The username of the user.


## Delete a Session

```shell
curl -X DELETE "https://abs.example.com/api/sessions/play_4oq00chunexu9s03jw" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint deletes a listening session.

### HTTP Request

`DELETE http://abs.example.com/api/sessions/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the listening session.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
403 | Forbidden | A user with delete permissions is required to delete sessions.
404 | Not Found | No session with provided ID exists.


## Sync a Local Session

```shell
curl -X POST "https://abs.example.com/api/session/local" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d $'{"id": "play_local_i00492kps6ow4axlvq", "userId": "root", "libraryId": "lib_p9wkw2i85qy9oltijt", "libraryItemId": "li_bufnnmp4y5o2gbbxfm", "episodeId": "ep_lh6ko39pumnrma3dhv", "mediaType": "podcast", "mediaMetadata": {"title": "Welcome to Night Vale", "author": "Night Vale Presents", "description": "\\n      Twice-monthly community updates for the small desert town of Night Vale, where every conspiracy theory is true. Turn on your radio and hide. Never listened before? It\'s an ongoing radio show. Start with the current episode, and you\'ll catch on in no time. Or, go right to Episode 1 if you wanna binge-listen.\\n    ", "releaseDate": "2022-10-20T19:00:00Z", "genres": ["Science Fiction", "Podcasts", "Fiction"], "feedUrl": "http://feeds.nightvalepresents.com/welcometonightvalepodcast", "imageUrl": "https://is4-ssl.mzstatic.com/image/thumb/Podcasts125/v4/4a/31/35/4a3135d0-1fe7-a2d7-fb43-d182ec175402/mza_8232698753950666850.jpg/600x600bb.jpg", "itunesPageUrl": "https://podcasts.apple.com/us/podcast/welcome-to-night-vale/id536258179?uo=4", "itunesId": 536258179, "itunesArtistId": 718704794, "explicit": false, "language": null}, "chapters": [], "displayTitle": "1 - Pilot", "displayAuthor": "Night Vale Presents", "coverPath": "/metadata/items/li_bufnnmp4y5o2gbbxfm/cover.jpg", "duration": 1454.18449, "playMethod": 0, "mediaPlayer": "html5", "deviceInfo": {"ipAddress": "192.168.1.118", "browserName": "Firefox", "browserVersion": "106.0", "osName": "Linux", "osVersion": "x86_64", "serverVersion": "2.2.4"}, "date": "2022-11-16", "dayOfWeek": "Wednesday", "timeListening": 20, "startTime": 616.291374, "currentTime": 636.09262, "startedAt": 1668580247687, "updatedAt": 1668580396623}'
```

This endpoint updates a local listening session on the server.

### HTTP Request

`POST http://abs.example.com/api/session/local`

### Parameters

Provide the local [Playback Session](#playback-session) as the body.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
500 | Internal Server Error | Either the local session is already syncing, or the library item was not found.


## Sync Local Sessions

```shell
curl -X POST "https://abs.example.com/api/session/local-all" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d $'{"sessions": [{"id": "play_local_i00492kps6ow4axlvq", "userId": "root", "libraryId": "lib_p9wkw2i85qy9oltijt", "libraryItemId": "li_bufnnmp4y5o2gbbxfm", "episodeId": "ep_lh6ko39pumnrma3dhv", "mediaType": "podcast", "mediaMetadata": {"title": "Welcome to Night Vale", "author": "Night Vale Presents", "description": "\\n      Twice-monthly community updates for the small desert town of Night Vale, where every conspiracy theory is true. Turn on your radio and hide. Never listened before? It\'s an ongoing radio show. Start with the current episode, and you\'ll catch on in no time. Or, go right to Episode 1 if you wanna binge-listen.\\n    ", "releaseDate": "2022-10-20T19:00:00Z", "genres": ["Science Fiction", "Podcasts", "Fiction"], "feedUrl": "http://feeds.nightvalepresents.com/welcometonightvalepodcast", "imageUrl": "https://is4-ssl.mzstatic.com/image/thumb/Podcasts125/v4/4a/31/35/4a3135d0-1fe7-a2d7-fb43-d182ec175402/mza_8232698753950666850.jpg/600x600bb.jpg", "itunesPageUrl": "https://podcasts.apple.com/us/podcast/welcome-to-night-vale/id536258179?uo=4", "itunesId": 536258179, "itunesArtistId": 718704794, "explicit": false, "language": null}, "chapters": [], "displayTitle": "1 - Pilot", "displayAuthor": "Night Vale Presents", "coverPath": "/metadata/items/li_bufnnmp4y5o2gbbxfm/cover.jpg", "duration": 1454.18449, "playMethod": 0, "mediaPlayer": "html5", "deviceInfo": {"ipAddress": "192.168.1.118", "browserName": "Firefox", "browserVersion": "106.0", "osName": "Linux", "osVersion": "x86_64", "serverVersion": "2.2.4"}, "date": "2022-11-16", "dayOfWeek": "Wednesday", "timeListening": 20, "startTime": 616.291374, "currentTime": 636.09262, "startedAt": 1668580247687, "updatedAt": 1668580396623}]}'
```

> The above command returns JSON structured like this:

```json
{
  "results": [
    {
      "id": "play_local_i00492kps6ow4axlvq",
      "success": true,
      "progressSynced": true
    }
  ]
}
```

This endpoint updates local listening sessions on the server.

### HTTP Request

`POST http://abs.example.com/api/session/local-all`

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`sessions` | Array of [Playback Session](#playback-session) | The local playback sessions to sync.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See Below

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`results` | Array of [Sync Local Session Result](#sync-local-session-result) | The results from the session syncs.

#### Sync Local Session Result

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the playback session.
`success` | Boolean | Whether the session was successfully synced.
`error` | String | Will only exist if `success` is `false`. The error that occurred when syncing.
`progressSynced` | Boolean | Will only exist if `success` is `true`. Whether the progress for the session's library item was updated.


## Get an Open Session

```shell
curl "https://abs.example.com/api/session/play_i00492kps6ow4axlvq" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "id": "play_i00492kps6ow4axlvq",
  "userId": "root",
  "libraryId": "lib_p9wkw2i85qy9oltijt",
  "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
  "episodeId": "ep_lh6ko39pumnrma3dhv",
  "mediaType": "podcast",
  "mediaMetadata": {
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
  "chapters": [],
  "displayTitle": "1 - Pilot",
  "displayAuthor": "Night Vale Presents",
  "coverPath": "/metadata/items/li_bufnnmp4y5o2gbbxfm/cover.jpg",
  "duration": 1454.18449,
  "playMethod": 0,
  "mediaPlayer": "html5",
  "deviceInfo": {
    "ipAddress": "192.168.1.118",
    "browserName": "Firefox",
    "browserVersion": "106.0",
    "osName": "Linux",
    "osVersion": "x86_64",
    "serverVersion": "2.2.4"
  },
  "date": "2022-11-16",
  "dayOfWeek": "Wednesday",
  "timeListening": 15,
  "startTime": 616.291374,
  "currentTime": 631.09262,
  "startedAt": 1668580247687,
  "updatedAt": 1668580396623,
  "audioTracks": [
    {
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
    }
  ],
  "videoTrack": null,
  "libraryItem": {
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
      "episodes": [
        {
          "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
          "id": "ep_lh6ko39pumnrma3dhv",
          "index": 1,
          "season": "",
          "episode": "",
          "episodeType": "full",
          "title": "1 - Pilot",
          "subtitle": "Pilot Episode. A new dog park opens in Night Vale. Carlos, a scientist, visits and discovers some interesting things. Seismic things. Plus, a helpful guide to surveillance helicopter-spotting. Weather: \"These and More Than These\" by Joseph Fink Music:...",
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
}
```

This endpoint retrieves an open listening session.

### HTTP Request

`GET http://abs.example.com/api/session/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the listening session.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Playback Session Expanded](#playback-session-expanded)
404 | Not Found | No listening session with the provided ID is open, or the session belongs to another user. |


## Sync an Open Session

```shell
curl -X POST "https://abs.example.com/api/session/play_i00492kps6ow4axlvq/sync" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"currentTime": 636.09262, "timeListened": 5, "duration": 1454.18449}'
```

This endpoint syncs the position of an open listening session from the client to the server and returns the session.

### HTTP Request

`POST http://abs.example.com/api/session/<ID>/sync`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the listening session.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`currentTime` | Float | The current time (in seconds) of the playback position.
`timeListened` | Float | The amount of time (in seconds) the user has spent listening since the last session sync.
`duration` | Float | The total duration (in seconds) of the playing item.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
404 | Not Found | No listening session with the provided ID is open, or the session belongs to another user.
500 | Internal Server Error | There was an error syncing the session.


## Close an Open Session

```shell
curl -X POST "https://abs.example.com/api/session/play_i00492kps6ow4axlvq/close" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"currentTime": 636.09262, "timeListened": 5, "duration": 1454.18449}'
```

This endpoint closes an open listening session. Optionally provide sync data to update the session before closing it.

### HTTP Request

`POST http://abs.example.com/api/session/<ID>/close`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the listening session.

### Optional Parameters

Parameter | Type | Description
--------- | ---- | -----------
`currentTime` | Float | The current time (in seconds) of the playback position.
`timeListened` | Float | The amount of time (in seconds) the user has spent listening since the last session sync.
`duration` | Float | The total duration (in seconds) of the playing item.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
404 | Not Found | No listening session with the provided ID is open, or the session belongs to another user.
