# Playlists

## Create a Playlist

```shell
curl -X POST "https://abs.example.com/api/playlists" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"libraryId": "lib_c1u6t4p45c35rf0nzd", "name": "Favorites", items: ["libraryItemId": "li_8gch9ve09orgn4fdz8"]}'
```

> The above command returns JSON structured like this:

```json
{
  "id": "pl_qbwet64998s5ra6dcu",
  "libraryId": "lib_c1u6t4p45c35rf0nzd",
  "userId": "root",
  "name": "Favorites",
  "description": null,
  "coverPath": null,
  "items": [
    {
      "libraryItemId": "li_8gch9ve09orgn4fdz8",
      "episodeId": null,
      "libraryItem": {
        "id": "li_8gch9ve09orgn4fdz8",
        "ino": "649641337522215266",
        "libraryId": "lib_c1u6t4p45c35rf0nzd",
        "folderId": "fol_bev1zuxhb0j0s1wehr",
        "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule",
        "relPath": "Terry Goodkind/Sword of Truth/Wizards First Rule",
        "isFile": false,
        "mtimeMs": 1650621074299,
        "ctimeMs": 1650621074299,
        "birthtimeMs": 0,
        "addedAt": 1650621073750,
        "updatedAt": 1650621110769,
        "lastScan": 1651830827825,
        "scanVersion": "2.0.21",
        "isMissing": false,
        "isInvalid": false,
        "mediaType": "book",
        "media": {
          "libraryItemId": "li_8gch9ve09orgn4fdz8",
          "metadata": {
            "title": "Wizards First Rule",
            "titleIgnorePrefix": "Wizards First Rule",
            "subtitle": null,
            "authors": [
              {
                "id": "aut_z3leimgybl7uf3y4ab",
                "name": "Terry Goodkind"
              }
            ],
            "narrators": [
              "Sam Tsoutsouvas"
            ],
            "series": [
              {
                "id": "ser_cabkj4jeu8be3rap4g",
                "name": "Sword of Truth",
                "sequence": "1"
              }
            ],
            "genres": [
              "Fantasy"
            ],
            "publishedYear": "2008",
            "publishedDate": null,
            "publisher": "Brilliance Audio",
            "description": "The masterpiece that started Terry Goodkind's New York Times bestselling epic Sword of Truth In the aftermath of the brutal murder of his father, a mysterious woman, Kahlan Amnell, appears in Richard Cypher's forest sanctuary seeking help...and more. His world, his very beliefs, are shattered when ancient debts come due with thundering violence. In a dark age it takes courage to live, and more than mere courage to challenge those who hold dominion, Richard and Kahlan must take up that challenge or become the next victims. Beyond awaits a bewitching land where even the best of their hearts could betray them. Yet, Richard fears nothing so much as what secrets his sword might reveal about his own soul. Falling in love would destroy them - for reasons Richard can't imagine and Kahlan dare not say. In their darkest hour, hunted relentlessly, tormented by treachery and loss, Kahlan calls upon Richard to reach beyond his sword - to invoke within himself something more noble. Neither knows that the rules of battle have just changed...or that their time has run out. Wizard's First Rule is the beginning. One book. One Rule. Witness the birth of a legend.",
            "isbn": null,
            "asin": "B002V0QK4C",
            "language": null,
            "explicit": false,
            "authorName": "Terry Goodkind",
            "authorNameLF": "Goodkind, Terry",
            "narratorName": "Sam Tsoutsouvas",
            "seriesName": "Sword of Truth"
          },
          "coverPath": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
          "tags": [
            "Favorite"
          ],
          "audioFiles": [
            {
              "index": 1,
              "ino": "649644248522215260",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "size": 48037888,
                "mtimeMs": 1632223180278,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              },
              "addedAt": 1650621074131,
              "updatedAt": 1651830828023,
              "trackNumFromMeta": 1,
              "discNumFromMeta": null,
              "trackNumFromFilename": 1,
              "discNumFromFilename": null,
              "manuallyVerified": false,
              "invalid": false,
              "exclude": false,
              "error": null,
              "format": "MP2/3 (MPEG audio layer 2/3)",
              "duration": 6004.6675,
              "bitRate": 64000,
              "language": null,
              "codec": "mp3",
              "timeBase": "1/14112000",
              "channels": 2,
              "channelLayout": "stereo",
              "chapters": [],
              "embeddedCoverArt": null,
              "metaTags": {
                "tagAlbum": "SOT Bk01",
                "tagArtist": "Terry Goodkind",
                "tagGenre": "Audiobook Fantasy",
                "tagTitle": "Wizards First Rule 01",
                "tagTrack": "01/20",
                "tagAlbumArtist": "Terry Goodkind",
                "tagComposer": "Terry Goodkind"
              },
              "mimeType": "audio/mpeg"
            },
            {
              "index": 2,
              "ino": "649644248522215261",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "size": 47972352,
                "mtimeMs": 1632223180281,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              },
              "addedAt": 1650621074130,
              "updatedAt": 1651830828023,
              "trackNumFromMeta": 2,
              "discNumFromMeta": null,
              "trackNumFromFilename": 1,
              "discNumFromFilename": null,
              "manuallyVerified": false,
              "invalid": false,
              "exclude": false,
              "error": null,
              "format": "MP2/3 (MPEG audio layer 2/3)",
              "duration": 5996.2785,
              "bitRate": 64000,
              "language": null,
              "codec": "mp3",
              "timeBase": "1/14112000",
              "channels": 2,
              "channelLayout": "stereo",
              "chapters": [],
              "embeddedCoverArt": null,
              "metaTags": {
                "tagAlbum": "SOT Bk01",
                "tagArtist": "Terry Goodkind",
                "tagGenre": "Audiobook Fantasy",
                "tagTitle": "Wizards First Rule 02",
                "tagTrack": "02/20",
                "tagAlbumArtist": "Terry Goodkind",
                "tagComposer": "Terry Goodkind"
              },
              "mimeType": "audio/mpeg"
            }
          ],
          "chapters": [
            {
              "id": 0,
              "start": 0,
              "end": 6004.6675,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01"
            },
            {
              "id": 1,
              "start": 6004.6675,
              "end": 12000.946,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02"
            }
          ],
          "duration": 33854.905,
          "size": 268824228,
          "tracks": [
            {
              "index": 1,
              "startOffset": 0,
              "duration": 6004.6675,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "contentUrl": "/s/item/li_8gch9ve09orgn4fdz8/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "mimeType": "audio/mpeg",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "size": 48037888,
                "mtimeMs": 1632223180278,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              }
            },
            {
              "index": 2,
              "startOffset": 6004.6675,
              "duration": 5996.2785,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "contentUrl": "/s/item/li_8gch9ve09orgn4fdz8/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "mimeType": "audio/mpeg",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 03.mp3",
                "size": 47972352,
                "mtimeMs": 1632223180281,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              }
            }
          ],
          "missingParts": [],
          "ebookFile": null
        },
        "libraryFiles": [
          {
            "ino": "649644248522215260",
            "metadata": {
              "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "ext": ".mp3",
              "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "size": 48037888,
              "mtimeMs": 1632223180278,
              "ctimeMs": 1645978261001,
              "birthtimeMs": 0
            },
            "addedAt": 1650621052494,
            "updatedAt": 1650621052494,
            "fileType": "audio"
          },
          {
            "ino": "649644248522215261",
            "metadata": {
              "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "ext": ".mp3",
              "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "size": 47972352,
              "mtimeMs": 1632223180281,
              "ctimeMs": 1645978261001,
              "birthtimeMs": 0
            },
            "addedAt": 1650621052494,
            "updatedAt": 1650621052494,
            "fileType": "audio"
          },
          {
            "ino": "649644248522215267",
            "metadata": {
              "filename": "cover.jpg",
              "ext": ".jpg",
              "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
              "relPath": "cover.jpg",
              "size": 325531,
              "mtimeMs": 1638754803540,
              "ctimeMs": 1645978261003,
              "birthtimeMs": 0
            },
            "addedAt": 1650621052495,
            "updatedAt": 1650621052495,
            "fileType": "image"
          }
        ],
        "size": 268990279
      }
    }
  ],
  "lastUpdate": 1669623431313,
  "createdAt": 1669623431313
}
```

