# Library Items

## Delete All Library Items

```shell
curl -X DELETE "https://abs.example.com/api/items/all" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint will delete all library items from the database. No actual files will be deleted.

### HTTP Request

`DELETE http://abs.example.com/api/items/all`

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
403 | Forbidden | An admin user is required to delete all library items.
500 | Internal Server Error | Something went wrong with recreating the library item database.


## Get a Library Item

```shell
curl "https://abs.example.com/api/items/li_8gch9ve09orgn4fdz8?expanded=1&include=progress,rssfeed,authors" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
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
          "asin": null,
          "name": "Terry Goodkind",
          "description": null,
          "imagePath": null,
          "relImagePath": null,
          "addedAt": 1650621073750,
          "updatedAt": 1650621073750
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
  "size": 268990279,
  "userMediaProgress": {
    "id": "li_8gch9ve09orgn4fdz8",
    "libraryItemId": "li_8gch9ve09orgn4fdz8",
    "episodeId": null,
    "duration": 6004.6675,
    "progress": 0.002710910637433297,
    "currentTime": 16.278117,
    "isFinished": false,
    "hideFromContinueListening": false,
    "lastUpdate": 1650621052495,
    "startedAt": 1650621052495,
    "finishedAt": null
  },
  "rssFeedUrl": null
}
```

This endpoint retrieves a library item.

### HTTP Request

`GET http://abs.example.com/api/items/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item to retrieve.

### Optional Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
`expanded` | Binary | Whether to return [Library Item Expanded](#library-item-expanded) instead. `0` for false, `1` for true.
`include` | String | A comma separated list of what to include with the library item. The options are: `progress`, `rssfeed`, `authors` (for books), and `downloads` (for podcasts). `expanded` must be `1` for `include` to have an effect.
`episode` | String | If requesting `progress` for a podcast, the episode ID to get progress for.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Library Item](#library-item) or, if `expanded` was requested, [Library Item Expanded](#library-item-expanded) with optional extra attributes (see below).

#### Extra Attributes

Attribute | Type | Description
--------- | ---- | -----------
`userMediaProgress` | [Media Progress](#media-progress) Object | If `progress` was requested, the user's progress for the book or podcast episode. If no progress exists, neither will this attribute.
`rssFeedUrl` | String or null | If `rssfeed` was requested, the rebroadcasting RSS feed URL of the library item. Will be `null` if the RSS feed for this library item is disabled.
`media.metadata.authors` | Array of [Author](#author) | If `authors` was requested, replaces the normally minified authors in the metadata.
`episodesDownloading` | Array of [Podcast Episode Download](#podcast-episode-download) | If `downloads` was requested, the podcast episodes currently in the download queue.


## Delete a Library Item

```shell
curl -X DELETE "https://abs.example.com/api/items/li_8gch9ve09orgn4fdz8" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint deletes a library item from the database. No files are deleted.

### HTTP Request

`DELETE http://abs.example.com/api/items/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item to delete.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success


## Update a Library Item's Media

```shell
curl -X PATCH "https://abs.example.com/api/items/li_8gch9ve09orgn4fdz8/media" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"metadata": {"title": "Wizards First Rule"}}'
```

> The above command returns JSON structured like this:

```json
{
  "updated": true,
  "id": "li_8gch9ve09orgn4fdz8",
  "ino": "649641337522215266",
  "libraryId": "main",
  "folderId": "audiobooks",
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
          "sequence": null
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
      "explicit": false
    },
    "coverPath": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
    "tags": [],
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
  ]
}
```

This endpoint updates a library item's media and returns the updated library item.

### HTTP Request

`PATCH http://abs.example.com/api/items/<ID>/media`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item.

### Parameters

A library item's media can be either [Book Parameters](#book-parameters) or [Podcast Parameters](#podcast-parameters) (see below). Check the library item's `mediaType` before updating it.

#### Book Parameters

