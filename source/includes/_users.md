# Users

## Create a User

```shell
curl -X POST "https://abs.example.com/api/users" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"username": "bob", "password": "12345", "type": "admin"}'
```

> The above command returns JSON structured like this:

```json
{
  "id": "usr_3vn1ywq2yc2aq4kfh4",
  "username": "bob",
  "type": "admin",
  "token": "exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY",
  "mediaProgress": [],
  "seriesHideFromContinueListening": [],
  "bookmarks": [],
  "isActive": true,
  "isLocked": false,
  "lastSeen": null,
  "createdAt": 1666569607117,
  "permissions": {
    "download": true,
    "update": true,
    "delete": false,
    "upload": true,
    "accessAllLibraries": true,
    "accessAllTags": true,
    "accessExplicitContent": true
  },
  "librariesAccessible": [],
  "itemTagsAccessible": []
}
```

This endpoint creates a user.

### HTTP Request

`POST http://abs.example.com/api/users`

### Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`username` | String | **Required** | The new user's username.
`password` | String | **Required** | The new user's password.
`type` | String | **Required** | The new user's type. May be `guest`, `user`, or `admin`.
`mediaProgress` | Array of [Media Progress](#media-progress) | `[]` | The new user's media progress.
`bookmarks` | Array of [Audio Bookmark](#audio-bookmark) | `[]` | The new user's bookmarks.
`seriesHideFromContinueListening` | Array of String | `[]` | The IDs of series to hide from the new user's "Continue Series" shelf.
`isActive` | Boolean | `true` | Whether the new user's account is active.
`isLocked` | Boolean | `false` | Whether the new user is locked.
`lastSeen` | Integer or null | `null` | The time (in ms since POSIX epoch) when the new user was last seen.
`createdAt` | Integer | `Date.now()` | The time (in ms since POSIX epoch) when the new user was created.
`permissions` | [User Permissions Parameters](#user-permissions-parameters) Object | See Below | The new user's permissions.
`librariesAccessible` | Array of String | `[]` | The IDs of libraries that are accessible to the new user. An empty array means all libraries are accessible.
`itemTagsAccessible` | Array of String | `[]` | The tags that are accessible to the new user. An empty array means all tags are accessible.

<aside class="notice">
For <code>permissions</code>, all parameters must be present if including them in the request.
</aside>

#### User Permissions Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`download` | Boolean | `true` | Whether the user can download items from the server.
`update` | Boolean | `true` | Whether the user can update library items.
`delete` | Boolean | `false` | Whether the user can delete library items.
`upload` | Boolean | `false` | Whether the user can upload items to the server. The default value is `true` if the user's `type` is `admin`.
`accessAllLibraries` | Boolean | `true` | Whether the user can access all libraries.
`accessAllTags` | Boolean | `true` | Whether the user can access all tags.
`accessExplicitContent` | Boolean | `true` | Whether the user can access explicit content.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [User](#user)
403 | Forbidden | The user does not have permission to create new users. |
500 | Internal Server Error | Either the username provided is already taken, or the server failed to save the new user. |


## Get All Users

```shell
curl "https://abs.example.com/api/users" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "users": [
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
  ]
}
```

This endpoint retrieves all users.

### HTTP Request

`GET http://abs.example.com/api/users`

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See Below
403 | Forbidden | An admin user is required to get all users. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`users` | Array of [User with Progress Details](#user-with-progress-details) | The requested users.


## Get Online Users

```shell
curl "https://abs.example.com/api/users/online" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "usersOnline": [
    {
      "id": "root",
      "username": "paul",
      "type": "root",
      "session": null,
      "mostRecent": {
        "id": "li_bufnnmp4y5o2gbbxfm-ep_lh6ko39pumnrma3dhv",
        "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
        "episodeId": "ep_lh6ko39pumnrma3dhv",
        "duration": 1454.18449,
        "progress": 0.41038768196461783,
        "currentTime": 596.779402,
        "isFinished": false,
        "hideFromContinueListening": false,
        "lastUpdate": 1668329493006,
        "startedAt": 1668120083771,
        "finishedAt": null,
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
        "episode": {
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
          "publishedAt": 1339761600000,
          "addedAt": 1667326679503,
          "updatedAt": 1667428186431
        }
      },
      "lastSeen": 1668324661087,
      "createdAt": 1666543632566
    }
  ],
  "openSessions": [
    {
      "id": "play_3m7y81exxkpodebwvd",
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
      "timeListening": 595,
      "startTime": 0,
      "currentTime": 595,
      "startedAt": 1668329239515,
      "updatedAt": 1668329240593
    }
  ]
}
```

This endpoint retrieves all online users.

### HTTP Request

`GET http://abs.example.com/api/users/online`

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
403 | Forbidden | An admin user is required to get users. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`usersOnline` | Array of [User with Session and Most Recent Progress](#user-with-session-and-most-recent-progress) | The users that are currently online.
`openSessions` | Array of [Playback Session](#playback-session) | The currently playing playback sessions.


## Get a User

```shell
curl "https://abs.example.com/api/users/root" \
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

This endpoint retrieves a user.

### HTTP Request

`GET http://abs.example.com/api/users/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the user.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [User with Progress Details](#user-with-progress-details)
403 | Forbidden | An admin user is required to get users. |
404 | Not Found | No user with the provided ID exists. |


## Update a User

```shell
curl -X PATCH "https://abs.example.com/api/users/root" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"username": "bob", "password": "12345"}'
```

> The above command returns JSON structured like this:

```json
{
  "id": "root",
  "username": "bob",
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

This endpoint updates a user.

### HTTP Request

`PATCH http://abs.example.com/api/users/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the user.

### Parameters

For the root user, only `username` and `password` are changeable.

Parameter | Type | Description
--------- | ---- | -----------
`username` | String | The user's username.
`password` | String | The user's password.
`type` | String | The user's type. May be `guest`, `user`, or `admin`.
`seriesHideFromContinueListening` | Array of String | The IDs of series to hide from the user's "Continue Series" shelf.
`isActive` | Boolean | Whether the user's account is active.
`permissions` | [User Permissions Parameters](#user-permissions-parameters-2) Object (See Below) | The user's permissions.
`librariesAccessible` | Array of String | The IDs of libraries that are accessible to the user. An empty array means all libraries are accessible.
`itemTagsAccessible` | Array of String | The tags that are accessible to the user. An empty array means all tags are accessible.

<aside class="notice">
When changing a user's username, their token will be regenerated.
</aside>

#### User Permissions Parameters

Parameter | Type | Description
--------- | ---- | -----------
`download` | Boolean | Whether the user can download items from the server.
`update` | Boolean | Whether the user can update library items.
`delete` | Boolean | Whether the user can delete library items.
`upload` | Boolean | Whether the user can upload items to the server.
`accessAllLibraries` | Boolean | Whether the user can access all libraries.
`accessAllTags` | Boolean | Whether the user can access all tags.
`accessExplicitContent` | Boolean | Whether the user can access explicit content.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
403 | Forbidden | An admin user is required to edit users and the root user is required to edit the root user. |
404 | Not Found | No user with the provided ID exists. |
500 | Internal Server Error | The provided username is already taken. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`success` | Boolean | Whether the user was updated successfully.
`user` | [User](#user) Object | The updated user.


## Delete a User

```shell
curl -X DELETE "https://abs.example.com/api/users/usr_rfk7dgyjp8kg4waewi" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "success": true
}
```

This endpoint deletes a user.

### HTTP Request

`DELETE http://abs.example.com/api/users/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the user.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
404 | Not Found | No user with the provided ID exists. |
500 | Internal Server Error | The root user cannot be deleted and users cannot delete themselves. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`success` | Boolean | Whether the user was successfully deleted.


## Get a User's Listening Sessions

```shell
curl "https://abs.example.com/api/users/root/listening-sessions?itemsPerPage=1" \
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

This endpoint retrieves a user's listening sessions.

### HTTP Request

`GET http://abs.example.com/api/users/<ID>/listening-sessions`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the user.

### Query Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`itemsPerPage` | Integer | `10` | The number of listening sessions to retrieve per page.
`page` | Integer | `0` | The page (0 indexed) to retrieve.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
404 | Not Found | No user with the provided ID exists. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`total` | Integer | The total number of listening sessions.
`numPages` | Integer | The total number of pages when using this `itemsPerPage` limit.
`itemsPerPage` | Integer | The provided `itemsPerPage` parameter.
`sessions` | Array of [Playback Session](#playback-session) | The requested listening sessions.


## Get a User's Listening Stats

```shell
curl "https://abs.example.com/api/users/root/listening-stats" \
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
        "language": null
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

This endpoint retrieves a user's listening statistics.

### HTTP Request

`GET http://abs.example.com/api/users/<ID>/listening-stats`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the user.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
404 | Not Found | No user with the provided ID exists. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`totalTime` | Integer | The total time (in seconds) the user has listened to library items.
`items` | [Items Listened To](#items-listened-to) Object (See Below) | The library items that the user has listened to.
`days` | [Day Time Totals](#day-time-totals) Object (See Below) | The total time the user has listened to library items on each day.
`dayOfWeek` | [Day of Week Totals](#day-of-week-totals) Object (See Below) | The total time the user has listened to library items on each day of the week.
`today` | Integer | The time (in seconds) the user has listened to library items today.
`recentSessions` | Array of [Playback Session](#playback-session) | The 10 most recent playback sessions for the user.

#### Items Listened To

The keys of this object are the library item IDs of the item listened to. The value of each key is an object of the following structure:

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the library item that was listened to by the user.
`timeListening` | Integer | The time (in seconds) the user listened to the library item.
`mediaMetadata` | [Book Metadata](#book-metadata) or [Podcast Metadata](#podcast-metadata) Object | The metadata of the library item's media.

#### Day Time Totals

The keys of this object are each day (in the format YYYY-MM-DD) when the user listened to library items. The values are the total time (in seconds, Integer) the user listened to library items.

#### Day of Week Totals

The keys of this object are each day of the week. The values are the total time (in seconds, Integer) the user listened to library items on that day of the week.


## Purge a User's Media Progress

```shell
curl -X POST "https://abs.example.com/api/users/root/purge-media-progress" \
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

This endpoint removes the user's media progress for library items that no longer exist.

### HTTP Request

`POST http://abs.example.com/api/users/<ID>/purge-media-progress`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the user.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [User with Progress Details](#user-with-progress-details)
403 | Forbidden | Only the root user can purge the root user's media progress. |
404 | Not Found | No user with the provided ID exists. |