This endpoint creates a playlist and returns it.

### HTTP Request

`POST http://abs.example.com/api/playlists`

### Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`libraryId` | String | **Required** | The ID of the library the playlist belongs to.
`name` | String | **Required** | The playlist's name.
`description` | String or null | `null` | The playlist's description.
`coverPath` | String or null | `null` | The path of the playlist's cover.
`items` | Array of [Playlist Item](#playlist-item) | `[]` | The items in the playlist.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Playlist Expanded](#playlist-expanded)
400 | Bad Request | The provided playlist data was invalid. |


## Get All User Playlists

```shell
curl "https://abs.example.com/api/playlists" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "playlists": [
    {
      "id": "pl_qbwet64998s5ra6dcu",
      "libraryId": "lib_c1u6t4p45c35rf0nzd",
      "userId": "root",
      "name": "Favorites",
      "description": null,
      "coverPath": null,
      "items": [
        {
          "libraryItemId": "li_8gch9ve09orgn4fdz8",
          "episodeId": null,
          "libraryItem": {
            "id": "li_8gch9ve09orgn4fdz8",
            "ino": "649641337522215266",
            "libraryId": "lib_c1u6t4p45c35rf0nzd",
            "folderId": "fol_bev1zuxhb0j0s1wehr",
            "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule",
            "relPath": "Terry Goodkind/Sword of Truth/Wizards First Rule",
            "isFile": false,
            "mtimeMs": 1650621074299,
            "ctimeMs": 1650621074299,
            "birthtimeMs": 0,
            "addedAt": 1650621073750,
            "updatedAt": 1650621110769,
            "lastScan": 1651830827825,
            "scanVersion": "2.0.21",
            "isMissing": false,
            "isInvalid": false,
            "mediaType": "book",
            "media": {
              "libraryItemId": "li_8gch9ve09orgn4fdz8",
              "metadata": {
                "title": "Wizards First Rule",
                "titleIgnorePrefix": "Wizards First Rule",
                "subtitle": null,
                "authors": [
                  {
                    "id": "aut_z3leimgybl7uf3y4ab",
                    "name": "Terry Goodkind"
                  }
                ],
                "narrators": [
                  "Sam Tsoutsouvas"
                ],
                "series": [
                  {
                    "id": "ser_cabkj4jeu8be3rap4g",
                    "name": "Sword of Truth",
                    "sequence": "1"
                  }
                ],
                "genres": [
                  "Fantasy"
                ],
                "publishedYear": "2008",
                "publishedDate": null,
                "publisher": "Brilliance Audio",
                "description": "The masterpiece that started Terry Goodkind's New York Times bestselling epic Sword of Truth In the aftermath of the brutal murder of his father, a mysterious woman, Kahlan Amnell, appears in Richard Cypher's forest sanctuary seeking help...and more. His world, his very beliefs, are shattered when ancient debts come due with thundering violence. In a dark age it takes courage to live, and more than mere courage to challenge those who hold dominion, Richard and Kahlan must take up that challenge or become the next victims. Beyond awaits a bewitching land where even the best of their hearts could betray them. Yet, Richard fears nothing so much as what secrets his sword might reveal about his own soul. Falling in love would destroy them - for reasons Richard can't imagine and Kahlan dare not say. In their darkest hour, hunted relentlessly, tormented by treachery and loss, Kahlan calls upon Richard to reach beyond his sword - to invoke within himself something more noble. Neither knows that the rules of battle have just changed...or that their time has run out. Wizard's First Rule is the beginning. One book. One Rule. Witness the birth of a legend.",
                "isbn": null,
                "asin": "B002V0QK4C",
                "language": null,
                "explicit": false,
                "authorName": "Terry Goodkind",
                "authorNameLF": "Goodkind, Terry",
                "narratorName": "Sam Tsoutsouvas",
                "seriesName": "Sword of Truth"
              },
              "coverPath": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
              "tags": [
                "Favorite"
              ],
              "audioFiles": [
                {
                  "index": 1,
                  "ino": "649644248522215260",
                  "metadata": {
                    "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                    "ext": ".mp3",
                    "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                    "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                    "size": 48037888,
                    "mtimeMs": 1632223180278,
                    "ctimeMs": 1645978261001,
                    "birthtimeMs": 0
                  },
                  "addedAt": 1650621074131,
                  "updatedAt": 1651830828023,
                  "trackNumFromMeta": 1,
                  "discNumFromMeta": null,
                  "trackNumFromFilename": 1,
                  "discNumFromFilename": null,
                  "manuallyVerified": false,
                  "invalid": false,
                  "exclude": false,
                  "error": null,
                  "format": "MP2/3 (MPEG audio layer 2/3)",
                  "duration": 6004.6675,
                  "bitRate": 64000,
                  "language": null,
                  "codec": "mp3",
                  "timeBase": "1/14112000",
                  "channels": 2,
                  "channelLayout": "stereo",
                  "chapters": [],
                  "embeddedCoverArt": null,
                  "metaTags": {
                    "tagAlbum": "SOT Bk01",
                    "tagArtist": "Terry Goodkind",
                    "tagGenre": "Audiobook Fantasy",
                    "tagTitle": "Wizards First Rule 01",
                    "tagTrack": "01/20",
                    "tagAlbumArtist": "Terry Goodkind",
                    "tagComposer": "Terry Goodkind"
                  },
                  "mimeType": "audio/mpeg"
                },
                {
                  "index": 2,
                  "ino": "649644248522215261",
                  "metadata": {
                    "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                    "ext": ".mp3",
                    "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                    "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                    "size": 47972352,
                    "mtimeMs": 1632223180281,
                    "ctimeMs": 1645978261001,
                    "birthtimeMs": 0
                  },
                  "addedAt": 1650621074130,
                  "updatedAt": 1651830828023,
                  "trackNumFromMeta": 2,
                  "discNumFromMeta": null,
                  "trackNumFromFilename": 1,
                  "discNumFromFilename": null,
                  "manuallyVerified": false,
                  "invalid": false,
                  "exclude": false,
                  "error": null,
                  "format": "MP2/3 (MPEG audio layer 2/3)",
                  "duration": 5996.2785,
                  "bitRate": 64000,
                  "language": null,
                  "codec": "mp3",
                  "timeBase": "1/14112000",
                  "channels": 2,
                  "channelLayout": "stereo",
                  "chapters": [],
                  "embeddedCoverArt": null,
                  "metaTags": {
                    "tagAlbum": "SOT Bk01",
                    "tagArtist": "Terry Goodkind",
                    "tagGenre": "Audiobook Fantasy",
                    "tagTitle": "Wizards First Rule 02",
                    "tagTrack": "02/20",
                    "tagAlbumArtist": "Terry Goodkind",
                    "tagComposer": "Terry Goodkind"
                  },
                  "mimeType": "audio/mpeg"
                }
              ],
              "chapters": [
                {
                  "id": 0,
                  "start": 0,
                  "end": 6004.6675,
                  "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01"
                },
                {
                  "id": 1,
                  "start": 6004.6675,
                  "end": 12000.946,
                  "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02"
                }
              ],
              "duration": 33854.905,
              "size": 268824228,
              "tracks": [
                {
                  "index": 1,
                  "startOffset": 0,
                  "duration": 6004.6675,
                  "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                  "contentUrl": "/s/item/li_8gch9ve09orgn4fdz8/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                  "mimeType": "audio/mpeg",
                  "metadata": {
                    "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                    "ext": ".mp3",
                    "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                    "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                    "size": 48037888,
                    "mtimeMs": 1632223180278,
                    "ctimeMs": 1645978261001,
                    "birthtimeMs": 0
                  }
                },
                {
                  "index": 2,
                  "startOffset": 6004.6675,
                  "duration": 5996.2785,
                  "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                  "contentUrl": "/s/item/li_8gch9ve09orgn4fdz8/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                  "mimeType": "audio/mpeg",
                  "metadata": {
                    "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                    "ext": ".mp3",
                    "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                    "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 03.mp3",
                    "size": 47972352,
                    "mtimeMs": 1632223180281,
                    "ctimeMs": 1645978261001,
                    "birthtimeMs": 0
                  }
                }
              ],
              "missingParts": [],
              "ebookFile": null
            },
            "libraryFiles": [
              {
                "ino": "649644248522215260",
                "metadata": {
                  "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                  "ext": ".mp3",
                  "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                  "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                  "size": 48037888,
                  "mtimeMs": 1632223180278,
                  "ctimeMs": 1645978261001,
                  "birthtimeMs": 0
                },
                "addedAt": 1650621052494,
                "updatedAt": 1650621052494,
                "fileType": "audio"
              },
              {
                "ino": "649644248522215261",
                "metadata": {
                  "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                  "ext": ".mp3",
                  "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                  "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                  "size": 47972352,
                  "mtimeMs": 1632223180281,
                  "ctimeMs": 1645978261001,
                  "birthtimeMs": 0
                },
                "addedAt": 1650621052494,
                "updatedAt": 1650621052494,
                "fileType": "audio"
              },
              {
                "ino": "649644248522215267",
                "metadata": {
                  "filename": "cover.jpg",
                  "ext": ".jpg",
                  "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
                  "relPath": "cover.jpg",
                  "size": 325531,
                  "mtimeMs": 1638754803540,
                  "ctimeMs": 1645978261003,
                  "birthtimeMs": 0
                },
                "addedAt": 1650621052495,
                "updatedAt": 1650621052495,
                "fileType": "image"
              }
            ],
            "size": 268990279
          }
        }
      ],
      "lastUpdate": 1669623431313,
      "createdAt": 1669623431313
    }
  ]
}
```

This endpoint retrieves all playlists belonging to the authenticated user.

### HTTP Request

`GET http://abs.example.com/api/playlists`

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See Below

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`playlists` | Array of [Playlist Expanded](#playlist-expanded) | The requested playlists.


## Get a Playlist

```shell
curl "https://abs.example.com/api/playlists/pl_qbwet64998s5ra6dcu" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "id": "pl_qbwet64998s5ra6dcu",
  "libraryId": "lib_c1u6t4p45c35rf0nzd",
  "userId": "root",
  "name": "Favorites",
  "description": null,
  "coverPath": null,
  "items": [
    {
      "libraryItemId": "li_8gch9ve09orgn4fdz8",
      "episodeId": null,
      "libraryItem": {
        "id": "li_8gch9ve09orgn4fdz8",
        "ino": "649641337522215266",
        "libraryId": "lib_c1u6t4p45c35rf0nzd",
        "folderId": "fol_bev1zuxhb0j0s1wehr",
        "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule",
        "relPath": "Terry Goodkind/Sword of Truth/Wizards First Rule",
        "isFile": false,
        "mtimeMs": 1650621074299,
        "ctimeMs": 1650621074299,
        "birthtimeMs": 0,
        "addedAt": 1650621073750,
        "updatedAt": 1650621110769,
        "lastScan": 1651830827825,
        "scanVersion": "2.0.21",
        "isMissing": false,
        "isInvalid": false,
        "mediaType": "book",
        "media": {
          "libraryItemId": "li_8gch9ve09orgn4fdz8",
          "metadata": {
            "title": "Wizards First Rule",
            "titleIgnorePrefix": "Wizards First Rule",
            "subtitle": null,
            "authors": [
              {
                "id": "aut_z3leimgybl7uf3y4ab",
                "name": "Terry Goodkind"
              }
            ],
            "narrators": [
              "Sam Tsoutsouvas"
            ],
            "series": [
              {
                "id": "ser_cabkj4jeu8be3rap4g",
                "name": "Sword of Truth",
                "sequence": "1"
              }
            ],
            "genres": [
              "Fantasy"
            ],
            "publishedYear": "2008",
            "publishedDate": null,
            "publisher": "Brilliance Audio",
            "description": "The masterpiece that started Terry Goodkind's New York Times bestselling epic Sword of Truth In the aftermath of the brutal murder of his father, a mysterious woman, Kahlan Amnell, appears in Richard Cypher's forest sanctuary seeking help...and more. His world, his very beliefs, are shattered when ancient debts come due with thundering violence. In a dark age it takes courage to live, and more than mere courage to challenge those who hold dominion, Richard and Kahlan must take up that challenge or become the next victims. Beyond awaits a bewitching land where even the best of their hearts could betray them. Yet, Richard fears nothing so much as what secrets his sword might reveal about his own soul. Falling in love would destroy them - for reasons Richard can't imagine and Kahlan dare not say. In their darkest hour, hunted relentlessly, tormented by treachery and loss, Kahlan calls upon Richard to reach beyond his sword - to invoke within himself something more noble. Neither knows that the rules of battle have just changed...or that their time has run out. Wizard's First Rule is the beginning. One book. One Rule. Witness the birth of a legend.",
            "isbn": null,
            "asin": "B002V0QK4C",
            "language": null,
            "explicit": false,
            "authorName": "Terry Goodkind",
            "authorNameLF": "Goodkind, Terry",
            "narratorName": "Sam Tsoutsouvas",
            "seriesName": "Sword of Truth"
          },
          "coverPath": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
          "tags": [
            "Favorite"
          ],
          "audioFiles": [
            {
              "index": 1,
              "ino": "649644248522215260",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "size": 48037888,
                "mtimeMs": 1632223180278,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              },
              "addedAt": 1650621074131,
              "updatedAt": 1651830828023,
              "trackNumFromMeta": 1,
              "discNumFromMeta": null,
              "trackNumFromFilename": 1,
              "discNumFromFilename": null,
              "manuallyVerified": false,
              "invalid": false,
              "exclude": false,
              "error": null,
              "format": "MP2/3 (MPEG audio layer 2/3)",
              "duration": 6004.6675,
              "bitRate": 64000,
              "language": null,
              "codec": "mp3",
              "timeBase": "1/14112000",
              "channels": 2,
              "channelLayout": "stereo",
              "chapters": [],
              "embeddedCoverArt": null,
              "metaTags": {
                "tagAlbum": "SOT Bk01",
                "tagArtist": "Terry Goodkind",
                "tagGenre": "Audiobook Fantasy",
                "tagTitle": "Wizards First Rule 01",
                "tagTrack": "01/20",
                "tagAlbumArtist": "Terry Goodkind",
                "tagComposer": "Terry Goodkind"
              },
              "mimeType": "audio/mpeg"
            },
            {
              "index": 2,
              "ino": "649644248522215261",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "size": 47972352,
                "mtimeMs": 1632223180281,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              },
              "addedAt": 1650621074130,
              "updatedAt": 1651830828023,
              "trackNumFromMeta": 2,
              "discNumFromMeta": null,
              "trackNumFromFilename": 1,
              "discNumFromFilename": null,
              "manuallyVerified": false,
              "invalid": false,
              "exclude": false,
              "error": null,
              "format": "MP2/3 (MPEG audio layer 2/3)",
              "duration": 5996.2785,
              "bitRate": 64000,
              "language": null,
              "codec": "mp3",
              "timeBase": "1/14112000",
              "channels": 2,
              "channelLayout": "stereo",
              "chapters": [],
              "embeddedCoverArt": null,
              "metaTags": {
                "tagAlbum": "SOT Bk01",
                "tagArtist": "Terry Goodkind",
                "tagGenre": "Audiobook Fantasy",
                "tagTitle": "Wizards First Rule 02",
                "tagTrack": "02/20",
                "tagAlbumArtist": "Terry Goodkind",
                "tagComposer": "Terry Goodkind"
              },
              "mimeType": "audio/mpeg"
            }
          ],
          "chapters": [
            {
              "id": 0,
              "start": 0,
              "end": 6004.6675,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01"
            },
            {
              "id": 1,
              "start": 6004.6675,
              "end": 12000.946,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02"
            }
          ],
          "duration": 33854.905,
          "size": 268824228,
          "tracks": [
            {
              "index": 1,
              "startOffset": 0,
              "duration": 6004.6675,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "contentUrl": "/s/item/li_8gch9ve09orgn4fdz8/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "mimeType": "audio/mpeg",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "size": 48037888,
                "mtimeMs": 1632223180278,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              }
            },
            {
              "index": 2,
              "startOffset": 6004.6675,
              "duration": 5996.2785,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "contentUrl": "/s/item/li_8gch9ve09orgn4fdz8/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "mimeType": "audio/mpeg",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 03.mp3",
                "size": 47972352,
                "mtimeMs": 1632223180281,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              }
            }
          ],
          "missingParts": [],
          "ebookFile": null
        },
        "libraryFiles": [
          {
            "ino": "649644248522215260",
            "metadata": {
              "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "ext": ".mp3",
              "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "size": 48037888,
              "mtimeMs": 1632223180278,
              "ctimeMs": 1645978261001,
              "birthtimeMs": 0
            },
            "addedAt": 1650621052494,
            "updatedAt": 1650621052494,
            "fileType": "audio"
          },
          {
            "ino": "649644248522215261",
            "metadata": {
              "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "ext": ".mp3",
              "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "size": 47972352,
              "mtimeMs": 1632223180281,
              "ctimeMs": 1645978261001,
              "birthtimeMs": 0
            },
            "addedAt": 1650621052494,
            "updatedAt": 1650621052494,
            "fileType": "audio"
          },
          {
            "ino": "649644248522215267",
            "metadata": {
              "filename": "cover.jpg",
              "ext": ".jpg",
              "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
              "relPath": "cover.jpg",
              "size": 325531,
              "mtimeMs": 1638754803540,
              "ctimeMs": 1645978261003,
              "birthtimeMs": 0
            },
            "addedAt": 1650621052495,
            "updatedAt": 1650621052495,
            "fileType": "image"
          }
        ],
        "size": 268990279
      }
    }
  ],
  "lastUpdate": 1669623431313,
  "createdAt": 1669623431313
}
```

This endpoint retrieves a playlist.

### HTTP Request

`GET http://abs.example.com/api/playlists/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the playlist.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Playlist Expanded](#playlist-expanded)
403 | Forbidden | The playlist does not belong to the authenticated user. |
404 | Not Found | No playlist with the provided ID exists. |


## Update a Playlist

```shell
curl -X PATCH "https://abs.example.com/api/playlists/pl_qbwet64998s5ra6dcu" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"name": "The Best Books"}'
```

> The above command returns JSON structured like this:

```json
{
  "id": "pl_qbwet64998s5ra6dcu",
  "libraryId": "lib_c1u6t4p45c35rf0nzd",
  "userId": "root",
  "name": "The Best Books",
  "description": null,
  "coverPath": null,
  "items": [
    {
      "libraryItemId": "li_8gch9ve09orgn4fdz8",
      "episodeId": null,
      "libraryItem": {
        "id": "li_8gch9ve09orgn4fdz8",
        "ino": "649641337522215266",
        "libraryId": "lib_c1u6t4p45c35rf0nzd",
        "folderId": "fol_bev1zuxhb0j0s1wehr",
        "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule",
        "relPath": "Terry Goodkind/Sword of Truth/Wizards First Rule",
        "isFile": false,
        "mtimeMs": 1650621074299,
        "ctimeMs": 1650621074299,
        "birthtimeMs": 0,
        "addedAt": 1650621073750,
        "updatedAt": 1650621110769,
        "lastScan": 1651830827825,
        "scanVersion": "2.0.21",
        "isMissing": false,
        "isInvalid": false,
        "mediaType": "book",
        "media": {
          "libraryItemId": "li_8gch9ve09orgn4fdz8",
          "metadata": {
            "title": "Wizards First Rule",
            "titleIgnorePrefix": "Wizards First Rule",
            "subtitle": null,
            "authors": [
              {
                "id": "aut_z3leimgybl7uf3y4ab",
                "name": "Terry Goodkind"
              }
            ],
            "narrators": [
              "Sam Tsoutsouvas"
            ],
            "series": [
              {
                "id": "ser_cabkj4jeu8be3rap4g",
                "name": "Sword of Truth",
                "sequence": "1"
              }
            ],
            "genres": [
              "Fantasy"
            ],
            "publishedYear": "2008",
            "publishedDate": null,
            "publisher": "Brilliance Audio",
            "description": "The masterpiece that started Terry Goodkind's New York Times bestselling epic Sword of Truth In the aftermath of the brutal murder of his father, a mysterious woman, Kahlan Amnell, appears in Richard Cypher's forest sanctuary seeking help...and more. His world, his very beliefs, are shattered when ancient debts come due with thundering violence. In a dark age it takes courage to live, and more than mere courage to challenge those who hold dominion, Richard and Kahlan must take up that challenge or become the next victims. Beyond awaits a bewitching land where even the best of their hearts could betray them. Yet, Richard fears nothing so much as what secrets his sword might reveal about his own soul. Falling in love would destroy them - for reasons Richard can't imagine and Kahlan dare not say. In their darkest hour, hunted relentlessly, tormented by treachery and loss, Kahlan calls upon Richard to reach beyond his sword - to invoke within himself something more noble. Neither knows that the rules of battle have just changed...or that their time has run out. Wizard's First Rule is the beginning. One book. One Rule. Witness the birth of a legend.",
            "isbn": null,
            "asin": "B002V0QK4C",
            "language": null,
            "explicit": false,
            "authorName": "Terry Goodkind",
            "authorNameLF": "Goodkind, Terry",
            "narratorName": "Sam Tsoutsouvas",
            "seriesName": "Sword of Truth"
          },
          "coverPath": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
          "tags": [
            "Favorite"
          ],
          "audioFiles": [
            {
              "index": 1,
              "ino": "649644248522215260",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "size": 48037888,
                "mtimeMs": 1632223180278,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              },
              "addedAt": 1650621074131,
              "updatedAt": 1651830828023,
              "trackNumFromMeta": 1,
              "discNumFromMeta": null,
              "trackNumFromFilename": 1,
              "discNumFromFilename": null,
              "manuallyVerified": false,
              "invalid": false,
              "exclude": false,
              "error": null,
              "format": "MP2/3 (MPEG audio layer 2/3)",
              "duration": 6004.6675,
              "bitRate": 64000,
              "language": null,
              "codec": "mp3",
              "timeBase": "1/14112000",
              "channels": 2,
              "channelLayout": "stereo",
              "chapters": [],
              "embeddedCoverArt": null,
              "metaTags": {
                "tagAlbum": "SOT Bk01",
                "tagArtist": "Terry Goodkind",
                "tagGenre": "Audiobook Fantasy",
                "tagTitle": "Wizards First Rule 01",
                "tagTrack": "01/20",
                "tagAlbumArtist": "Terry Goodkind",
                "tagComposer": "Terry Goodkind"
              },
              "mimeType": "audio/mpeg"
            },
            {
              "index": 2,
              "ino": "649644248522215261",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "size": 47972352,
                "mtimeMs": 1632223180281,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              },
              "addedAt": 1650621074130,
              "updatedAt": 1651830828023,
              "trackNumFromMeta": 2,
              "discNumFromMeta": null,
              "trackNumFromFilename": 1,
              "discNumFromFilename": null,
              "manuallyVerified": false,
              "invalid": false,
              "exclude": false,
              "error": null,
              "format": "MP2/3 (MPEG audio layer 2/3)",
              "duration": 5996.2785,
              "bitRate": 64000,
              "language": null,
              "codec": "mp3",
              "timeBase": "1/14112000",
              "channels": 2,
              "channelLayout": "stereo",
              "chapters": [],
              "embeddedCoverArt": null,
              "metaTags": {
                "tagAlbum": "SOT Bk01",
                "tagArtist": "Terry Goodkind",
                "tagGenre": "Audiobook Fantasy",
                "tagTitle": "Wizards First Rule 02",
                "tagTrack": "02/20",
                "tagAlbumArtist": "Terry Goodkind",
                "tagComposer": "Terry Goodkind"
              },
              "mimeType": "audio/mpeg"
            }
          ],
          "chapters": [
            {
              "id": 0,
              "start": 0,
              "end": 6004.6675,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01"
            },
            {
              "id": 1,
              "start": 6004.6675,
              "end": 12000.946,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02"
            }
          ],
          "duration": 33854.905,
          "size": 268824228,
          "tracks": [
            {
              "index": 1,
              "startOffset": 0,
              "duration": 6004.6675,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "contentUrl": "/s/item/li_8gch9ve09orgn4fdz8/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "mimeType": "audio/mpeg",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "size": 48037888,
                "mtimeMs": 1632223180278,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              }
            },
            {
              "index": 2,
              "startOffset": 6004.6675,
              "duration": 5996.2785,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "contentUrl": "/s/item/li_8gch9ve09orgn4fdz8/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "mimeType": "audio/mpeg",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 03.mp3",
                "size": 47972352,
                "mtimeMs": 1632223180281,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              }
            }
          ],
          "missingParts": [],
          "ebookFile": null
        },
        "libraryFiles": [
          {
            "ino": "649644248522215260",
            "metadata": {
              "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "ext": ".mp3",
              "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "size": 48037888,
              "mtimeMs": 1632223180278,
              "ctimeMs": 1645978261001,
              "birthtimeMs": 0
            },
            "addedAt": 1650621052494,
            "updatedAt": 1650621052494,
            "fileType": "audio"
          },
          {
            "ino": "649644248522215261",
            "metadata": {
              "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "ext": ".mp3",
              "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "size": 47972352,
              "mtimeMs": 1632223180281,
              "ctimeMs": 1645978261001,
              "birthtimeMs": 0
            },
            "addedAt": 1650621052494,
            "updatedAt": 1650621052494,
            "fileType": "audio"
          },
          {
            "ino": "649644248522215267",
            "metadata": {
              "filename": "cover.jpg",
              "ext": ".jpg",
              "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
              "relPath": "cover.jpg",
              "size": 325531,
              "mtimeMs": 1638754803540,
              "ctimeMs": 1645978261003,
              "birthtimeMs": 0
            },
            "addedAt": 1650621052495,
            "updatedAt": 1650621052495,
            "fileType": "image"
          }
        ],
        "size": 268990279
      }
    }
  ],
  "lastUpdate": 1669623431313,
  "createdAt": 1669623431313
}
```

This endpoint updates a playlist and returns it.

### HTTP Request

`PATCH http://abs.example.com/api/playlists/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the playlist.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`name` | String | The playlist's name.
`description` | String or null | The playlist's description.
`coverPath` | String or null | The path of the playlist's cover.
`items` | Array of [Playlist Item](#playlist-item) | The items in the playlist.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Playlist Expanded](#playlist-expanded)
403 | Forbidden | The playlist does not belong to the authenticated user. |
404 | Not Found | No playlist with the provided ID exists. |


## Delete a Playlist

```shell
curl -X DELETE "https://abs.example.com/api/playlists/pl_qbwet64998s5ra6dcu" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint deletes a playlist.

### HTTP Request

`DELETE http://abs.example.com/api/playlists/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the playlist.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
403 | Forbidden | The playlist does not belong to the authenticated user.
404 | Not Found | No playlist with the provided ID exists.


## Add an Item to a Playlist

```shell
curl -X POST "https://abs.example.com/api/playlists/pl_qbwet64998s5ra6dcu/item" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"libraryItemId": "li_8gch9ve09orgn4fdz8"}'
```

> The above command returns JSON structured like this:

```json
{
  "id": "pl_qbwet64998s5ra6dcu",
  "libraryId": "lib_c1u6t4p45c35rf0nzd",
  "userId": "root",
  "name": "The Best Books",
  "description": null,
  "coverPath": null,
  "items": [
    {
      "libraryItemId": "li_8gch9ve09orgn4fdz8",
      "episodeId": null,
      "libraryItem": {
        "id": "li_8gch9ve09orgn4fdz8",
        "ino": "649641337522215266",
        "libraryId": "lib_c1u6t4p45c35rf0nzd",
        "folderId": "fol_bev1zuxhb0j0s1wehr",
        "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule",
        "relPath": "Terry Goodkind/Sword of Truth/Wizards First Rule",
        "isFile": false,
        "mtimeMs": 1650621074299,
        "ctimeMs": 1650621074299,
        "birthtimeMs": 0,
        "addedAt": 1650621073750,
        "updatedAt": 1650621110769,
        "lastScan": 1651830827825,
        "scanVersion": "2.0.21",
        "isMissing": false,
        "isInvalid": false,
        "mediaType": "book",
        "media": {
          "libraryItemId": "li_8gch9ve09orgn4fdz8",
          "metadata": {
            "title": "Wizards First Rule",
            "titleIgnorePrefix": "Wizards First Rule",
            "subtitle": null,
            "authors": [
              {
                "id": "aut_z3leimgybl7uf3y4ab",
                "name": "Terry Goodkind"
              }
            ],
            "narrators": [
              "Sam Tsoutsouvas"
            ],
            "series": [
              {
                "id": "ser_cabkj4jeu8be3rap4g",
                "name": "Sword of Truth",
                "sequence": "1"
              }
            ],
            "genres": [
              "Fantasy"
            ],
            "publishedYear": "2008",
            "publishedDate": null,
            "publisher": "Brilliance Audio",
            "description": "The masterpiece that started Terry Goodkind's New York Times bestselling epic Sword of Truth In the aftermath of the brutal murder of his father, a mysterious woman, Kahlan Amnell, appears in Richard Cypher's forest sanctuary seeking help...and more. His world, his very beliefs, are shattered when ancient debts come due with thundering violence. In a dark age it takes courage to live, and more than mere courage to challenge those who hold dominion, Richard and Kahlan must take up that challenge or become the next victims. Beyond awaits a bewitching land where even the best of their hearts could betray them. Yet, Richard fears nothing so much as what secrets his sword might reveal about his own soul. Falling in love would destroy them - for reasons Richard can't imagine and Kahlan dare not say. In their darkest hour, hunted relentlessly, tormented by treachery and loss, Kahlan calls upon Richard to reach beyond his sword - to invoke within himself something more noble. Neither knows that the rules of battle have just changed...or that their time has run out. Wizard's First Rule is the beginning. One book. One Rule. Witness the birth of a legend.",
            "isbn": null,
            "asin": "B002V0QK4C",
            "language": null,
            "explicit": false,
            "authorName": "Terry Goodkind",
            "authorNameLF": "Goodkind, Terry",
            "narratorName": "Sam Tsoutsouvas",
            "seriesName": "Sword of Truth"
          },
          "coverPath": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
          "tags": [
            "Favorite"
          ],
          "audioFiles": [
            {
              "index": 1,
              "ino": "649644248522215260",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "size": 48037888,
                "mtimeMs": 1632223180278,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              },
              "addedAt": 1650621074131,
              "updatedAt": 1651830828023,
              "trackNumFromMeta": 1,
              "discNumFromMeta": null,
              "trackNumFromFilename": 1,
              "discNumFromFilename": null,
              "manuallyVerified": false,
              "invalid": false,
              "exclude": false,
              "error": null,
              "format": "MP2/3 (MPEG audio layer 2/3)",
              "duration": 6004.6675,
              "bitRate": 64000,
              "language": null,
              "codec": "mp3",
              "timeBase": "1/14112000",
              "channels": 2,
              "channelLayout": "stereo",
              "chapters": [],
              "embeddedCoverArt": null,
              "metaTags": {
                "tagAlbum": "SOT Bk01",
                "tagArtist": "Terry Goodkind",
                "tagGenre": "Audiobook Fantasy",
                "tagTitle": "Wizards First Rule 01",
                "tagTrack": "01/20",
                "tagAlbumArtist": "Terry Goodkind",
                "tagComposer": "Terry Goodkind"
              },
              "mimeType": "audio/mpeg"
            },
            {
              "index": 2,
              "ino": "649644248522215261",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "size": 47972352,
                "mtimeMs": 1632223180281,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              },
              "addedAt": 1650621074130,
              "updatedAt": 1651830828023,
              "trackNumFromMeta": 2,
              "discNumFromMeta": null,
              "trackNumFromFilename": 1,
              "discNumFromFilename": null,
              "manuallyVerified": false,
              "invalid": false,
              "exclude": false,
              "error": null,
              "format": "MP2/3 (MPEG audio layer 2/3)",
              "duration": 5996.2785,
              "bitRate": 64000,
              "language": null,
              "codec": "mp3",
              "timeBase": "1/14112000",
              "channels": 2,
              "channelLayout": "stereo",
              "chapters": [],
              "embeddedCoverArt": null,
              "metaTags": {
                "tagAlbum": "SOT Bk01",
                "tagArtist": "Terry Goodkind",
                "tagGenre": "Audiobook Fantasy",
                "tagTitle": "Wizards First Rule 02",
                "tagTrack": "02/20",
                "tagAlbumArtist": "Terry Goodkind",
                "tagComposer": "Terry Goodkind"
              },
              "mimeType": "audio/mpeg"
            }
          ],
          "chapters": [
            {
              "id": 0,
              "start": 0,
              "end": 6004.6675,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01"
            },
            {
              "id": 1,
              "start": 6004.6675,
              "end": 12000.946,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02"
            }
          ],
          "duration": 33854.905,
          "size": 268824228,
          "tracks": [
            {
              "index": 1,
              "startOffset": 0,
              "duration": 6004.6675,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "contentUrl": "/s/item/li_8gch9ve09orgn4fdz8/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "mimeType": "audio/mpeg",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "size": 48037888,
                "mtimeMs": 1632223180278,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              }
            },
            {
              "index": 2,
              "startOffset": 6004.6675,
              "duration": 5996.2785,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "contentUrl": "/s/item/li_8gch9ve09orgn4fdz8/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "mimeType": "audio/mpeg",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 03.mp3",
                "size": 47972352,
                "mtimeMs": 1632223180281,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              }
            }
          ],
          "missingParts": [],
          "ebookFile": null
        },
        "libraryFiles": [
          {
            "ino": "649644248522215260",
            "metadata": {
              "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "ext": ".mp3",
              "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "size": 48037888,
              "mtimeMs": 1632223180278,
              "ctimeMs": 1645978261001,
              "birthtimeMs": 0
            },
            "addedAt": 1650621052494,
            "updatedAt": 1650621052494,
            "fileType": "audio"
          },
          {
            "ino": "649644248522215261",
            "metadata": {
              "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "ext": ".mp3",
              "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "size": 47972352,
              "mtimeMs": 1632223180281,
              "ctimeMs": 1645978261001,
              "birthtimeMs": 0
            },
            "addedAt": 1650621052494,
            "updatedAt": 1650621052494,
            "fileType": "audio"
          },
          {
            "ino": "649644248522215267",
            "metadata": {
              "filename": "cover.jpg",
              "ext": ".jpg",
              "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
              "relPath": "cover.jpg",
              "size": 325531,
              "mtimeMs": 1638754803540,
              "ctimeMs": 1645978261003,
              "birthtimeMs": 0
            },
            "addedAt": 1650621052495,
            "updatedAt": 1650621052495,
            "fileType": "image"
          }
        ],
        "size": 268990279
      }
    }
  ],
  "lastUpdate": 1669623431313,
  "createdAt": 1669623431313
}
```

This endpoint adds an item to a playlist and returns the updated playlist.

### HTTP Request

`POST http://abs.example.com/api/playlists/<ID>/item`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the playlist.

### Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`libraryItemId` | String | **Required** | The ID of the library item the playlist item is for.
`episodeId` | String or null | `null` | The ID of the podcast episode the playlist item is for.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Playlist Expanded](#playlist-expanded)
400 | Bad Request | No library item with the provided ID exists, the library item is in a different library from the playlist, the library item is already in the playlist, the library item is not a podcast and an `episodeId` was provided, the library item is a podcast and an `episodeId` was not provided, or no podcast episode with the provided ID exists in the library item. |
403 | Forbidden | The playlist does not belong to the authenticated user. |
404 | Not Found | No playlist with the provided ID exists. |


## Remove an Item From a Playlist

```shell
curl -X DELETE "https://abs.example.com/api/playlists/pl_qbwet64998s5ra6dcu/item/li_8gch9ve09orgn4fdz8" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "id": "pl_qbwet64998s5ra6dcu",
  "libraryId": "lib_c1u6t4p45c35rf0nzd",
  "userId": "root",
  "name": "The Best Books",
  "description": null,
  "coverPath": null,
  "items": [],
  "lastUpdate": 1669623431313,
  "createdAt": 1669623431313
}
```

This endpoint removes an item from a playlist and returns the updated playlist. Then, if the playlist is empty, it will be deleted.

### HTTP Request

* `DELETE http://abs.example.com/api/playlists/<ID>/item/<LibraryItemID>`
* `DELETE http://abs.example.com/api/playlists/<ID>/item/<LibraryItemID>/<EpisodeID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the playlist.
LibraryItemID | The ID of the library item the playlist item to remove is for.
EpisodeID | The ID of the podcast episode the playlist item to remove is for.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Playlist Expanded](#playlist-expanded)
403 | Forbidden | The playlist does not belong to the authenticated user. |
404 | Not Found | No playlist with the provided ID exists, or the playlist does not contain the provided item. |


## Batch Add Items to a Playlist

```shell
curl -X POST "https://abs.example.com/api/playlists/pl_qbwet64998s5ra6dcu/batch/add" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"items": [{"libraryItemId": "li_8gch9ve09orgn4fdz8"}]}'
```

> The above command returns JSON structured like this:

```json
{
  "id": "pl_qbwet64998s5ra6dcu",
  "libraryId": "lib_c1u6t4p45c35rf0nzd",
  "userId": "root",
  "name": "The Best Books",
  "description": null,
  "coverPath": null,
  "items": [
    {
      "libraryItemId": "li_8gch9ve09orgn4fdz8",
      "episodeId": null,
      "libraryItem": {
        "id": "li_8gch9ve09orgn4fdz8",
        "ino": "649641337522215266",
        "libraryId": "lib_c1u6t4p45c35rf0nzd",
        "folderId": "fol_bev1zuxhb0j0s1wehr",
        "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule",
        "relPath": "Terry Goodkind/Sword of Truth/Wizards First Rule",
        "isFile": false,
        "mtimeMs": 1650621074299,
        "ctimeMs": 1650621074299,
        "birthtimeMs": 0,
        "addedAt": 1650621073750,
        "updatedAt": 1650621110769,
        "lastScan": 1651830827825,
        "scanVersion": "2.0.21",
        "isMissing": false,
        "isInvalid": false,
        "mediaType": "book",
        "media": {
          "libraryItemId": "li_8gch9ve09orgn4fdz8",
          "metadata": {
            "title": "Wizards First Rule",
            "titleIgnorePrefix": "Wizards First Rule",
            "subtitle": null,
            "authors": [
              {
                "id": "aut_z3leimgybl7uf3y4ab",
                "name": "Terry Goodkind"
              }
            ],
            "narrators": [
              "Sam Tsoutsouvas"
            ],
            "series": [
              {
                "id": "ser_cabkj4jeu8be3rap4g",
                "name": "Sword of Truth",
                "sequence": "1"
              }
            ],
            "genres": [
              "Fantasy"
            ],
            "publishedYear": "2008",
            "publishedDate": null,
            "publisher": "Brilliance Audio",
            "description": "The masterpiece that started Terry Goodkind's New York Times bestselling epic Sword of Truth In the aftermath of the brutal murder of his father, a mysterious woman, Kahlan Amnell, appears in Richard Cypher's forest sanctuary seeking help...and more. His world, his very beliefs, are shattered when ancient debts come due with thundering violence. In a dark age it takes courage to live, and more than mere courage to challenge those who hold dominion, Richard and Kahlan must take up that challenge or become the next victims. Beyond awaits a bewitching land where even the best of their hearts could betray them. Yet, Richard fears nothing so much as what secrets his sword might reveal about his own soul. Falling in love would destroy them - for reasons Richard can't imagine and Kahlan dare not say. In their darkest hour, hunted relentlessly, tormented by treachery and loss, Kahlan calls upon Richard to reach beyond his sword - to invoke within himself something more noble. Neither knows that the rules of battle have just changed...or that their time has run out. Wizard's First Rule is the beginning. One book. One Rule. Witness the birth of a legend.",
            "isbn": null,
            "asin": "B002V0QK4C",
            "language": null,
            "explicit": false,
            "authorName": "Terry Goodkind",
            "authorNameLF": "Goodkind, Terry",
            "narratorName": "Sam Tsoutsouvas",
            "seriesName": "Sword of Truth"
          },
          "coverPath": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
          "tags": [
            "Favorite"
          ],
          "audioFiles": [
            {
              "index": 1,
              "ino": "649644248522215260",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "size": 48037888,
                "mtimeMs": 1632223180278,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              },
              "addedAt": 1650621074131,
              "updatedAt": 1651830828023,
              "trackNumFromMeta": 1,
              "discNumFromMeta": null,
              "trackNumFromFilename": 1,
              "discNumFromFilename": null,
              "manuallyVerified": false,
              "invalid": false,
              "exclude": false,
              "error": null,
              "format": "MP2/3 (MPEG audio layer 2/3)",
              "duration": 6004.6675,
              "bitRate": 64000,
              "language": null,
              "codec": "mp3",
              "timeBase": "1/14112000",
              "channels": 2,
              "channelLayout": "stereo",
              "chapters": [],
              "embeddedCoverArt": null,
              "metaTags": {
                "tagAlbum": "SOT Bk01",
                "tagArtist": "Terry Goodkind",
                "tagGenre": "Audiobook Fantasy",
                "tagTitle": "Wizards First Rule 01",
                "tagTrack": "01/20",
                "tagAlbumArtist": "Terry Goodkind",
                "tagComposer": "Terry Goodkind"
              },
              "mimeType": "audio/mpeg"
            },
            {
              "index": 2,
              "ino": "649644248522215261",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "size": 47972352,
                "mtimeMs": 1632223180281,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              },
              "addedAt": 1650621074130,
              "updatedAt": 1651830828023,
              "trackNumFromMeta": 2,
              "discNumFromMeta": null,
              "trackNumFromFilename": 1,
              "discNumFromFilename": null,
              "manuallyVerified": false,
              "invalid": false,
              "exclude": false,
              "error": null,
              "format": "MP2/3 (MPEG audio layer 2/3)",
              "duration": 5996.2785,
              "bitRate": 64000,
              "language": null,
              "codec": "mp3",
              "timeBase": "1/14112000",
              "channels": 2,
              "channelLayout": "stereo",
              "chapters": [],
              "embeddedCoverArt": null,
              "metaTags": {
                "tagAlbum": "SOT Bk01",
                "tagArtist": "Terry Goodkind",
                "tagGenre": "Audiobook Fantasy",
                "tagTitle": "Wizards First Rule 02",
                "tagTrack": "02/20",
                "tagAlbumArtist": "Terry Goodkind",
                "tagComposer": "Terry Goodkind"
              },
              "mimeType": "audio/mpeg"
            }
          ],
          "chapters": [
            {
              "id": 0,
              "start": 0,
              "end": 6004.6675,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01"
            },
            {
              "id": 1,
              "start": 6004.6675,
              "end": 12000.946,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02"
            }
          ],
          "duration": 33854.905,
          "size": 268824228,
          "tracks": [
            {
              "index": 1,
              "startOffset": 0,
              "duration": 6004.6675,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "contentUrl": "/s/item/li_8gch9ve09orgn4fdz8/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "mimeType": "audio/mpeg",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "size": 48037888,
                "mtimeMs": 1632223180278,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              }
            },
            {
              "index": 2,
              "startOffset": 6004.6675,
              "duration": 5996.2785,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "contentUrl": "/s/item/li_8gch9ve09orgn4fdz8/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "mimeType": "audio/mpeg",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 03.mp3",
                "size": 47972352,
                "mtimeMs": 1632223180281,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              }
            }
          ],
          "missingParts": [],
          "ebookFile": null
        },
        "libraryFiles": [
          {
            "ino": "649644248522215260",
            "metadata": {
              "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "ext": ".mp3",
              "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "size": 48037888,
              "mtimeMs": 1632223180278,
              "ctimeMs": 1645978261001,
              "birthtimeMs": 0
            },
            "addedAt": 1650621052494,
            "updatedAt": 1650621052494,
            "fileType": "audio"
          },
          {
            "ino": "649644248522215261",
            "metadata": {
              "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "ext": ".mp3",
              "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "size": 47972352,
              "mtimeMs": 1632223180281,
              "ctimeMs": 1645978261001,
              "birthtimeMs": 0
            },
            "addedAt": 1650621052494,
            "updatedAt": 1650621052494,
            "fileType": "audio"
          },
          {
            "ino": "649644248522215267",
            "metadata": {
              "filename": "cover.jpg",
              "ext": ".jpg",
              "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
              "relPath": "cover.jpg",
              "size": 325531,
              "mtimeMs": 1638754803540,
              "ctimeMs": 1645978261003,
              "birthtimeMs": 0
            },
            "addedAt": 1650621052495,
            "updatedAt": 1650621052495,
            "fileType": "image"
          }
        ],
        "size": 268990279
      }
    }
  ],
  "lastUpdate": 1669623431313,
  "createdAt": 1669623431313
}
```

This endpoint batch adds items to a playlist and returns the updated playlist.

### HTTP Request

`POST http://abs.example.com/api/playlists/<ID>/batch/add`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the playlist.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`items` | Array of [Playlist Item](#playlist-item) | The items to add to the playlist.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Playlist Expanded](#playlist-expanded)
400 | Bad Request | One or more of the provided items does not have a `libraryItemId`. |
403 | Forbidden | The playlist does not belong to the authenticated user. |
404 | Not Found | No playlist with the provided ID exists. |
500 | Internal Server Error | The provided `items` array was empty or did not exist. |