Parameter | Type | Description
--------- | ---- | -----------
`metadata` | [Book Metadata](#book-metadata-parameters) Object (See Below) | The book's metadata.
`coverPath` | String or null | The absolute path on the server of the cover file. Use `null` to remove the cover. Prefer using the [Update a Library Item's Cover](#update-a-library-item-39-s-cover) endpoint.
`tags` | Array of String | The book's tags.
`chapters` | Array of [Book Chapter](#book-chapter-parameters) | The book's chapters. Prefer using the [Update a Library Item's Chapters](#update-a-library-item-39-s-chapters) endpoint.

#### Book Metadata Parameters

Parameter | Type | Description
--------- | ---- | -----------
`title` | String or null | The title of the book.
`subtitle` | String or null | The subtitle of the book.
`authors` | Array of [Author](#author-parameters) (See Below) | The authors of the book.
`narrators` | Array of String | The narrators of the book.
`series` | Array of [Series Sequence](#series-parameters) (See Below) | The series the book belongs to.
`genres` | Array of String | The genres of the book.
`publishedYear` | String or null | The year the book was published.
`publishedDate` | String or null | The date the book was published.
`publisher` | String or null | The publisher of the book.
`description` | String or null | A description of the book.
`isbn` | String or null | The ISBN of the book.
`asin` | String or null | The ASIN of the book.
`language` | String or null | The language of the book.
`explicit` | Boolean | Whether to mark the book as explicit.

#### Author Parameters

The server will automatically find the ID of the author or create one.

Parameter | Type | Description
--------- | ---- | -----------
`name` | String | The name of the author.

#### Series Parameters

The server will automatically find the ID of the series or create one.

Parameter | Type | Description
--------- | ---- | -----------
`name` | String | The name of the series.
`sequence` | String or null | The position in the series the book is.

#### Podcast Parameters

Parameter | Type | Description
--------- | ---- | -----------
`metadata` | [Podcast Metadata](#podcast-metadata-parameters) Object (See Below) | The podcast's metadata.
`coverPath` | String or null | The absolute path on the server of the cover file. Use `null` to remove the cover. Prefer using the [Update a Library Item's Cover](#update-a-library-item-39-s-cover) endpoint.
`tags` | Array of String | The podcast's tags.
`autoDownloadEpisodes` | Boolean | Whether the server will automatically download podcast episodes according to the schedule.
`autoDownloadSchedule` | String or null | The [cron expression](https://en.wikipedia.org/wiki/Cron#CRON_expression) for when to automatically download podcast episodes.
`lastEpisodeCheck` | Integer | The time (in ms since POSIX epoch) when the podcast was checked for new episodes.
`maxEpisodesToKeep` | Integer | The maximum number of podcast episodes to keep when automatically downloading new episodes. Episodes beyond this limit will be deleted. If `0`, all episodes will be kept.
`maxNewEpisodesToDownload` | Integer | The maximum number of podcast episodes to download when automatically downloading new episodes. If `0`, all episodes will be downloaded.

<aside class="notice">
Use the <a href="#update-a-podcast-episode">Update a Podcast Episode</a> endpoint to update a podcast's episodes.
</aside>

#### Podcast Metadata Parameters

Parameter | Type | Description
--------- | ---- | -----------
`title` | String or null | The title of the podcast.
`author` | String or null | The author of the podcast.
`description` | String or null | The description of the podcast.
`releaseDate` | String or null | The release date of the podcast.
`genres` | Array of String | The podcast's genres.
`feedUrl` | String or null | A URL of an RSS feed for the podcast.
`imageUrl` | String or null | A URL of a cover image for the podcast.
`itunesPageUrl` | String or null | A URL of an iTunes page for the podcast.
`itunesId` | Integer or null | The iTunes ID for the podcast.
`itunesArtistId` | Integer or null | The iTunes Artist ID for the author of the podcast.
`explicit` | Boolean | Whether to mark the podcast as explicit.
`language` | String or null | The language of the podcast.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Library Item](#library-item) with an `updated` attribute, a Boolean, whether anything was actually changed.


## Get a Library Item's Cover

```shell
curl "https://abs.example.com/api/items/li_8gch9ve09orgn4fdz8/cover" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  --output cover.webp
```

> The above command writes an image file.

This endpoint retrieves a library item's cover.

### HTTP Request

`GET http://abs.example.com/api/items/<ID>/cover`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item.

### Optional Query Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`width` | Integer | `400` | The requested width of the cover image.
`height` | Integer or null | `null` | The requested height of the cover image. If `null` the image is scaled proportionately.
`format` | String | `webp` or `jpeg` | The requested format of the cover image. The default value depends on the request headers.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
404 | Not Found | Either no library item exists with the given ID, or the item does not have a cover.
500 | Internal Server Error | There was an error when attempting to read the cover file.


## Upload a Library Item Cover

> Upload a cover image:

```shell
curl -X POST "https://abs.example.com/api/items/li_8gch9ve09orgn4fdz8/cover" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -F cover=@cover.jpg
```

> Or download a cover image from a URL:

```shell
curl -X POST "https://abs.example.com/api/items/li_8gch9ve09orgn4fdz8/cover" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"url": "https://m.media-amazon.com/images/I/51xUwj8eKVL._SL500_.jpg"}'
```

> The above commands return JSON structured like this:

```json
{
  "success": true,
  "cover": "/metadata/items/li_8gch9ve09orgn4fdz8/cover.jpg"
}
```

This endpoint uploads a cover for a library item or requests the server to download a cover from a specified URL.

### HTTP Request

`POST http://abs.example.com/api/items/<ID>/cover`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item.

### Form Parameters

Parameter | Type | Description
--------- | ---- | -----------
`cover` | Image Binary Data | The cover to upload.

### JSON Parameters

Parameter | Type | Description
--------- | ---- | -----------
`url` | String | The URL to download the cover from.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
400 | Bad Request | The request did not contain a file or URL.
403 | Forbidden | The user does not have permission to upload.
500 | Internal Server Error | Unknown error.

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`success` | Boolean | Whether the upload was successful.
`cover` | String | The full path of the cover on the server.


## Update a Library Item's Cover

```shell
curl -X PATCH "https://abs.example.com/api/items/li_8gch9ve09orgn4fdz8/cover" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"cover": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg"}'
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "cover": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg"
}
```

This endpoint updates a library item's cover with an image already on the server.

### HTTP Request

`PATCH http://abs.example.com/api/items/<ID>/cover`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`cover` | String | The absolute path of the image on the server to change the library item's cover to.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
400 | Bad Request | The `cover` parameter is required.
500 | Internal Server Error | Either the submitted path is invalid, does not exist, is not an image, or the server failed to copy the image to the library item's directory.

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`success` | Boolean | Whether the cover was updated successfully.
`cover` | String | The absolute path on the server of the library item's cover.


## Remove a Library Item's Cover

```shell
curl -X DELETE "https://abs.example.com/api/items/li_8gch9ve09orgn4fdz8/cover" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint removes a library item's cover.

### HTTP Request

`DELETE http://abs.example.com/api/items/<ID>/cover`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success


## Match a Library Item

```shell
curl -X POST "https://abs.example.com/api/items/li_8gch9ve09orgn4fdz8/match" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"provider": "openlibrary"}'
```

> The above command returns JSON structured like this:

```json
{
  "updated": true,
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
```

This endpoint matches the library item using quick match. Quick match populates empty book details and the cover with the first book result. Does not overwrite details unless the "Prefer matched metadata" server setting is enabled or the `overrideDefaults` parameter is `true`.

### HTTP Request

`POST http://abs.example.com/api/items/<ID>/match`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item.

### Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`provider` | String | `google` | The metadata provider to search. See [Metadata Providers](#metadata-providers) for a list of options.
`title` | String | The library item's title. | The title to search for.
`author` | String | The library item's author. | The author to search for.
`overrideDefaults` | Boolean | `false` | Whether to override the existing book details and cover. This will be `true` if the "Prefer matched metadata" server setting is enabled.
`isbn` | String | The book's ISBN. | If the library item is a book, the ISBN to search for.
`asin` | String | The book's ASIN. | If the library item is a book, the ASIN to search for.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`updated` | Boolean | Whether the library item was actually updated with new information.
`libraryItem` | [Library Item Expanded](#library-item-expanded) Object | The updated library item.


## Play a Library Item or Podcast Episode

```shell
curl -X POST "https://abs.example.com/api/items/li_bufnnmp4y5o2gbbxfm/play/ep_lh6ko39pumnrma3dhv" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"deviceInfo": {"clientVersion": "0.0.1"}, "supportedMimeTypes": ["audio/flac", "audio/mpeg", "audio/mp4"]}'
```

> The above command returns JSON structured like this:

```json
{
  "id": "play_c786zm3qtjz6bd5q3n",
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
  "mediaPlayer": "unknown",
  "deviceInfo": {
    "ipAddress": "192.168.1.118",
    "clientVersion": "0.0.1",
    "serverVersion": "2.2.2"
  },
  "date": "2022-11-11",
  "dayOfWeek": "Friday",
  "timeListening": 0,
  "startTime": 0,
  "currentTime": 0,
  "startedAt": 1668206493239,
  "updatedAt": 1668206493239,
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
    "mtimeMs": 1667326679508,
    "ctimeMs": 1667326679508,
    "birthtimeMs": 1667326662083,
    "addedAt": 1667326662087,
    "updatedAt": 1668157565937,
    "lastScan": 1667327311529,
    "scanVersion": "2.2.1",
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
            "updatedAt": 1667327311570,
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

This endpoint starts a playback session for a library item or podcast episode.

### HTTP Request

* `POST http://abs.example.com/api/items/<ID>/play`
* `POST http://abs.example.com/api/items/<ID>/play/<EpisodeID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item.
EpisodeID | The ID of the podcast episode.

### Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`deviceInfo` | [Device Info Parameters](#device-info-parameters) Object (See Below) | | Information about the device.
`forceDirectPlay` | Boolean | `false` | Whether to force direct play of the library item.
`forceTranscode` | Boolean | `false` | Whether to force the server to transcode the audio.
`supportedMimeTypes` | Array of String | `[]` | The MIME types that are supported by the client. If the MIME type of the audio file is not in this list, the server will transcode it.
`mediaPlayer` | String | `unknown` | The media player the client is using.

#### Device Info Parameters

Parameter | Type | Description
--------- | ---- | -----------
`clientVersion` | String | The version of the client.
`manufacturer` | String | The manufacturer of the client device.
`model` | String | The model of the client device.
`sdkVersion` | Integer | For an Android client, the Android SDK version of the client.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Playback Session Expanded](#playback-session-expanded)
404 | Not Found | The library item does not have any audio tracks to play. |


## Update a Library Item's Audio Tracks

```shell
curl -X PATCH "https://abs.example.com/api/items/li_bufnnmp4y5o2gbbxfm/tracks" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"orderedFileData": [{"ino": "649644248522215260"}, {"ino": "649644248522215261"}]}'
```

> The above command returns JSON structured like this:

```json
{
  "id": "li_8gch9ve09orgn4fdz8",
  "ino": "649641337522215266",
  "libraryId": "main",
  "folderId": "audiobooks",
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
          "sequence": null
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
      "explicit": false
    },
    "coverPath": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
    "tags": [],
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
  ]
}
```

This endpoint updates the order of and whether to exclude a library item's audio files. This only applies to books. The updated library item is returned.

### HTTP Request

`PATCH http://abs.example.com/api/items/<ID>/tracks`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`orderedFileData` | Array of [Audio File Data Parameters](#audio-file-data-parameters) (See Below) | The audio file data in the wanted order.

<aside class="warning">
Make sure to include all audio files of a library item in the array.
</aside>

#### Audio File Data Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`ino` | String | **Required** | The inode of the audio file. This is how the server matches this entry to the correct audio file.
`exclude` | Boolean | `false` | Whether to exclude the audio file from playback. Excluded audio files will have their `index` set to `-1`.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Library Item](#library-item)
500 | Internal Server Error | The library item's media type must be `book` for this endpoint.


## Scan a Library Item

```shell
curl "https://abs.example.com/api/items/li_bufnnmp4y5o2gbbxfm/scan" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "result": "UPDATED"
}
```

This endpoint scans a library item's files for changes.

### HTTP Request

`GET http://abs.example.com/api/items/<ID>/scan`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
403 | Forbidden | An admin user is required to scan a library item. |
500 | Internal Server Error | Rescanning file library items is not yet supported. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`result` | String | The result of the scan operation. Can be `NOTHING`, `ADDED`, `UPDATED`, `REMOVED`, or `UPTODATE`.


## Get a Library Item's Tone Metadata Object

```shell
curl "https://abs.example.com/api/items/li_bufnnmp4y5o2gbbxfm/tone-object" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "Title": "Wizards First Rule",
  "Album": "Wizards First Rule",
  "TrackTotal": 2,
  "Artist": "Terry Goodkind",
  "AlbumArtist": "Terry Goodkind",
  "Comment": "The masterpiece that started Terry Goodkind's New York Times bestselling epic Sword of Truth In the aftermath of the brutal murder of his father, a mysterious woman, Kahlan Amnell, appears in Richard Cypher's forest sanctuary seeking help...and more. His world, his very beliefs, are shattered when ancient debts come due with thundering violence. In a dark age it takes courage to live, and more than mere courage to challenge those who hold dominion, Richard and Kahlan must take up that challenge or become the next victims. Beyond awaits a bewitching land where even the best of their hearts could betray them. Yet, Richard fears nothing so much as what secrets his sword might reveal about his own soul. Falling in love would destroy them - for reasons Richard can't imagine and Kahlan dare not say. In their darkest hour, hunted relentlessly, tormented by treachery and loss, Kahlan calls upon Richard to reach beyond his sword - to invoke within himself something more noble. Neither knows that the rules of battle have just changed...or that their time has run out. Wizard's First Rule is the beginning. One book. One Rule. Witness the birth of a legend.",
  "Description": "The masterpiece that started Terry Goodkind's New York Times bestselling epic Sword of Truth In the aftermath of the brutal murder of his father, a mysterious woman, Kahlan Amnell, appears in Richard Cypher's forest sanctuary seeking help...and more. His world, his very beliefs, are shattered when ancient debts come due with thundering violence. In a dark age it takes courage to live, and more than mere courage to challenge those who hold dominion, Richard and Kahlan must take up that challenge or become the next victims. Beyond awaits a bewitching land where even the best of their hearts could betray them. Yet, Richard fears nothing so much as what secrets his sword might reveal about his own soul. Falling in love would destroy them - for reasons Richard can't imagine and Kahlan dare not say. In their darkest hour, hunted relentlessly, tormented by treachery and loss, Kahlan calls upon Richard to reach beyond his sword - to invoke within himself something more noble. Neither knows that the rules of battle have just changed...or that their time has run out. Wizard's First Rule is the beginning. One book. One Rule. Witness the birth of a legend.",
  "Narrator": "Sam Tsoutsouvas",
  "Composer": "Sam Tsoutsouvas",
  "MovementName": "Sword of Truth",
  "Movement": "1",
  "Genre": "Fantasy",
  "Publisher": "Brilliance Audio",
  "CoverFile": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
  "PublishingDate": "01/01/2008",
  "AdditionalFields": [
    "ASIN=B002V0QK4C"
  ]
}
```

This endpoint returns a library item's tone metadata object.

### HTTP Request

`GET http://abs.example.com/api/items/<ID>/tone-object`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
403 | Forbidden | An admin user is required to get a library item's tone metadata object. |
500 | Internal Server Error | The library item has missing parts, does not have audio files, or is not a book. |

#### Response Schema

Book metadata that is `null` will not exist in the response object, except for the title which will be replaced by an empty string.

Attribute | Type | Description
--------- | ---- | -----------
`Title` | String | The book's title.
`Album` | String | The book's title.
`TrackTotal` | Integer | The number of audio tracks for the book.
`Artist` | String | The book's author.
`AlbumArtist` | String | The book's author.
`Comment` | String | The book's description.
`Description` | String | The book's description.
`Narrator` | String | The book's narrators.
`Composer` | String | The book's narrators.
`MovementName` | String | The book's first series.
`Movement` | String | The sequence of the book in its first series.
`Genre` | String | All of the book's genres `/` separated.
`Publisher` | String | The book's publisher.
`CoverFile` | String | The book's cover path.
`PublishingDate` | String | January 1st of the book's published year.
`AdditionalFields` | Array of String | Additional metadata fields. Those are currently ASIN and ISBN.


## Update a Library Item's Chapters

```shell
curl -X POST "https://abs.example.com/api/items/li_bufnnmp4y5o2gbbxfm/chapters" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"chapters": [{"id": 0, "start": 0, "end": 6004.6675, "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01"}, {"id": 1, "start": 6004.6675, "end": 12000.946, "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 02"}]}'
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "updated": false
}
```

This endpoint updates a library item's chapters. This only applies to books.

### HTTP Request

`POST http://abs.example.com/api/items/<ID>/chapters`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`chapters` | Array of [Book Chapter](#book-chapter) | The requested book chapters, in order.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
400 | Bad Request | The provided chapter list must have a non-zero length. |
403 | Forbidden | The user does not have permission to update a library item. |
500 | Internal Server Error | The library item has missing parts, does not have audio files, or is not a book. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`success` | Boolean | Whether the update succeeded.
`updated` | Boolean | Whether the book's chapters were actually changed.


## Open an RSS Feed for a Library Item

```shell
curl -X POST "https://abs.example.com/api/items/li_bufnnmp4y5o2gbbxfm/open-feed" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"serverAddress": "https://abs.example.com", "slug": "li_bufnnmp4y5o2gbbxfm"}'
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "feedUrl": "https://abs.example.com/feed/li_bufnnmp4y5o2gbbxfm"
}
```

This endpoint opens an RSS feed for a library item.

### HTTP Request

`POST http://abs.example.com/api/items/<ID>/open-feed`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`serverAddress` | String | The URL address of the server.
`slug` | String | The slug (the last part of the URL) to use for the RSS feed.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
403 | Forbidden | An admin user is required to open an RSS feed. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`success` | Boolean | Whether the RSS feed was successfully opened.
`error` | String | The error that occurred. Will only exist if `success` is `false`.
`feedUrl` | String | The URL where the feed was opened. Will only exist if `success` is `true`.


## Close an RSS Feed for a Library Item

```shell
curl -X POST "https://abs.example.com/api/items/li_bufnnmp4y5o2gbbxfm/close-feed" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint closes the RSS feed for a library item.

### HTTP Request

`POST http://abs.example.com/api/items/<ID>/close-feed`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
500 | Internal Server Error | An admin user is required to close an RSS feed.


## Tone Scan a Library Item

```shell
curl -X POST "https://abs.example.com/api/items/li_bufnnmp4y5o2gbbxfm/tone-scan/1" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "audio": {
    "bitrate": 64,
    "format": "MPEG Audio (Layer III)",
    "formatShort": "MPEG",
    "sampleRate": 22050,
    "duration": 6004667,
    "channels": {
      "count": 2,
      "description": "Joint Stereo"
    },
    "frames": {
      "offset": 3857,
      "length": 66381321
    },
    "metaFormat": [
      "id3V23",
      "id3V1"
    ]
  },
  "meta": {
    "album": "Sword of Truth",
    "albumArtist": "Terry Goodkind",
    "artist": "Terry Goodkind",
    "composer": "Sam Tsoutsouvas",
    "comment": "The masterpiece that started Terry Goodkind's New York Times bestselling epic Sword of Truth In the aftermath of the brutal murder of his father, a mysterious woman, Kahlan Amnell, appears in Richard Cypher's forest sanctuary seeking help...and more. His world, his very beliefs, are shattered when ancient debts come due with thundering violence. In a dark age it takes courage to live, and more than mere courage to challenge those who hold dominion, Richard and Kahlan must take up that challenge or become the next victims. Beyond awaits a bewitching land where even the best of their hearts could betray them. Yet, Richard fears nothing so much as what secrets his sword might reveal about his own soul. Falling in love would destroy them - for reasons Richard can't imagine and Kahlan dare not say. In their darkest hour, hunted relentlessly, tormented by treachery and loss, Kahlan calls upon Richard to reach beyond his sword - to invoke within himself something more noble. Neither knows that the rules of battle have just changed...or that their time has run out. Wizard's First Rule is the beginning. One book. One Rule. Witness the birth of a legend.",
    "encoderSettings": "LAME 32bits version 3.99.5 (http://lame.sf.net)",
    "genre": "Fantasy",
    "recordingDate": "2008-01-01T00:00:00",
    "title": "Wizards First Rule",
    "trackNumber": 1,
    "additionalFields": {
      "ufid": "FID",
      "narratedby": "ARRATEDBY",
      "woas": "OAS"
    }
  },
  "file": {
    "size": 48037888,
    "created": "2022-04-22T09:51:14.299+00:00",
    "modified": "2022-04-22T09:51:14.299+00:00",
    "accessed": "2022-04-22T09:51:14.299+00:00",
    "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule",
    "name": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3"
  }
}
```

This endpoint uses [tone](https://github.com/sandreas/tone) to scan a library item and returns the results.

### HTTP Request

`POST http://abs.example.com/api/items/<ID>/tone-scan/<Index?>`

### URL Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
ID | String | **Required** | The ID of the library item.
Index | Integer | `1` | The index of the audio file to tone scan.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
404 | Not Found | The library does not have any audio files to scan or the requested audio file index does not exist. |

#### Response Schema

See [tone](https://github.com/sandreas/tone) for details.

Attribute | Type | Description
--------- | ---- | -----------
`audio.bitrate` | Integer | The bitrate of the audio file.
`audio.format` | String | The format of the audio file.
`audio.formatShort` | String | The short format of the audio file.
`audio.duration` | Integer | The duration (in ms) of the audio file.
`audio.channels.count` | Integer | The number of audio channels in the audio file.
`audio.channels.description` | String | The description of the channel setup of the audio file.
`audio.frames.offset` | Integer | The frame offset of the audio file.
`audio.frames.length` | Integer | The frame length of the audio file.
`audio.metaFormat` | Array of String | The metadata formats of the audio file.
`meta` | Object | The metadata tags of the audio file.
`file.size` | Integer | The size (in bytes) of the audio file.
`file.created` | String | When the audio file was created.
`file.modified` | String | When the audio file was last modified.
`file.accessed` | String | When the audio file was last accessed.
`file.path` | String | The parent path of the audio file.
`file.name` | String | The filename of the audio file.


## Batch Delete Library Items

```shell
curl -X POST "https://abs.example.com/api/items/batch/delete" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"libraryItemIds: ["li_bufnnmp4y5o2gbbxfm"]}'
```

This endpoint batch deletes library items from the database. No files are deleted.

### HTTP Request

`POST http://abs.example.com/api/items/batch/delete`

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`libraryItemIds` | Array of String | The IDs of library items to delete.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
403 | Forbidden | The user does not have permission to delete library items.
404 | Not Found | None of the IDs provided match any library items.
500 | Internal Server Error | The `libraryItemIds` array must have a non-zero length.


## Batch Update Library Items

```shell
curl -X POST "https://abs.example.com/api/items/batch/update" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '["id": "li_8gch9ve09orgn4fdz8", "mediaPayload": {"metadata": {"title": "Wizards First Rule"}}]'
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "updates": 1
}
```

This endpoint batch updates library items.

### HTTP Request

`POST http://abs.example.com/api/items/batch/update`

### Parameters

Provide an array of objects with the following parameters:

Parameter | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the library item to update.
`mediaPayload` | [Book Parameters](#book-parameters) or [Podcast Parameters](#podcast-parameters) | See [Update a Library Item's Media](#update-a-library-item-39-s-media) for details.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
403 | Forbidden | The user does not have permission to update library items. |
500 | Internal Server Error | The provided array must have a non-zero length. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`success` | Boolean | Whether library items were updated successfully.
`updates` | Integer | The number library items that were actually changed.


## Batch Get Library Items

```shell
curl -X POST "https://abs.example.com/api/items/batch/get" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"libraryItemIds: ["li_8gch9ve09orgn4fdz8"]}'
```

> The above command returns JSON structured like this:

```json
[
  {
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
]
```

This endpoint batch gets library items.

### HTTP Request

`POST http://abs.example.com/api/items/batch/get`

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`libraryItemIds` | Array of String | The IDs of library items to get.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | Array of [Library Item Expanded](#library-item-expanded)
403 | Forbidden | The `libraryItemIds` array must have a non-zero length. |


## Batch Quick Match Library Items

```shell
curl -X POST "https://abs.example.com/api/items/batch/quickmatch" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"options": {"provider": "openlibrary"}, "libraryItemIds: ["li_8gch9ve09orgn4fdz8"]}'
```

This endpoint batch matches library items using quick match. Quick match populates empty book details and the cover with the first book result. Does not overwrite existing details unless the "Prefer matched metadata" server setting is enabled or the `overrideDefaults` parameter is `true`.

### HTTP Request

`POST http://abs.example.com/api/items/batch/quickmatch`

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`options` | [Options Parameters](#options-parameters) Object (See Below) | The options to use when quick matching.
`libraryItemIds` | Array of String | The IDs of library items to quick match.

#### Options Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`provider` | String | `google` | The metadata provider to search. See [Metadata Providers](#metadata-providers) for a list of options.
`overrideDefaults` | Boolean | `false` | Whether to override the existing book details and cover. This will be `true` if the "Prefer matched metadata" server setting is enabled.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
403 | Forbidden | An admin user is required to quick match library items.
500 | Internal Server Error | The `libraryItemIds` array must have a non-zero length.
