# Me

All the "Me" endpoints are based off of the authenticated user. In these docs, "you" will refer to the authenticated user.

## Get Your User

```shell
curl "https://abs.example.com/api/me" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "id": "root",
  "username": "root",
  "type": "root",
  "token": "exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY",
  "mediaProgress": [],
  "seriesHideFromContinueListening": [],
  "bookmarks": [],
  "isActive": true,
  "isLocked": false,
  "lastSeen": 1667687240810,
  "createdAt": 1666569607117,
  "permissions": {
    "download": true,
    "update": true,
    "delete": true,
    "upload": true,
    "accessAllLibraries": true,
    "accessAllTags": true,
    "accessExplicitContent": true
  },
  "librariesAccessible": [],
  "itemTagsAccessible": []
}
```

This endpoint retrieves your user.

### HTTP Request

`GET http://abs.example.com/api/me`

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [User](#user)


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


## Get Your Listening Stats

```shell
curl "https://abs.example.com/api/me/listening-stats" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "totalTime": 493,
  "items": {
    "li_bufnnmp4y5o2gbbxfm": {
      "id": "li_bufnnmp4y5o2gbbxfm",
      "timeListening": 63,
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
        "language": null,
        "type": "episodic"
      }
    },
    ...
  },
  "days": {
    "2022-11-13": 104,
    "2022-11-12": 3,
    "2022-11-11": 1,
    "2022-11-10": 30,
    "2022-11-06": 14,
    "2022-11-05": 12,
    "2022-11-04": 20,
    "2022-10-26": 12,
    "2022-10-25": 206,
    "2022-10-24": 73,
    "2022-10-23": 12
  },
  "dayOfWeek": {
    "Sunday": 130,
    "Saturday": 15,
    "Friday": 21,
    "Thursday": 30,
    "Wednesday": 12,
    "Tuesday": 206,
    "Monday": 73
  },
  "today": 104,
  "recentSessions": [
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
    },
    ...
  ]
}
```

This endpoint retrieves your listening statistics.

### HTTP Request

`GET http://abs.example.com/api/me/listening-stats`

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`totalTime` | Integer | The total time (in seconds) you have listened to library items.
`items` | [Your Items Listened To](#your-items-listened-to) Object (See Below) | The library items that you have listened to.
`days` | [Your Day Time Totals](#your-day-time-totals) Object (See Below) | The total time you have listened to library items on each day.
`dayOfWeek` | [Your Day of Week Totals](#your-day-of-week-totals) Object (See Below) | The total time you have listened to library items on each day of the week.
`today` | Integer | The time (in seconds) you have listened to library items today.
`recentSessions` | Array of [Playback Session](#playback-session) | The 10 most recent of your playback sessions.

#### Your Items Listened To

The keys of this object are the library item IDs of the item listened to. The value of each key is an object of the following structure:

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the library item you listened to.
`timeListening` | Integer | The time (in seconds) you listened to the library item.
`mediaMetadata` | [Book Metadata](#book-metadata) or [Podcast Metadata](#podcast-metadata) Object | The metadata of the library item's media.

#### Your Day Time Totals

The keys of this object are each day (in the format YYYY-MM-DD) when you listened to library items. The values are the total time (in seconds, Integer) you listened to library items.

#### Your Day of Week Totals

The keys of this object are each day of the week. The values are the total time (in seconds, Integer) you listened to library items on that day of the week.


## Remove an Item From Continue Listening

```shell
curl "https://abs.example.com/api/me/progress/li_bufnnmp4y5o2gbbxfm-ep_lh6ko39pumnrma3dhv/remove-from-continue-listening" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "id": "root",
  "username": "root",
  "type": "root",
  "token": "exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY",
  "mediaProgress": [
    {
      "id": "li_bufnnmp4y5o2gbbxfm-ep_lh6ko39pumnrma3dhv",
      "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
      "episodeId": "ep_lh6ko39pumnrma3dhv",
      "duration": 1454.18449,
      "progress": 0.42057298864465265,
      "currentTime": 611.590717,
      "isFinished": false,
      "hideFromContinueListening": true,
      "lastUpdate": 1668330152157,
      "startedAt": 1668120083771,
      "finishedAt": null
    }
  ],
  "seriesHideFromContinueListening": [],
  "bookmarks": [],
  "isActive": true,
  "isLocked": false,
  "lastSeen": 1667687240810,
  "createdAt": 1666569607117,
  "permissions": {
    "download": true,
    "update": true,
    "delete": true,
    "upload": true,
    "accessAllLibraries": true,
    "accessAllTags": true,
    "accessExplicitContent": true
  },
  "librariesAccessible": [],
  "itemTagsAccessible": []
}
```

This endpoint removes a library item, that has media progress associated with your user, from your "Continue Listening" shelf. Your user is returned.

### HTTP Request

`GET http://abs.example.com/api/me/progress/<ID>/remove-from-continue-listening`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the **media progress** that refers to the library item to remove.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [User](#user)


## Get a Media Progress

```shell
curl "https://abs.example.com/api/me/progress/li_bufnnmp4y5o2gbbxfm/ep_lh6ko39pumnrma3dhv" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "id": "li_bufnnmp4y5o2gbbxfm-ep_lh6ko39pumnrma3dhv",
  "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
  "episodeId": "ep_lh6ko39pumnrma3dhv",
  "duration": 1454.18449,
  "progress": 0.42057298864465265,
  "currentTime": 611.590717,
  "isFinished": false,
  "hideFromContinueListening": false,
  "lastUpdate": 1668330152157,
  "startedAt": 1668120083771,
  "finishedAt": null
}
```

This endpoint retrieves your media progress that is associated with the given library item ID or podcast episode ID.

### HTTP Request

* `GET http://abs.example.com/api/me/progress/<LibraryItemID>`
* `GET http://abs.example.com/api/me/progress/<LibraryItemID>/<EpisodeID>`

### URL Parameters

Parameter | Description
--------- | -----------
LibraryItemID | The ID of the library item to retrieve the media progress for.
EpisodeID | The ID of the podcast episode to retrieve the media progress for.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Media Progress](#media-progress)
404 | Not Found | No media progress was found that matches the given IDs. |


## Batch Create/Update Media Progress

```shell
curl -X PATCH "https://abs.example.com/api/me/progress/batch/update" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '[{"libraryItemId": "li_bufnnmp4y5o2gbbxfm", "episodeId": "ep_lh6ko39pumnrma3dhv", "isFinished": true}]'
```

This endpoint batch creates/updates your media progress.

### HTTP Request

`PATCH http://abs.example.com/api/me/progress/batch/update`

### Parameters

Provide an array of objects with the following parameters:

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`libraryItemId` | String | **Required** | The ID of the library item the media progress is for.
`episodeId` | String or null | `null` | The ID of the podcast episode the media progress is for.
`duration` | Float | `0` | The total duration (in seconds) of the media.
`progress` | Float | `0` or `1` | The percentage completion progress of the media. Will automatically be set to `1` if the media is finished.
`currentTime` | Float | `0` | The current time (in seconds) of your progress.
`isFinished` | Boolean | `false` | Whether the media is finished.
`hideFromContinueListening` | Boolean | `false` | Whether the media will be hidden from the "Continue Listening" shelf.
`finishedAt` | Integer or null | `null` or `Date.now()` | The time (in ms since POSIX epoch) when the user finished the media. The default will be `Date.now()` if `isFinished` is `true`.
`startedAt` | Integer | `Date.now()` or `finishedAt` | The time (in ms since POSIX epoch) when the user started consuming the media. The default will be the value of `finishedAt` if `isFinished` is `true`.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
400 | Bad Request | The provided array must have a non-zero length.


## Create/Update Media Progress

```shell
curl -X PATCH "https://abs.example.com/api/me/progress/li_bufnnmp4y5o2gbbxfm/ep_lh6ko39pumnrma3dhv" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"isFinished": true}'
```

This endpoint creates/updates your media progress for a library item or podcast episode.

### HTTP Request

* `PATCH http://abs.example.com/api/me/progress/<LibraryItemID>`
* `PATCH http://abs.example.com/api/me/progress/<LibraryItemID>/<EpisodeID>`

### URL Parameters

Parameter | Description
--------- | -----------
LibraryItemID | The ID of the library item to create/update media progress for.
EpisodeID | The ID of the podcast episode to create/update media progress for.

### Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`duration` | Float | `0` | The total duration (in seconds) of the media.
`progress` | Float | `0` or `1` | The percentage completion progress of the media. Will automatically be set to `1` if the media is finished.
`currentTime` | Float | `0` | The current time (in seconds) of your progress.
`isFinished` | Boolean | `false` | Whether the media is finished.
`hideFromContinueListening` | Boolean | `false` | Whether the media will be hidden from the "Continue Listening" shelf.
`finishedAt` | Integer or null | `null` or `Date.now()` | The time (in ms since POSIX epoch) when the user finished the media. The default will be `Date.now()` if `isFinished` is `true`.
`startedAt` | Integer | `Date.now()` or `finishedAt` | The time (in ms since POSIX epoch) when the user started consuming the media. The default will be the value of `finishedAt` if `isFinished` is `true`.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
404 | Not Found | No library items or podcast episodes were found with the given IDs.


## Remove a Media Progress

```shell
curl -X DELETE "https://abs.example.com/api/me/progress/li_bufnnmp4y5o2gbbxfm-ep_lh6ko39pumnrma3dhv" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint removes a media progress entry from your user.

### HTTP Request

`DELETE http://abs.example.com/api/me/progress/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the media progress to remove.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success


## Create a Bookmark

```shell
curl -X POST "https://abs.example.com/api/me/item/li_bufnnmp4y5o2gbbxfm/bookmark" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"time": 16, "title": "the good part"}'
```

> The above command returns JSON structured like this:

```json
{
  "libraryItemId": "li_8gch9ve09orgn4fdz8",
  "title": "the good part",
  "time": 16,
  "createdAt": 1668120083771
}
```

This endpoint creates a bookmark for a book library item and returns the created bookmark.

### HTTP Request

`POST http://abs.example.com/api/me/item/<ID>/bookmark`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item to create a bookmark for.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`time` | Integer | The time (in seconds) in the book to create the bookmark at.
`title` | String | The title of the bookmark.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Audio Bookmark](#audio-bookmark)
404 | Not Found | No library item with the provided ID exists. |


## Update a Bookmark 

```shell
curl -X PATCH "https://abs.example.com/api/me/item/li_bufnnmp4y5o2gbbxfm/bookmark" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"time": 16, "title": "the better part"}'
```

> The above command returns JSON structured like this:

```json
{
  "libraryItemId": "li_8gch9ve09orgn4fdz8",
  "title": "the better part",
  "time": 16,
  "createdAt": 1668120083771
}
```

This endpoint updates a bookmark and returns it.

### HTTP Request

`PATCH http://abs.example.com/api/me/item/<ID>/bookmark`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item to update a bookmark for.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`time` | Integer | The time (in seconds) of the bookmark.
`title` | String | The title of the bookmark.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Audio Bookmark](#audio-bookmark)
404 | Not Found | No library item with the provided ID exists or no bookmark at the given `time` exists. |
500 | Internal Server Error | Could not find the bookmark. |


## Remove a Bookmark

```shell
curl -X DELETE "https://abs.example.com/api/me/item/li_bufnnmp4y5o2gbbxfm/bookmark/16" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint removes a bookmark.

### HTTP Request

`DELETE http://abs.example.com/api/me/item/<ID>/bookmark/<Time>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item to remove a bookmark from.
Time | The time (in seconds) the bookmark is at.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
404 | Not Found | No library item with the provided ID exists or no bookmark at the given Time exists.
500 | Internal Server Error | The Time URL parameter must be a number.


## Change Your Password

```shell
curl -X PATCH "https://abs.example.com/api/me/password" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"password": "12345", "newPassword": "54321"}'
```

> The above command returns JSON structured like this:

```json
{
  "success": true
}
```

This endpoint changes your password.

### HTTP Request

`PATCH http://abs.example.com/api/me/password`

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`password` | String | Your current password.
`newPassword` | String | Your new password.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
500 | Internal Server Error | Guest users cannot change their password. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`success` | Boolean | Will only exist and be `true` if the password was updated successfully.
`error` | String | The error that occurred. Will only exist if there was an error updating your password.


## Sync Local Media Progress

```shell
curl -X POST "https://abs.example.com/api/me/sync-local-progress" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"localMediaProgress": [{ "id": "local_li_bufnnmp4y5o2gbbxfm-local_ep_lh6ko39pumnrma3dhv", "libraryItemId": "li_bufnnmp4y5o2gbbxfm", "episodeId": "ep_lh6ko39pumnrma3dhv", "duration": 1454.18449, "progress": 0.011193983371394644, "currentTime": 16.278117, "isFinished": false, "hideFromContinueListening": false, "lastUpdate": 1668120246620, "startedAt": 1668120083771, "finishedAt": null}]}'
```

> The above command returns JSON structured like this:

```json
{
  "numServerProgressUpdates": 1,
  "localProgressUpdates": [],
  "serverProgressUpdates": {
    "id": "li_bufnnmp4y5o2gbbxfm-ep_lh6ko39pumnrma3dhv",
    "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
    "episodeId": "ep_lh6ko39pumnrma3dhv",
    "duration": 1454.18449,
    "progress": 0.011193983371394644,
    "currentTime": 16.278117,
    "isFinished": false,
    "hideFromContinueListening": false,
    "lastUpdate": 1668120246620,
    "startedAt": 1668120083771,
    "finishedAt": null
  },
}
```

<aside class="warning">
This endpoint will soon be <strong>deprecated</strong>.
</aside>

This endpoint syncs a mobile client's local media progress with the server. For any local media progress with a greater `lastUpdate` time than the `lastUpdate` time of the matching media progress on the server, the server's media progress is updated. If the server's `lastUpdate` time is greater, than the local media progress will be returned with the updated information.

### HTTP Request

`POST http://abs.example.com/api/me/sync-local-progress`

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`localMediaProgress` | Array of [Media Progress](#media-progress) | The client's local media progress.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
500 | Internal Server Error | The `localMediaProgress` parameter is required. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`numServerProgressUpdates` | Integer | The number of media progress items that were updated on the server.
`localProgressUpdates` | Array of [Media Progress](#media-progress) | Local media progress items with updated information from the server (server more recent).
`serverProgressUpdates` | Array of [Media Progress](#media-progress) | Media progress items that were updated on the server (local more recent).


## Get Library Items In Progress

```shell
curl "https://abs.example.com/api/me/items-in-progress?limit=1" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "libraryItems": [
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
      "isMissing": false,
      "isInvalid": false,
      "mediaType": "podcast",
      "media": {
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
        "numEpisodes": 1,
        "autoDownloadEpisodes": false,
        "autoDownloadSchedule": "0 0 * * 1",
        "lastEpisodeCheck": 1667326662087,
        "maxEpisodesToKeep": 0,
        "maxNewEpisodesToDownload": 3,
        "size": 23653735
      },
      "numFiles": 2,
      "size": 23706728,
      "recentEpisode": {
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
        "publishedAt": 1339761600000,
        "addedAt": 1667326679503,
        "updatedAt": 1667428186431
      },
      "progressLastUpdate": 1668434165531
    }
  ]
}
```

This endpoint retrieves library items that are in progress (started, not finished).

### HTTP Request

`GET http://abs.example.com/api/me/items-in-progress`

### Optional Query Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`limit` | Integer | `25` | A limit for how many library items to return.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`libraryItems` | Array of [Library Item Minified](#library-item-minified) | The in progress library items. They have extra attributes which are described below.

#### Extra Attributes

Attribute | Type | Description
--------- | ---- | -----------
`recentEpisode` | [Podcast Episode](#podcast-episode) Object | If the library item is for a podcast, the media progress's corresponding podcast episode. Will not exist for book library items.
`progressLastUpdate` | Integer | The time (in ms since POSIX epoch) when the corresponding media progress was last updated.


## Remove a Series From Continue Listening

```shell
curl "https://abs.example.com/api/me/series/ser_cabkj4jeu8be3rap4g/remove-from-continue-listening" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "id": "root",
  "username": "root",
  "type": "root",
  "token": "exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY",
  "mediaProgress": [
    {
      "id": "li_8gch9ve09orgn4fdz8",
      "libraryItemId": "li_8gch9ve09orgn4fdz8",
      "episodeId": null,
      "duration": 33854.905,
      "progress": 0,
      "currentTime": 0,
      "isFinished": false,
      "hideFromContinueListening": false,
      "lastUpdate": 1668330152157,
      "startedAt": 1668120083771,
      "finishedAt": null
    }
  ],
  "seriesHideFromContinueListening": [
    "ser_cabkj4jeu8be3rap4g"
  ],
  "bookmarks": [],
  "isActive": true,
  "isLocked": false,
  "lastSeen": 1667687240810,
  "createdAt": 1666569607117,
  "permissions": {
    "download": true,
    "update": true,
    "delete": true,
    "upload": true,
    "accessAllLibraries": true,
    "accessAllTags": true,
    "accessExplicitContent": true
  },
  "librariesAccessible": [],
  "itemTagsAccessible": []
}
```

This endpoint removes a series from your "Continue Series" shelf. Your user is returned.

### HTTP Request

`GET http://abs.example.com/api/me/series/<ID>/remove-from-continue-listening`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the series to remove from continue listening.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [User](#user)
404 | Not Found | No series matching the provided ID was found. |