## Batch Remove Items From a Playlist

```shell
curl -X POST "https://abs.example.com/api/playlists/pl_qbwet64998s5ra6dcu/batch/remove" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"items": [{"libraryItemId": "li_8gch9ve09orgn4fdz8"}]}'
```

> The above command returns JSON structured like this:

```json
{
  "id": "pl_qbwet64998s5ra6dcu",
  "libraryId": "lib_c1u6t4p45c35rf0nzd",
  "userId": "root",
  "name": "The Best Books",
  "description": null,
  "coverPath": null,
  "items": [],
  "lastUpdate": 1669623431313,
  "createdAt": 1669623431313
}
```

This endpoint batch removes items from a playlist and returns the updated playlist. Then, if the playlist is empty, it will be deleted.

### HTTP Request

`POST http://abs.example.com/api/playlists/<ID>/batch/remove`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the playlist.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`items` | Array of [Playlist Item](#playlist-item) | The items to remove from the playlist.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Playlist Expanded](#playlist-expanded)
400 | Bad Request | One or more of the provided items does not have a `libraryItemId`. |
403 | Forbidden | The playlist does not belong to the authenticated user. |
404 | Not Found | No playlist with the provided ID exists. |
500 | Internal Server Error | The provided `items` array was empty or did not exist. |


## Create a Playlist From a Collection

```shell
curl -X POST "https://abs.example.com/api/playlists/collection/col_fpfstanv6gd7tq2qz7" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "id": "pl_qbwet64998s5ra6dcu",
  "libraryId": "lib_c1u6t4p45c35rf0nzd",
  "userId": "root",
  "name": "Favorites",
  "description": null,
  "coverPath": null,
  "items": [
    {
      "libraryItemId": "li_8gch9ve09orgn4fdz8",
      "episodeId": null,
      "libraryItem": {
        "id": "li_8gch9ve09orgn4fdz8",
        "ino": "649641337522215266",
        "libraryId": "lib_c1u6t4p45c35rf0nzd",
        "folderId": "fol_bev1zuxhb0j0s1wehr",
        "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule",
        "relPath": "Terry Goodkind/Sword of Truth/Wizards First Rule",
        "isFile": false,
        "mtimeMs": 1650621074299,
        "ctimeMs": 1650621074299,
        "birthtimeMs": 0,
        "addedAt": 1650621073750,
        "updatedAt": 1650621110769,
        "lastScan": 1651830827825,
        "scanVersion": "2.0.21",
        "isMissing": false,
        "isInvalid": false,
        "mediaType": "book",
        "media": {
          "libraryItemId": "li_8gch9ve09orgn4fdz8",
          "metadata": {
            "title": "Wizards First Rule",
            "titleIgnorePrefix": "Wizards First Rule",
            "subtitle": null,
            "authors": [
              {
                "id": "aut_z3leimgybl7uf3y4ab",
                "name": "Terry Goodkind"
              }
            ],
            "narrators": [
              "Sam Tsoutsouvas"
            ],
            "series": [
              {
                "id": "ser_cabkj4jeu8be3rap4g",
                "name": "Sword of Truth",
                "sequence": "1"
              }
            ],
            "genres": [
              "Fantasy"
            ],
            "publishedYear": "2008",
            "publishedDate": null,
            "publisher": "Brilliance Audio",
            "description": "The masterpiece that started Terry Goodkind's New York Times bestselling epic Sword of Truth In the aftermath of the brutal murder of his father, a mysterious woman, Kahlan Amnell, appears in Richard Cypher's forest sanctuary seeking help...and more. His world, his very beliefs, are shattered when ancient debts come due with thundering violence. In a dark age it takes courage to live, and more than mere courage to challenge those who hold dominion, Richard and Kahlan must take up that challenge or become the next victims. Beyond awaits a bewitching land where even the best of their hearts could betray them. Yet, Richard fears nothing so much as what secrets his sword might reveal about his own soul. Falling in love would destroy them - for reasons Richard can't imagine and Kahlan dare not say. In their darkest hour, hunted relentlessly, tormented by treachery and loss, Kahlan calls upon Richard to reach beyond his sword - to invoke within himself something more noble. Neither knows that the rules of battle have just changed...or that their time has run out. Wizard's First Rule is the beginning. One book. One Rule. Witness the birth of a legend.",
            "isbn": null,
            "asin": "B002V0QK4C",
            "language": null,
            "explicit": false,
            "authorName": "Terry Goodkind",
            "authorNameLF": "Goodkind, Terry",
            "narratorName": "Sam Tsoutsouvas",
            "seriesName": "Sword of Truth"
          },
          "coverPath": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
          "tags": [
            "Favorite"
          ],
          "audioFiles": [
            {
              "index": 1,
              "ino": "649644248522215260",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "size": 48037888,
                "mtimeMs": 1632223180278,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              },
              "addedAt": 1650621074131,
              "updatedAt": 1651830828023,
              "trackNumFromMeta": 1,
              "discNumFromMeta": null,
              "trackNumFromFilename": 1,
              "discNumFromFilename": null,
              "manuallyVerified": false,
              "invalid": false,
              "exclude": false,
              "error": null,
              "format": "MP2/3 (MPEG audio layer 2/3)",
              "duration": 6004.6675,
              "bitRate": 64000,
              "language": null,
              "codec": "mp3",
              "timeBase": "1/14112000",
              "channels": 2,
              "channelLayout": "stereo",
              "chapters": [],
              "embeddedCoverArt": null,
              "metaTags": {
                "tagAlbum": "SOT Bk01",
                "tagArtist": "Terry Goodkind",
                "tagGenre": "Audiobook Fantasy",
                "tagTitle": "Wizards First Rule 01",
                "tagTrack": "01/20",
                "tagAlbumArtist": "Terry Goodkind",
                "tagComposer": "Terry Goodkind"
              },
              "mimeType": "audio/mpeg"
            },
            {
              "index": 2,
              "ino": "649644248522215261",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "size": 47972352,
                "mtimeMs": 1632223180281,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              },
              "addedAt": 1650621074130,
              "updatedAt": 1651830828023,
              "trackNumFromMeta": 2,
              "discNumFromMeta": null,
              "trackNumFromFilename": 1,
              "discNumFromFilename": null,
              "manuallyVerified": false,
              "invalid": false,
              "exclude": false,
              "error": null,
              "format": "MP2/3 (MPEG audio layer 2/3)",
              "duration": 5996.2785,
              "bitRate": 64000,
              "language": null,
              "codec": "mp3",
              "timeBase": "1/14112000",
              "channels": 2,
              "channelLayout": "stereo",
              "chapters": [],
              "embeddedCoverArt": null,
              "metaTags": {
                "tagAlbum": "SOT Bk01",
                "tagArtist": "Terry Goodkind",
                "tagGenre": "Audiobook Fantasy",
                "tagTitle": "Wizards First Rule 02",
                "tagTrack": "02/20",
                "tagAlbumArtist": "Terry Goodkind",
                "tagComposer": "Terry Goodkind"
              },
              "mimeType": "audio/mpeg"
            }
          ],
          "chapters": [
            {
              "id": 0,
              "start": 0,
              "end": 6004.6675,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01"
            },
            {
              "id": 1,
              "start": 6004.6675,
              "end": 12000.946,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02"
            }
          ],
          "duration": 33854.905,
          "size": 268824228,
          "tracks": [
            {
              "index": 1,
              "startOffset": 0,
              "duration": 6004.6675,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "contentUrl": "/s/item/li_8gch9ve09orgn4fdz8/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "mimeType": "audio/mpeg",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
                "size": 48037888,
                "mtimeMs": 1632223180278,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              }
            },
            {
              "index": 2,
              "startOffset": 6004.6675,
              "duration": 5996.2785,
              "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "contentUrl": "/s/item/li_8gch9ve09orgn4fdz8/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "mimeType": "audio/mpeg",
              "metadata": {
                "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "ext": ".mp3",
                "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
                "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 03.mp3",
                "size": 47972352,
                "mtimeMs": 1632223180281,
                "ctimeMs": 1645978261001,
                "birthtimeMs": 0
              }
            }
          ],
          "missingParts": [],
          "ebookFile": null
        },
        "libraryFiles": [
          {
            "ino": "649644248522215260",
            "metadata": {
              "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "ext": ".mp3",
              "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
              "size": 48037888,
              "mtimeMs": 1632223180278,
              "ctimeMs": 1645978261001,
              "birthtimeMs": 0
            },
            "addedAt": 1650621052494,
            "updatedAt": 1650621052494,
            "fileType": "audio"
          },
          {
            "ino": "649644248522215261",
            "metadata": {
              "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "ext": ".mp3",
              "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3",
              "size": 47972352,
              "mtimeMs": 1632223180281,
              "ctimeMs": 1645978261001,
              "birthtimeMs": 0
            },
            "addedAt": 1650621052494,
            "updatedAt": 1650621052494,
            "fileType": "audio"
          },
          {
            "ino": "649644248522215267",
            "metadata": {
              "filename": "cover.jpg",
              "ext": ".jpg",
              "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
              "relPath": "cover.jpg",
              "size": 325531,
              "mtimeMs": 1638754803540,
              "ctimeMs": 1645978261003,
              "birthtimeMs": 0
            },
            "addedAt": 1650621052495,
            "updatedAt": 1650621052495,
            "fileType": "image"
          }
        ],
        "size": 268990279
      }
    }
  ],
  "lastUpdate": 1669623431313,
  "createdAt": 1669623431313
}
```

This endpoint creates a playlist from a collection. The newly created playlist is returned.

### HTTP Request

`POST http://abs.example.com/api/playlists/collection/<CollectionID>`

### URL Parameters

Parameter | Description
--------- | -----------
CollectionID | The ID of the collection.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Playlist Expanded](#playlist-expanded)
400 | Bad Request | The user cannot access any books contained in the collection. |
404 | Not Found | No collection with the given ID exists. |
