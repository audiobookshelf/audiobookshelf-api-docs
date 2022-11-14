# Me

All of the "Me" endpoints are based off of the authenticated user. In these docs, "you" will refer to the authenticated user.

## Get Your Listening Sessions

```shell
curl "https://abs.example.com/api/me/listening-sessions?itemsPerPage=1" \
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
  ]
}
```

This endpoint retrieves your listening sessions.

### HTTP Request

`GET http://abs.example.com/api/me/listening-sessions`

### Query Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`itemsPerPage` | Integer | `10` | The number of listening sessions to retrieve per page.
`page` | Integer | `0` | The page (0 indexed) to retrieve.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`total` | Integer | The total number of listening sessions.
`numPages` | Integer | The total number of pages when using this `itemsPerPage` limit.
`itemsPerPage` | Integer | The provided `itemsPerPage` parameter.
`sessions` | Array of [Playback Session](#playback-session) | The requested listening sessions.
