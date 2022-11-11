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
`expanded` | Binary | Whether or not to return [Library Item Expanded](#library-item-expanded) instead. `0` for false, `1` for true.
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

A library item's media can be either a [Book](#book-parameters) or [Podcast](#podcast-parameters) (see below). Check the library item's `mediaType` before updating it.

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
`explicit` | Boolean | Whether or not to mark the book as explicit.

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
`autoDownloadEpisodes` | Boolean | Whether or not the server will automatically download podcast episodes according to the schedule.
`autoDownloadSchedule` | String or null | The [cron expression](https://en.wikipedia.org/wiki/Cron#CRON_expression) for when to automatically download podcast episodes.
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
`explicit` | Boolean | Whether or not to mark the podcast as explicit.
`language` | String or null | The language of the podcast.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Library Item](#library-item) with a `updated` attribute, a Boolean, whether or not anything was actually changed.


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
400 | Bad Request | There was an internal server error when attempting to read the cover file.
404 | Not Found | Either no library item exists with the given ID, or the item does not have a cover.


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

Parameter | Type | Description
--------- | ---- | -----------
`success` | Boolean | Whether or not the upload was successful.
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

This endpoint updates a library item's cover with a image already on the server.

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
400 | Bad Request | The request did not contain a file or URL.
500 | Internal Server Error | Either the submitted path is invalid, does not exist, is not an image, or the server failed to copy the image to the library item's directory.

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`success` | Boolean | Whether or not the cover was updated successfully.
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
