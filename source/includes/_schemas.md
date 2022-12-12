# Schemas

## Library

> Library

```json
{
  "id": "lib_c1u6t4p45c35rf0nzd",
  "name": "Main",
  "folders": [...],
  "displayOrder": 1,
  "icon": "audiobookshelf",
  "mediaType": "book",
  "provider": "audible",
  "settings": {...},
  "createdAt": 1633522963509,
  "lastUpdate": 1646520916818
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the library. (Read Only)
`name` | String | The name of the library.
`folders` | Array of [Folder](#folder) | The folders that the library is composed of on the server.
`displayOrder` | Integer | Display position of the library in the list of libraries. Must be `>= 1`.  
`icon` | String | The selected icon for the library. See [Library Icons](#library-icons) for a list of possible icons.
`mediaType` | String | The type of media that the library contains. Will be `book` or `podcast`. (Read Only)
`provider` | String | Preferred metadata provider for the library. See [Metadata Providers](#metadata-providers) for a list of possible providers.
`settings` | [Library Settings](#library-settings) Object | The settings for the library.
`createdAt` | Integer | The time (in ms since POSIX epoch) when the library was created. (Read Only)
`lastUpdate` | Integer | The time (in ms since POSIX epoch) when the library was last updated. (Read Only)


## Library Settings

> Library Settings

```json
{
  "coverAspectRatio": 1,
  "disableWatcher": false,
  "skipMatchingMediaWithAsin": false,
  "skipMatchingMediaWithIsbn": false,
  "autoScanCronExpression": null
}
```

Attribute | Type | Description
--------- | ---- | -----------
`coverAspectRatio` | Integer | Whether the library should use square book covers. Must be `0` (for false) or `1` (for true).
`disableWatcher` | Boolean | Whether to disable the folder watcher for the library.
`skipMatchingMediaWithAsin` | Boolean | Whether to skip matching books that already have an ASIN.
`skipMatchingMediaWithIsbn` | Boolean | Whether to skip matching books that already have an ISBN.
`autoScanCronExpression` | String or null | The [cron expression](https://en.wikipedia.org/wiki/Cron#CRON_expression) for when to automatically scan the library folders. If `null`, automatic scanning will be disabled.


## Library Filter Data

> Library Filter Data

```json
{
  "authors": [
    {
      "id": "aut_z3leimgybl7uf3y4ab",
      "name": "Terry Goodkind"
    }
  ],
  "genres": [
    "Fantasy"
  ],
  "tags": [],
  "series": [
    {
      "id": "ser_cabkj4jeu8be3rap4g",
      "name": "Sword of Truth"
    }
  ],
  "narrators": [
    "Sam Tsoutsouvas"
  ],
  "languages": []
}
```

Attribute | Type | Description
--------- | ---- | -----------
`authors` | Array of [Author Minified](#author-minified) | The authors of books in the library.
`genres` | Array of String | The genres of books in the library.
`tags` | Array of String | The tags in the library.
`series` | Array of [Series](#series) | The series in the library. The series will only have their `id` and `name`.
`narrators` | Array of String | The narrators of books in the library.
`languages` | Array of String | The languages of books in the library.


## Folder

> Folder

```json
{
  "id": "fol_bev1zuxhb0j0s1wehr",
  "fullPath": "/podcasts",
  "libraryId": "lib_c1u6t4p45c35rf0nzd",
  "addedAt": 1650462940610
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the folder. (Read Only) 
`fullPath` | String | The path on the server for the folder. (Read Only)
`libraryId` | String | The ID of the library the folder belongs to. (Read Only)
`addedAt` | Integer | The time (in ms since POSIX epoch) when the folder was added. (Read Only)

<aside class="notice">
  Only provide <code>fullPath</code> when creating a new folder. The other attributes will be automatically set.
</aside>


## Library Item

> Library Item

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
  "media": {...},
  "libraryFiles": [...]
}
```

> Library Item Minified

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
  "isMissing": false,
  "isInvalid": false,
  "mediaType": "book",
  "media": {...},
  "numFiles": 2,
  "size": 268990279
}
```

> Library Item Expanded

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
  "media": {...},
  "libraryFiles": [...],
  "size": 268990279
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the library item.
`ino` | String | The inode of the library item.
`libraryId` | String | The ID of the library the item belongs to.
`folderId` | String | The ID of the folder the library item is in.
`path` | String | The path of the library item on the server.
`relPath` | String | The path, relative to the library folder, of the library item.
`isFile` | Boolean | Whether the library item is a single file in the root of the library folder.
`mtimeMs` | Integer | The time (in ms since POSIX epoch) when the library item was last modified on disk.
`ctimeMs` | Integer | The time (in ms since POSIX epoch) when the library item status was changed on disk.
`birthtimeMs` | Integer | The time (in ms since POSIX epoch) when the library item was created on disk. Will be `0` if unknown.
`addedAt` | Integer | The time (in ms since POSIX epoch) when the library item was added to the library.
`updatedAt` | Integer | The time (in ms since POSIX epoch) when the library item was last updated. (Read Only)
`lastScan` | Integer or null | The time (in ms since POSIX epoch) when the library item was last scanned. Will be `null` if the server has not yet scanned the library item.
`scanVersion` | String or null | The version of the scanner when last scanned. Will be `null` if it has not been scanned.
`isMissing` | Boolean | Whether the library item was scanned and no longer exists.
`isInvalid` | Boolean | Whether the library item was scanned and no longer has media files.
`mediaType` | String | What kind of media the library item contains. Will be `book` or `podcast`.
`media` | [Book](#book) or [Podcast](#podcast) Object | The media of the library item.
`libraryFiles` | Array of [Library File](#library-file) | The files of the library item.

### Library Item Minified

#### Removed Attributes

* `lastScan`
* `scanVersion`
* `libraryFiles`

#### Modified Attributes

* `media` is [Book Minified](#book-minified) or [Podcast Minified](#podcast-minified)

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`numFiles` | Integer | The number of library files for the library item.
`size` | Integer | The total size (in bytes) of the library item.

### Library Item Expanded

#### Modified Attributes

* `media` is [Book Expanded](#book-expanded) or [Podcast Expanded](#podcast-expanded)

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`size` | Integer | The total size (in bytes) of the library item.


## Book

> Book

```json
{
  "libraryItemId": "li_8gch9ve09orgn4fdz8",
  "metadata": {...},
  "coverPath": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
  "tags": [
    "Favorite"
  ],
  "audioFiles": [...],
  "chapters": [...],
  "missingParts": [...],
  "ebookFile": null
}
```

> Book Minified

```json
{
  "metadata": {...},
  "coverPath": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
  "tags": [
    "Favorite"
  ],
  "numTracks": 1,
  "numAudioFiles": 1,
  "numChapters": 1,
  "numMissingParts": 0,
  "numInvalidAudioFiles": 0,
  "duration": 33854.905,
  "size": 268824228,
  "ebookFormat": null
}
```

> Book Expanded

```json
{
  "libraryItemId": "li_8gch9ve09orgn4fdz8",
  "metadata": {...},
  "coverPath": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
  "tags": [
    "Favorite"
  ],
  "audioFiles": [...],
  "chapters": [...],
  "duration": 33854.905,
  "size": 268824228,
  "tracks": [...],
  "missingParts": [...],
  "ebookFile": null
}
```

Attribute | Type | Description
--------- | ---- | -----------
`libraryItemId` | String | The ID of the library item that contains the book.
`metadata` | [Book Metadata](#book-metadata) Object | The book's metadata.
`coverPath` | String or null | The absolute path on the server of the cover file. Will be `null` if there is no cover.
`tags` | Array of String | The book's tags.
`audioFiles` | Array of [Audio File](#audio-file) | The book's audio files.
`chapters` | Array of [Book Chapter](#book-chapter) | The book's chapters.
`missingParts` | Array of Integer | Any parts missing from the book by track index.
`ebookFile` | [EBook File](#ebook-file) Object or null | The book's ebook file. Will be `null` if this is an audiobook.

### Book Minified

#### Removed Attributes

* `libraryItemId`
* `audioFiles`
* `chapters`
* `missingParts`
* `ebookFile`

#### Modified Attributes

* `metadata` is [Book Metadata Minified](#book-metadata-minified)

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`numTracks` | Integer | The number of tracks the book's audio files have.
`numAudioFiles` | Integer | The number of audio files the book has.
`numChapters` | Integer | The number of chapters the book has.
`numMissingParts` | Integer | The total number of missing parts the book has.
`numInvalidAudioFiles` | Integer | The number of invalid audio files the book has.
`duration` | Float | The total length (in seconds) of the book.
`size` | Integer | The total size (in bytes) of the book.
`ebookFormat` | String or null | The format of ebook of the book. Will be `null` if the book is an audiobook.

### Book Expanded

#### Modified Attributes

* `metadata` is [Book Metadata Expanded](#book-metadata-expanded)

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`duration` | Float | The total length (in seconds) of the book.
`size` | Integer | The total size (in bytes) of the book.
`tracks` | Array of [Audio Track](#audio-track) | The book's audio tracks from the audio files.


## Book Metadata

> Book Metadata

```json
{
  "title": "Wizards First Rule",
  "subtitle": null,
  "authors": [...],
  "narrators": [
    "Sam Tsoutsouvas"
  ],
  "series": [...],
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
}
```

> Book Metadata Minified

```json
{
  "title": "Wizards First Rule",
  "titleIgnorePrefix": "Wizards First Rule",
  "subtitle": null,
  "authorName": "Terry Goodkind",
  "authorNameLF": "Goodkind, Terry",
  "narratorName": "Sam Tsoutsouvas",
  "seriesName": "Sword of Truth",
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
}
```

> Book Metadata Expanded

```json
{
  "title": "Wizards First Rule",
  "titleIgnorePrefix": "Wizards First Rule",
  "subtitle": null,
  "authors": [...],
  "narrators": [
    "Sam Tsoutsouvas"
  ],
  "series": [...],
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
}
```

Attribute | Type | Description
--------- | ---- | -----------
`title` | String or null | The title of the book. Will be `null` if unknown.
`subtitle` | String or null | The subtitle of the book. Will be `null` if there is no subtitle.
`authors` | Array of [Author Minified](#author-minified) | The authors of the book.
`narrators` | Array of String | The narrators of the audiobook.
`series` | Array of [Series Sequence](#series-sequence) | The series the book belongs to.
`genres` | Array of String | The genres of the book.
`publishedYear` | String or null | The year the book was published. Will be `null` if unknown.
`publishedDate` | String or null | The date the book was published. Will be `null` if unknown.
`publisher` | String or null | The publisher of the book. Will be `null` if unknown.
`description` | String or null | A description for the book. Will be `null` if empty.
`isbn` | String or null | The ISBN of the book. Will be `null` if unknown.
`asin` | String or null | The ASIN of the book. Will be `null` if unknown.
`language` | String or null | The language of the book. Will be `null` if unknown.
`explicit` | Boolean | Whether the book has been marked as explicit.

### Book Metadata Minified

#### Removed Attributes

* `authors`
* `narrators`
* `series`

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`titleIgnorePrefix` | String | The title of the book with any prefix moved to the end.
`authorName` | String | The name of the book's author(s).
`authorNameLF` | String | The name of the book's author(s) with last names first.
`narratorName` | String | The name of the audiobook's narrator(s).
`seriesName` | String | The name of the book's series.

### Book Metadata Expanded

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`titleIgnorePrefix` | String | The title of the book with any prefix moved to the end.
`authorName` | String | The name of the book's author(s).
`authorNameLF` | String | The name of the book's author(s) with last names first.
`narratorName` | String | The name of the audiobook's narrator(s).
`seriesName` | String | The name of the book's series.


## Book Chapter

> Book Chapter

```json
{
  "id": 0,
  "start": 0,
  "end": 6004.6675,
  "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01"
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | Integer | The ID of the book chapter.
`start` | Float | When in the book (in seconds) the chapter starts.
`end` | Float | When in the book (in seconds) the chapter ends.
`title` | String | The title of the chapter.


## Podcast

> Podcast

```json
{
  "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
  "metadata": {...},
  "coverPath": "/podcasts/Welcome to Night Vale/cover.jpg",
  "tags": [
    "Favorite"
  ],
  "episodes": [...],
  "autoDownloadEpisodes": true,
  "autoDownloadSchedule": "0 0 * * 1",
  "lastEpisodeCheck": 1667326662087,
  "maxEpisodesToKeep": 0,
  "maxNewEpisodesToDownload": 3
}
```

> Podcast Minified

```json
{
  "metadata": {...},
  "coverPath": "/podcasts/Welcome to Night Vale/cover.jpg",
  "tags": [
    "Favorite"
  ],
  "numEpisodes": 1,
  "autoDownloadEpisodes": true,
  "autoDownloadSchedule": "0 0 * * 1",
  "lastEpisodeCheck": 1667326662087,
  "maxEpisodesToKeep": 0,
  "maxNewEpisodesToDownload": 3,
  "size": 23706728
}
```

> Podcast Expanded

```json
{
  "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
  "metadata": {...},
  "coverPath": "/podcasts/Welcome to Night Vale/cover.jpg",
  "tags": [
    "Favorite"
  ],
  "episodes": [...],
  "autoDownloadEpisodes": true,
  "autoDownloadSchedule": "0 0 * * 1",
  "lastEpisodeCheck": 1667326662087,
  "maxEpisodesToKeep": 0,
  "maxNewEpisodesToDownload": 3,
  "size": 23706728
}
```

Attribute | Type | Description
--------- | ---- | -----------
`libraryItemId` | String | The ID of the library item that contains the podcast.
`metadata` | [Podcast Metadata](#podcast-metadata) Object | The metadata for the podcast.
`coverPath` | String or null | The absolute path on the server of the cover file. Will be `null` if there is no cover.
`tags` | Array of String | The podcast's tags.
`episodes` | Array of [Podcast Episode](#podcast-episode) | The downloaded episodes of the podcast.
`autoDownloadEpisodes` | Boolean | Whether the server will automatically download podcast episodes according to the schedule.
`autoDownloadSchedule` | String | The [cron expression](https://en.wikipedia.org/wiki/Cron#CRON_expression) for when to automatically download podcast episodes. Will not exist if `autoDownloadEpisodes` is `false`.
`lastEpisodeCheck` | Integer | The time (in ms since POSIX epoch) when the podcast was checked for new episodes.
`maxEpisodesToKeep` | Integer | The maximum number of podcast episodes to keep when automatically downloading new episodes. Episodes beyond this limit will be deleted. If `0`, all episodes will be kept.
`maxNewEpisodesToDownload` | Integer | The maximum number of podcast episodes to download when automatically downloading new episodes. If `0`, all episodes will be downloaded.

### Podcast Minified

#### Removed Attributes

* `libraryItemId`
* `episodes`

#### Modified Attributes

* `metadata` is [Podcast Metadata Minified](#podcast-metadata-minified)

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`numEpisodes` | Integer | The number of downloaded episodes for the podcast.
`size` | Integer | The total size (in bytes) of the podcast.

### Podcast Expanded

#### Modified Attributes

* `metadata` is [Podcast Metadata Expanded](#podcast-metadata-expanded)
* `episodes` is an Array of [Podcast Episodes Expanded](#podcast-episode-expanded)

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`size` | Integer | The total size (in bytes) of the podcast.


## Podcast Metadata

> Podcast Metadata

```json
{
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
```

> Podcast Metadata Minified

```json
{
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
}
```

> Podcast Metadata Expanded

```json
{
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
}
```

Attribute | Type | Description
--------- | ---- | -----------
`title` | String or null | The title of the podcast. Will be `null` if unknown.
`author` | String or null | The author of the podcast. Will be `null` if unknown.
`description` | String or null | The description for the podcast. Will be `null` if unknown.
`releaseDate` | String or null | The release date of the podcast. Will be `null` if unknown.
`genres` | Array of String | The podcast's genres.
`feedUrl` | String or null | A URL of an RSS feed for the podcast. Will be `null` if unknown.
`imageUrl` | String or null | A URL of a cover image for the podcast. Will be `null` if unknown.
`itunesPageUrl` | String or null | A URL of an iTunes page for the podcast. Will be `null` if unknown.
`itunesId` | Integer or null | The iTunes ID for the podcast. Will be `null` if unknown.
`itunesArtistId` | Integer or null | The iTunes Artist ID for the author of the podcast. Will be `null` if unknown.
`explicit` | Boolean | Whether the podcast has been marked as explicit.
`language` | String or null | The language of the podcast. Will be `null` if unknown.

### Podcast Metadata Minified

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`titleIgnorePrefix` | String | The title of the podcast with any prefix moved to the end.

### Podcast Metadata Expanded

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`titleIgnorePrefix` | String | The title of the podcast with any prefix moved to the end.


## Podcast Episode

> Podcast Episode

```json
{
  "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
  "id": "ep_lh6ko39pumnrma3dhv",
  "index": 1,
  "season": "",
  "episode": "",
  "episodeType": "full",
  "title": "1 - Pilot",
  "subtitle": "Pilot Episode. A new dog park opens in Night Vale. Carlos, a scientist, visits and discovers some interesting things. Seismic things. Plus, a helpful guide to surveillance helicopter-spotting. Weather: \"These and More Than These\" by Joseph Fink Music:...",
  "description": "\n        <p>Pilot Episode. A new dog park opens in Night Vale. Carlos, a scientist, visits and discovers some interesting things. Seismic things. Plus, a helpful guide to surveillance helicopter-spotting.</p>\n\n<p>Weather: \"These and More Than These\" by Joseph Fink</p>\n\n<p>Music: Disparition, <a target=\"_blank\">disparition.info</a></p>\n\n<p>Logo: Rob Wilson, <a target=\"_blank\">silastom.com</a></p>\n\n<p>Produced by Night Vale Presents. Written by Joseph Fink and Jeffrey Cranor. Narrated by Cecil Baldwin. More Info: <a target=\"_blank\">welcometonightvale.com</a>, and follow <a target=\"_blank\">@NightValeRadio</a> on Twitter or <a target=\"_blank\">Facebook</a>.</p>\n      ",
  "enclosure": {...},
  "pubDate": "Fri, 15 Jun 2012 12:00:00 -0000",
  "audioFile": {...},
  "publishedAt": 1339761600000,
  "addedAt": 1667326679503,
  "updatedAt": 1667326679503
}
```

> Podcast Episode Expanded

```json
{
  "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
  "id": "ep_lh6ko39pumnrma3dhv",
  "index": 1,
  "season": "",
  "episode": "",
  "episodeType": "full",
  "title": "1 - Pilot",
  "subtitle": "Pilot Episode. A new dog park opens in Night Vale. Carlos, a scientist, visits and discovers some interesting things. Seismic things. Plus, a helpful guide to surveillance helicopter-spotting. Weather: \"These and More Than These\" by Joseph Fink Music:...",
  "description": "\n        <p>Pilot Episode. A new dog park opens in Night Vale. Carlos, a scientist, visits and discovers some interesting things. Seismic things. Plus, a helpful guide to surveillance helicopter-spotting.</p>\n\n<p>Weather: \"These and More Than These\" by Joseph Fink</p>\n\n<p>Music: Disparition, <a target=\"_blank\">disparition.info</a></p>\n\n<p>Logo: Rob Wilson, <a target=\"_blank\">silastom.com</a></p>\n\n<p>Produced by Night Vale Presents. Written by Joseph Fink and Jeffrey Cranor. Narrated by Cecil Baldwin. More Info: <a target=\"_blank\">welcometonightvale.com</a>, and follow <a target=\"_blank\">@NightValeRadio</a> on Twitter or <a target=\"_blank\">Facebook</a>.</p>\n      ",
  "enclosure": {...},
  "pubDate": "Fri, 15 Jun 2012 12:00:00 -0000",
  "audioFile": {...},
  "audioTrack": {...},
  "publishedAt": 1339761600000,
  "addedAt": 1667326679503,
  "updatedAt": 1667326679503,
  "duration": 1454.18449,
  "size": 23653735
}
```

Attribute | Type | Description
--------- | ---- | -----------
`libraryItemId` | String | The ID of the library item that contains the podcast.
`id` | String | The ID of the podcast episode.
`index` | Integer | The index of the podcast episode.
`season` | String | The season of the podcast episode, if known.
`episode` | String | The episode of the season of the podcast, if known.
`episodeType` | String | The type of episode that the podcast episode is.
`title` | String | The title of the podcast episode.
`subtitle` | String | The subtitle of the podcast episode.
`description` | String | A HTML encoded, description of the podcast episode.
`enclosure` | [Podcast Episode Enclosure](#podcast-episode-enclosure) Object | Information about the podcast episode from when it was downloaded.
`pubDate` | String | When the podcast episode was published.
`audioFile` | [Audio File](#audio-file) Object | The audio file for the podcast episode.
`publishedAt` | Integer | The time (in ms since POSIX epoch) when the podcast episode was published.
`addedAt` | Integer | The time (in ms since POSIX epoch) when the podcast episode was added to the library.
`updatedAt` | Integer | The time (in ms since POSIX epoch) when the podcast episode was last updated.

### Podcast Episode Expanded

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`audioTrack` | [Audio Track](#audio-track) Object | The podcast episode's audio tracks from the audio file.
`duration` | Float | The total length (in seconds) of the podcast episode.
`size` | Integer | The total size (in bytes) of the podcast episode.


## Podcast Episode Enclosure

> Podcast Episode Enclosure

```json
{
  "url": "https://www.podtrac.com/pts/redirect.mp3/dovetail.prxu.org/_/126/1fadf1ad-aad8-449f-843b-6e8bb6949622/1_Pilot.mp3",
  "type": "audio/mpeg",
  "length": "20588611"
}
```

Attribute | Type | Description
--------- | ---- | -----------
`url` | String | The URL where the podcast episode's audio file was downloaded from.
`type` | String | The MIME type of the podcast episode's audio file.
`length` | String | The size (in bytes) that was reported when downloading the podcast episode's audio file.


## Podcast Episode Download

> Podcast Episode Download

```json
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
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the podcast episode download.
`episodeDisplayTitle` | String | The display title of the episode to be downloaded.
`url` | String | The URL from which to download the episode.
`libraryItemId` | String | The ID of the library item the episode belongs to.
`isDownloading` | Boolean | Whether the episode is actively being downloaded.
`isFinished` | Boolean | Whether the episode has finished downloading.
`failed` | Boolean | Whether the episode failed to download.
`startedAt` | Integer or null | The time (in ms since POSIX epoch) when the episode started downloading. Will be `null` if it has not started downloading yet.
`createdAt` | Integer | The time (in ms since POSIX epoch) when the podcast episode download request was created.
`finishedAt` | Integer or null | The time (in ms since POSIX epoch) when the episode finished downloading. Will be `null` if it has not finished.


## Podcast Feed

> Podcast Feed

```json
{
  "metadata": {...},
  "episodes": [...]
}
```

> Podcast Feed Minified

```json
{
  "metadata": {...},
  "numEpisodes": 280
}
```

Attribute | Type | Description
--------- | ---- | -----------
`metadata` | [Podcast Feed Metadata](#podcast-feed-metadata) Object | The podcast's metadata from the feed.
`episodes` | Array of [Podcast Feed Episode](#podcast-feed-episode) | The podcast's episodes from the feed.

### Podcast Feed Minified

#### Removed Attributes

* `episodes`

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`numEpisodes` | Integer | The number of episodes the podcast has.


## Podcast Feed Metadata

> Podcast Feed Metadata

```json
{
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
}
```

Attribute | Type | Description
--------- | ---- | -----------
`image` | String | A URL for the podcast's cover image.
`categories` | Array of String | The podcast's categories. Can be similar to genres.
`feedUrl` | String | A URL of an RSS feed for the podcast.
`description` | String | A HTML encoded description of the podcast.
`descriptionPlain` | String | A plain text description of the podcast.
`title` | String | The podcast's title.
`language` | String | The podcast's language.
`explicit` | String | Whether the podcast is explicit. Will probably be `"true"` or `"false"`.
`author` | String | The podcast's author.
`pubDate` | String | The podcast's publication date.
`link` | String | A URL the RSS feed provided for possible display to the user.


## Podcast Feed Episode

> Podcast Feed Episode

```json
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
  "enclosure": {...}
}
```

Attribute | Type | Description
--------- | ---- | -----------
`title` | String | The podcast episode's title.
`subtitle` | String | The podcast episode's subtitle.
`description` | String | A HTML encoded description of the podcast episode.
`descriptionPlain` | String | A plain text description of the podcast episode.
`pubDate` | String | The podcast episode's publication date.
`episodeType` | String | The type of episode that the podcast episode is.
`season` | String | The season of the podcast episode.
`episode` | String | The episode of the season of the podcast.
`author` | String | The author of the podcast episode.
`duration` | String | The duration of the podcast episode as reported by the RSS feed.
`explicit` | String | Whether the podcast episode is explicit.
`publishedAt` | Integer | The time (in ms since POSIX epoch) when the podcast episode was published.
`enclosure` | [Podcast Episode Enclosure](#podcast-episode-enclosure) Object | Download information for the podcast episode.


## Audio File

> Audio File

```json
{
  "index": 1,
  "ino": "649644248522215260",
  "metadata": {...},
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
  "metaTags": {...},
  "mimeType": "audio/mpeg"
}
```

Attribute | Type | Description
--------- | ---- | -----------
`index` | Integer | The index of the audio file.
`ino` | String | The inode of the audio file.
`metadata` | [File Metadata](#file-metadata) Object | The audio file's metadata.
`addedAt` | Integer | The time (in ms since POSIX epoch) when the audio file was added to the library.
`updatedAt` | Integer | The time (in ms since POSIX epoch) when the audio file last updated. (Read Only)
`trackNumFromMeta` | Integer or null | The track number of the audio file as pulled from the file's metadata. Will be `null` if unknown.
`discNumFromMeta` | Integer or null | The disc number of the audio file as pulled from the file's metadata. Will be `null` if unknown.
`trackNumFromFilename` | Integer or null | The track number of the audio file as determined from the file's name. Will be `null` if unknown.
`discNumFromFilename` | Integer or null | The track number of the audio file as determined from the file's name. Will be `null` if unknown.
`manuallyVerified` | Boolean | Whether the audio file has been manually verified by a user.
`invalid` | Boolean | Whether the audio file is missing from the server.
`exclude` | Boolean | Whether the audio file has been marked for exclusion.
`error` | String or null | Any error with the audio file. Will be `null` if there is none.
`format` | String | The format of the audio file.
`duration` | Float | The total length (in seconds) of the audio file.
`bitRate` | Integer | The bit rate (in bit/s) of the audio file.
`language` | String or null | The language of the audio file.
`codec` | String | The codec of the audio file.
`timeBase` | String | The time base of the audio file.
`channels` | Integer | The number of channels the audio file has.
`channelLayout` | String | The layout of the audio file's channels.
`chapters` | Array of [Book Chapter](#book-chapter) | If the audio file is part of an audiobook, the chapters the file contains.
`embeddedCoverArt` | String or null | The type of embedded cover art in the audio file. Will be `null` if none exists.
`metaTags` | [Audio Meta Tags](#audio-meta-tags) Object | The audio metadata tags from the audio file.
`mimeType` | String | The MIME type of the audio file.


## Audio Meta Tags

> Audio Meta Tags

```json
{
  "tagAlbum": "SOT Bk01",
  "tagArtist": "Terry Goodkind",
  "tagGenre": "Audiobook Fantasy",
  "tagTitle": "Wizards First Rule 01",
  "tagSeries": null,
  "tagSeriesPart": null,
  "tagTrack": "01/20",
  "tagDisc": null,
  "tagSubtitle": null,
  "tagAlbumArtist": "Terry Goodkind",
  "tagDate": null,
  "tagComposer": "Terry Goodkind",
  "tagPublisher": null,
  "tagComment": null,
  "tagDescription": null,
  "tagEncoder": null,
  "tagEncodedBy": null,
  "tagIsbn": null,
  "tagLanguage": null,
  "tagASIN": null,
  "tagOverdriveMediaMarker": null
}
```

[ID3](https://en.wikipedia.org/wiki/ID3) metadata tags pulled from the audio file on import.
Only non-null tags will be returned in requests.


## Audio Track

> Audio Track

```json
{
  "index": 1,
  "startOffset": 0,
  "duration": 33854.905,
  "title": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
  "contentUrl": "/s/item/li_8gch9ve09orgn4fdz8/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
  "mimeType": "audio/mpeg",
  "metadata": {...}
}
```

Attribute | Type | Description
--------- | ---- | -----------
`index` | Integer | The index of the audio track.
`startOffset` | Float | When in the audio file (in seconds) the track starts.
`duration` | Float | The length (in seconds) of the audio track.
`title` | String | The filename of the audio file the audio track belongs to.
`contentUrl` | String | The URL path of the audio file.
`mimeType` | String | The MIME type of the audio file.
`metadata` | [File Metadata](#file-metadata) Object or null | The metadata of the audio file.


## EBook File

> EBook File

```json
{
  "ino" : "9463162",
  "metadata": {...},
  "ebookFormat": "epub",
  "addedAt": 1650621073750,
  "updatedAt": 1650621110769
}
```

Attribute | Type | Description
--------- | ---- | -----------
`ino` | String | The inode of the ebook file.
`metadata` | [File Metadata](#file-metadata) Object | The metadata of the ebook file.
`ebookFormat` | String | The ebook format of the ebook file.
`addedAt` | Integer | The time (in ms since POSIX epoch) when the library file was added.
`updatedAt` | Integer | The time (in ms since POSIX epoch) when the library file was last updated.


## Library File

> Library File

```json
{
  "ino": "649644248522215260",
  "metadata": {...},
  "addedAt": 1650621052494,
  "updatedAt": 1650621052494,
  "fileType": "audio"
}
```

Attribute | Type | Description
--------- | ---- | -----------
`ino` | String | The inode of the library file.
`metadata` | [File Metadata](#file-metadata) Object | The metadata for the library file.
`addedAt` | Integer | The time (in ms since POSIX epoch) when the library file was added.
`updatedAt` | Integer | The time (in ms since POSIX epoch) when the library file was last updated.
`fileType` | String | The type of file that the library file is (audio, image, etc.).


## File Metadata

> File Metadata

```json
{
  "filename": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
  "ext": ".mp3",
  "path": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
  "relPath": "Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3",
  "size": 48037888,
  "mtimeMs": 1632223180278,
  "ctimeMs": 1645978261001,
  "birthtimeMs": 0
}
```

Attribute | Type | Description
--------- | ---- | -----------
`filename` | String | The filename of the file.
`ext` | String | The file extension of the file.
`path` | String | The absolute path on the server of the file.
`relPath` | String | The path of the file, relative to the book's or podcast's folder.
`size` | Integer | The size (in bytes) of the file.
`mtimeMs` | Integer | The time (in ms since POSIX epoch) when the file was last modified on disk.
`ctimeMs` | Integer | The time (in ms since POSIX epoch) when the file status was changed on disk.
`birthtimeMs` | Integer | The time (in ms since POSIX epoch) when the file was created on disk. Will be `0` if unknown.


## Author

> Author

```json
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
```

> Author Minified

```json
{
  "id": "aut_z3leimgybl7uf3y4ab",
  "name": "Terry Goodkind"
}
```

> Author Expanded

```json
{
  "id": "aut_z3leimgybl7uf3y4ab",
  "asin": null,
  "name": "Terry Goodkind",
  "description": null,
  "imagePath": null,
  "relImagePath": null,
  "addedAt": 1650621073750,
  "updatedAt": 1650621073750,
  "numBooks": 1
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the author.
`asin` | String or null | The ASIN of the author. Will be `null` if unknown.
`name` | String | The name of the author.
`description` | String or null | A description of the author. Will be `null` if there is none.
`imagePath` | String or null | The absolute path for the author image. Will be `null` if there is no image.
`relImagePath` | String or null | The path for the author image. Will be `null` if there is no image.
`addedAt` | Integer | The time (in ms since POSIX epoch) when the author was added.
`updatedAt` | Integer | The time (in ms since POSIX epoch) when the author was last updated.

### Author Minified

#### Removed Attributes

* `asin`
* `description`
* `imagePath`
* `relImagePath`
* `addedAt`
* `updatedAt`

### Author Expanded

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`numBooks` | Integer | The number of books associated with the author in the library.


## Series

> Series

```json
{
  "id": "ser_cabkj4jeu8be3rap4g",
  "name": "Sword of Truth",
  "description": null,
  "addedAt": 1650621073750,
  "updatedAt": 1650621073750
}
```

> Series Num Books

```json
{
  "id": "ser_cabkj4jeu8be3rap4g",
  "name": "Sword of Truth",
  "nameIgnorePrefix": "Sword of Truth",
  "libraryItemIds": [
    "li_8gch9ve09orgn4fdz8"
  ],
  "numBooks": 1
}
```

> Series Books

```json
{
  "id": "ser_cabkj4jeu8be3rap4g",
  "name": "Sword of Truth",
  "nameIgnorePrefix": "Sword of Truth",
  "nameIgnorePrefixSort": "Sword of Truth",
  "type": "series",
  "books": [...],
  "addedAt": 1650621073750,
  "totalDuration": 12000.946
}
```

> Series Sequence

```json
{
  "id": "ser_cabkj4jeu8be3rap4g",
  "name": "Sword of Truth",
  "sequence": "1"
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the series.
`name` | String | The name of the series.
`description` | String or null | A description for the series. Will be `null` if there is none.
`addedAt` | Integer | The time (in ms since POSIX epoch) when the series was added.
`updatedAt` | Integer | The time (in ms since POSIX epoch) when the series was last updated.

### Series Num Books

#### Removed Attributes

* `description`
* `addedAt`
* `updatedAt`

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`nameIgnorePrefix` | String | The name of the series with any prefix moved to the end.
`libraryItemIds` | Array of String | The IDs of the library items in the series.
`numBooks` | Integer | The number of books in the series.

### Series Books

#### Removed Attributes

* `description`
* `updatedAt`

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`nameIgnorePrefix` | String | The name of the series with any prefix moved to the end.
`nameIgnorePrefixSort` | String | The name of the series with any prefix removed.
`type` | String | Will always be `series`.
`books` | Array of [Library Item](#library-item) | The library items that contain the books in the series. A `sequence` attribute that denotes the position in the series the book is in, is tacked on.
`totalDuration` | Float | The combined duration (in seconds) of all books in the series.

### Series Sequence

#### Removed Attributes

* `description`
* `addedAt`
* `updatedAt`

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`sequence` | String or null | The position in the series the book is.


## Collection

> Collection

```json
{
  "id": "col_fpfstanv6gd7tq2qz7",
  "libraryId": "lib_c1u6t4p45c35rf0nzd",
  "userId": "root",
  "name": "Favorites",
  "description": null,
  "cover": null,
  "coverFullPath": null,
  "books": [...],
  "lastUpdate": 1650621110769,
  "createdAt": 1650621073750
}
```

> Collection Expanded

```json
{
  "id": "col_fpfstanv6gd7tq2qz7",
  "libraryId": "lib_c1u6t4p45c35rf0nzd",
  "userId": "root",
  "name": "Favorites",
  "description": null,
  "cover": null,
  "coverFullPath": null,
  "books": [...],
  "lastUpdate": 1650621110769,
  "createdAt": 1650621073750
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the collection.
`libraryId` | String | The ID of the library the collection belongs to.
`userId` | String | The ID of the user that the created the collection.
`name` | String | The name of the collection.
`description` | String or null | The collection's description. Will be `null` if there is none.
`cover` | String or null | The path to the collection's cover. Will be `null` if there is no cover.
`coverFullPath` | String or null | The full path to collection's cover. Will be `null` if there is no cover.
`books` | Array of [Library Item](#library-item) | The books that belong to the collection.
`lastUpdate` | Integer | The time (in ms since POSIX epoch) when the collection was last updated.
`createdAt` | Integer | The time (in ms since POSIX epoch) when the collection was created.

### Collection Expanded

#### Modified Attributes

* `books` is an Array of [Library Item Expanded](#library-item-expanded).


## Playlist

> Playlist

```json
{
  "id": "pl_qbwet64998s5ra6dcu",
  "libraryId": "lib_c1u6t4p45c35rf0nzd",
  "userId": "root",
  "name": "Favorites",
  "description": null,
  "coverPath": null,
  "items": [...],
  "lastUpdate": 1669623431313,
  "createdAt": 1669623431313
}
```

> Playlist Expanded

```json
{
  "id": "pl_qbwet64998s5ra6dcu",
  "libraryId": "lib_c1u6t4p45c35rf0nzd",
  "userId": "root",
  "name": "Favorites",
  "description": null,
  "coverPath": null,
  "items": [...],
  "lastUpdate": 1669623431313,
  "createdAt": 1669623431313
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the playlist.
`libraryId` | String | The ID of the library the playlist belongs to.
`userId` | String | The ID of the user the playlist belongs to.
`name` | String | The playlist's name.
`description` | String or null | The playlist's description.
`coverPath` | String or null | The path of the playlist's cover.
`items` | Array of [Playlist Item](#playlist-item) | The items in the playlist.
`lastUpdate` | Integer | The time (in ms since POSIX epoch) when the playlist was last updated.
`createdAt` | Integer | The time (in ms since POSIX epoch) when the playlist was created.

### Playlist Expanded

#### Modified Attributes

* `items` is an Array of [Playlist Item Expanded](#playlist-item-expanded).


## Playlist Item

> Playlist Item

```json
{
  "libraryItemId": "li_8gch9ve09orgn4fdz8",
  "episodeId": null
}
```

> Playlist Item Expanded

```json
{
  "libraryItemId": "li_8gch9ve09orgn4fdz8",
  "episodeId": null,
  "libraryItem": {...}
}
```

Attribute | Type | Description
--------- | ---- | -----------
`libraryItemId` | String | The ID of the library item the playlist item is for.
`episodeId` | String or null | The ID of the podcast episode the playlist item is for.

### Playlist Item Expanded

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`episode` | [Podcast Episode Expanded](#podcast-episode-expanded) Object | The podcast episode the playlist item is for. Will only exist if `episodeId` is not `null`.
`libraryItem` | [Library Item Expanded](#library-item-expanded) or [Library Item Minified](#library-item-minified) Object | The library item the playlist item is for. Will be [Library Item Minified](#library-item-minified) if `episodeId` is not `null`.


## Media Progress

> Media Progress

```json
{
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
}
```

> Media Progress with Media

```json
{
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
  "finishedAt": null,
  "media": {...},
  "episode": {...}
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the media progress. If the media progress is for a book, this will just be the `libraryItemId`. If for a podcast episode, it will be a hyphenated combination of the `libraryItemId` and `episodeId`.
`libraryItemId` | String | The ID of the library item the media progress is of.
`episodeId` | String or null | The ID of the podcast episode the media progress is of. Will be `null` if the progress is for a book.
`duration` | Float | The total duration (in seconds) of the media. Will be `0` if the media was marked as finished without the user listening to it.
`progress` | Float | The percentage completion progress of the media. Will be `1` if the media is finished.
`currentTime` | Float | The current time (in seconds) of the user's progress. If the media has been marked as finished, this will be the time the user was at beforehand.
`isFinished` | Boolean | Whether the media is finished.
`hideFromContinueListening` | Boolean | Whether the media will be hidden from the "Continue Listening" shelf.
`lastUpdate` | Integer | The time (in ms since POSIX epoch) when the media progress was last updated.
`startedAt` | Integer | The time (in ms since POSIX epoch) when the media progress was created.
`finishedAt` | Integer or null | The time (in ms since POSIX epoch) when the media was finished. Will be `null` if the media has is not finished.

### Media Progress with Media

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`media` | [Book Expanded](#book-expanded) or [Podcast Expanded](#podcast-expanded) Object | The media of the library item the media progress is for.
`episode` | [Podcast Episode](#podcast-episode) | The podcast episode the media progress is for. Will only exist if the media progress is for a podcast episode.


## Playback Session

> Playback Session

```json
{
  "id": "play_c786zm3qtjz6bd5q3n",
  "userId": "root",
  "libraryId": "lib_p9wkw2i85qy9oltijt",
  "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
  "episodeId": "ep_lh6ko39pumnrma3dhv",
  "mediaType": "podcast",
  "mediaMetadata": {...},
  "chapters": [],
  "displayTitle": "1 - Pilot",
  "displayAuthor": "Night Vale Presents",
  "coverPath": "/metadata/items/li_bufnnmp4y5o2gbbxfm/cover.jpg",
  "duration": 1454.18449,
  "playMethod": 0,
  "mediaPlayer": "unknown",
  "deviceInfo": {...},
  "date": "2022-11-11",
  "dayOfWeek": "Friday",
  "timeListening": 0,
  "startTime": 0,
  "currentTime": 0,
  "startedAt": 1668206493239,
  "updatedAt": 1668206493239
}
```

<!-- PlaybackSession.toJSONForClient() -->
> Playback Session Expanded

```json
{
  "id": "play_c786zm3qtjz6bd5q3n",
  "userId": "root",
  "libraryId": "lib_p9wkw2i85qy9oltijt",
  "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
  "episodeId": "ep_lh6ko39pumnrma3dhv",
  "mediaType": "podcast",
  "mediaMetadata": {...},
  "chapters": [],
  "displayTitle": "1 - Pilot",
  "displayAuthor": "Night Vale Presents",
  "coverPath": "/metadata/items/li_bufnnmp4y5o2gbbxfm/cover.jpg",
  "duration": 1454.18449,
  "playMethod": 0,
  "mediaPlayer": "unknown",
  "deviceInfo": {...},
  "date": "2022-11-11",
  "dayOfWeek": "Friday",
  "timeListening": 0,
  "startTime": 0,
  "currentTime": 0,
  "startedAt": 1668206493239,
  "updatedAt": 1668206493239,
  "audioTracks": [...],
  "videoTrack": null,
  "libraryItem": {...}
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the playback session.
`userId` | String | The ID of the user the playback session is for.
`libraryId` | String | The ID of the library that contains the library item.
`libraryItemId` | String | The ID of the library item.
`episodeId` | String or null | The ID of the podcast episode. Will be `null` if this playback session was started without an episode ID.
`mediaType` | String | The media type of the library item. Will be `book` or `podcast`.
`mediaMetadata` | [Book Metadata](#book-metadata) or [Podcast Metadata](#podcast-metadata) Object | The metadata of the library item's media.
`chapters` | Array of [Book Chapter](#book-chapter) | If the library item is a book, the chapters it contains.
`displayTitle` | String | The title of the playing item to show to the user.
`displayAuthor` | String | The author of the playing item to show to the user.
`coverPath` | String | The cover path of the library item's media.
`duration` | Float | The total duration (in seconds) of the playing item.
`playMethod` | [Play Method](#play-method) Enumerated Integer | What play method the playback session is using. See below for values.
`mediaPlayer` | String | The given media player when the playback session was requested.
`deviceInfo` | [Device Info](#device-info) Object | The given device info when the playback session was requested.
`day` | String | The day (in the format YYYY-MM-DD) the playback session was started.
`dayOfWeek` | String | The day of the week the playback session was started.
`timeListening` | Float | The amount of time (in seconds) the user has spent listening using this playback session.
`startTime` | Float | The time (in seconds) where the playback session started.
`currentTime` | Float | The current time (in seconds) of the playback position.
`startedAt` | Integer | The time (in ms since POSIX epoch) when the playback session was started.
`updatedAt` | Integer | The time (in ms since POSIX epoch) when the playback session was last updated.

#### Play Method

Value | Meaning
----- | -------
`0` | Direct Play
`1` | Direct Stream
`2` | Transcode
`3` | Local

### Playback Session Expanded

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`audioTracks` | Array of [Audio Tracks](#audio-track) | The audio tracks that are being played with the playback session.
`videoTrack` | Video Track Object or null | The video track that is being played with the playback session. Will be `null` if the playback session is for a book or podcast.
`libraryItem` | [Library Item Expanded](#library-item-expanded) Object | The library item of the playback session.


## Device Info

> Device Info

```json
{
  "ipAddress": "192.168.1.118",
  "browserName": "Firefox",
  "browserVersion": "106.0",
  "osName": "Linux",
  "osVersion": "x86_64",
  "deviceType": null,
  "manufacturer": null,
  "model": null,
  "sdkVersion": null,
  "serverVersion": "2.2.2"
}
```

Any attributes with a `null` value will be filtered out in responses.

Attribute | Type | Description
--------- | ---- | -----------
`ipAddress` | String or null | The IP address that the request came from.
`browserName` | String or null | The browser name, taken from the user agent.
`browserVersion` | String or null | The browser version, taken from the user agent.
`osName` | String or null | The name of OS, taken from the user agent.
`osVersion` | String or null | The version of the OS, taken from the user agent.
`deviceType` | String or null | The device type, taken from the user agent.
`manufacturer` | String or null | The client device's manufacturer, as provided in the request.
`model` | String or null | The client device's model, as provided in the request.
`sdkVersion` | Integer or null | For an Android device, the Android SDK version of the client, as provided in the request.
`serverVersion` | String or null | The version of the server at the time of the request.


## User

<!-- This is actually the User.toJSONForBrowser() method as User.toJSON() is not accessible to the API. -->
> User

```json
{
  "id": "root",
  "username": "root",
  "type": "root",
  "token": "exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY",
  "mediaProgress": [...],
  "seriesHideFromContinueListening": [],
  "bookmarks": [...],
  "isActive": true,
  "isLocked": false,
  "lastSeen": 1668296147437,
  "createdAt": 1666543632566,
  "settings": {...},
  "permissions": {...},
  "librariesAccessible": [...],
  "itemTagsAccessible": [...]
}
```

<!-- ApiRouter.userJsonWithItemProgressDetails() -->
> User with Progress Details

```json
{
  "id": "root",
  "username": "root",
  "type": "root",
  "token": "exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY",
  "mediaProgress": [...],
  "seriesHideFromContinueListening": [],
  "bookmarks": [...],
  "isActive": true,
  "isLocked": false,
  "lastSeen": 1668296147437,
  "createdAt": 1666543632566,
  "settings": {...},
  "permissions": {...},
  "librariesAccessible": [...],
  "itemTagsAccessible": [...]
}
```

<!-- User.toJSONForPublic() -->
> User with Session and Most Recent Progress

```json
{
  "id": "root",
  "username": "root",
  "type": "root",
  "session": null,
  "mostRecent": {...},
  "lastSeen": 1668296147437,
  "createdAt": 1666543632566
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the user. Only the root user has the `root` ID.
`username` | String | The username of the user.
`type` | String | The type of the user. Will be `root`, `guest`, `user`, or `admin`. There will be only one root user which is created when the server first starts.
`token` | String | The authentication token of the user.
`mediaProgress` | Array of [Media Progress](#media-progress) | The user's media progress.
`seriesHideFromContinueListening` | Array of String | The IDs of series to hide from the user's "Continue Series" shelf.
`bookmarks` | Array of [Audio Bookmark](#audio-bookmark) | The user's bookmarks.
`isActive` | Boolean | Whether the user's account is active.
`isLocked` | Boolean | Whether the user is locked.
`lastSeen` | Integer or null | The time (in ms since POSIX epoch) when the user was last seen by the server. Will be `null` if the user has never logged in.
`createdAt` | Integer | The time (in ms since POSIX epoch) when the user was created.
`settings` | [User Settings](#user-settings) Object | The user's settings.
`permissions` | [User Permissions](#user-permissions) Object | The user's permissions.
`librariesAccessible` | Array of String | The IDs of libraries accessible to the user. An empty array means all libraries are accessible.
`itemTagsAccessible` | Array of String | The tags accessible to the user. An empty array means all tags are accessible.

### User with Progress Details

#### Modified Attributes

* `mediaProgress` is an Array of [Media Progress with Media](#media-progress-with-media)

### User with Session and Most Recent Progress

#### Removed Attributes

* `token`
* `mediaProgress`
* `seriesHideFromContinueListening`
* `bookmarks`
* `isActive`
* `isLocked`
* `settings`
* `permissions`
* `librariesAccessible`
* `itemTagsAccessible`

#### Added Attributes

Attribute | Type | Description
--------- | ---- | -----------
`session` | [Playback Session Expanded](#playback-session-expanded) Object or null | The user's currently playing session. Will be `null` if the user is not currently playing anything.
`mostRecent` | [Media Progress with Media](#media-progress-with-media) Object or null | The user's most recent media progress. Will be `null` if the user has no media progress.


## User Settings

> User Settings

```json
{
  "mobileOrderBy": "recent",
  "mobileOrderDesc": true,
  "mobileFilterBy": "all",
  "orderBy": "media.metadata.title",
  "orderDesc": false,
  "filterBy": "all",
  "playbackRate": 1,
  "bookshelfCoverSize": 120,
  "collapseSeries": false
}
```

Attribute | Type | Description
--------- | ---- | -----------
`mobileOrderBy` | String | What to order library items by on mobile.
`mobileOrderDesc` | Boolean | Whether to reverse the sort order on mobile.
`mobileFilterBy` | String | What to filter library items by on mobile.
`orderBy` | String | What to order library items by.
`orderDesc` | Boolean | Whether to reverse the sort order.
`filterBy` | String | What to filter library items by.
`playbackRate` | Float | What speed to play items.
`bookshelfCoverSize` | Integer | What size to display covers at.
`collapseSeries` | Boolean | Whether to collapse series when viewing library items.


## User Permissions

> User Permissions

```json
{
  "download": true,
  "update": true,
  "delete": true,
  "upload": true,
  "accessAllLibraries": true,
  "accessAllTags": true,
  "accessExplicitContent": true
}
```

Attribute | Type | Description
--------- | ---- | -----------
`download` | Boolean | Whether the user can download items to the server.
`update` | Boolean | Whether the user can update library items.
`delete` | Boolean | Whether the user can delete library items.
`upload` | Boolean | Whether the user can upload items to the server.
`accessAllLibraries` | Boolean | Whether the user can access all libraries.
`accessAllTags` | Boolean | Whether the user can access all tags.
`accessExplicitContent` | Boolean | Whether the user can access explicit content.


## Audio Bookmark

> Audio Bookmark

```json
{
  "libraryItemId": "li_8gch9ve09orgn4fdz8",
  "title": "the good part",
  "time": 16,
  "createdAt": 1668120083771
}
```

Attribute | Type | Description
--------- | ---- | -----------
`libraryItemId` | String | The ID of the library item the bookmark is for.
`title` | String | The title of the bookmark.
`time` | Integer | The time (in seconds) the bookmark is at in the book.
`createdAt` | Integer | The time (in ms since POSIX epoch) when the bookmark was created.


## Backup

> Backup

```json
{
  "id": "2022-11-14T0130",
  "backupMetadataCovers": true,
  "backupDirPath": "/metadata/backups",
  "datePretty": "Mon, Nov 14 2022 01:30",
  "fullPath": "/metadata/backups/2022-11-14T0130.audiobookshelf",
  "path": "backups/2022-11-14T0130.audiobookshelf",
  "filename": "2022-11-14T0130.audiobookshelf",
  "fileSize": 7776983,
  "createdAt": 1668411000329,
  "serverVersion": "2.2.4"
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the backup. Will be the date and time when the backup was created.
`backupMetadataCovers` | Boolean | Whether the backup includes library item covers and author images located in metadata.
`backupDirPath` | String | The backup directory path.
`datePretty` | String | The date and time when the backup was created in a human-readable format.
`fullPath` | String | The full path of the backup on the server.
`path` | String | The path of the backup relative to the metadata directory.
`filename` | String | The filename of the backup.
`fileSize` | Integer | The size (in bytes) of the backup file.
`createdAt` | Integer | The time (in ms since POSIX epoch) when the backup was created.
`serverVersion` | String | The version of the server when the backup was created.


## Notification Settings

> Notification Settings

```json
{
  "id": "notification-settings",
  "appriseType": "api",
  "appriseApiUrl": "https://apprise.example.com/notify",
  "notifications": [...],
  "maxFailedAttempts": 5,
  "maxNotificationQueue": 20,
  "notificationDelay": 1000
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the notification settings.
`appriseType` | String | The type of Apprise that will be used. At the moment, only `api` is available.
`appriseApiUrl` | String or null | The full URL where the Apprise API to use is located.
`notifications` | Array of [Notification](#notification) | The set notifications.
`maxFailedAttempts` | Integer | The maximum number of times a notification fails before being disabled.
`maxNotificationQueue` | Integer | The maximum number of notifications in the notification queue before events are ignored.
`notificationDelay` | Integer | The time (in ms) between notification pushes.


## Notification

> Notification

```json
{
  "id": "noti_nod281qwkj5ow7h7fi",
  "libraryId": null,
  "eventName": "onPodcastEpisodeDownloaded",
  "urls": [
    "apprises://apprise.example.com/email"
  ],
  "titleTemplate": "New {{podcastTitle}} Episode!",
  "bodyTemplate": "{{episodeTitle}} has been added to {{libraryName}} library.",
  "enabled": true,
  "type": "info",
  "lastFiredAt": 1668776410792,
  "lastAttemptFailed": false,
  "numConsecutiveFailedAttempts": 0,
  "numTimesFired": 5,
  "createdAt": 1666545142424
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the notification.
`libraryId` | String or null | The ID of the library the notification is associated with.
`eventName` | String | The name of the event the notification will fire on.
`urls` | Array of String | The Apprise URLs to use for the notification.
`titleTemplate` | String | The template for the notification title.
`bodyTemplate` | String | The template for the notification body.
`enabled` | Boolean | Whether the notification is enabled.
`type` | String | The notification's type.
`lastFiredAt` | String or null | The time (in ms since POSIX epoch) when the notification was last fired. Will be `null` if the notification has not fired.
`lastAttemptFailed` | Boolean | Whether the last notification attempt failed.
`numConsecutiveFailedAttempts` | Integer | The number of consecutive times the notification has failed.
`numTimesFired` | Integer | The number of times the notification has fired.
`createdAt` | Integer | The time (in ms since POSIX epoch) when the notification was created.


## Notification Event

> Notification Event

```json
{
  "name": "onPodcastEpisodeDownloaded",
  "requiresLibrary": true,
  "libraryMediaType": "podcast",
  "description": "Triggered when a podcast episode is auto-downloaded",
  "variables": [
    "libraryItemId",
    "libraryId",
    "podcastTitle",
    "episodeTitle",
    "libraryName",
    "episodeId"
  ],
  "defaults": {
    "title": "New {{podcastTitle}} Episode!",
    "body": "{{episodeTitle}} has been added to {{libraryName}} library."
  },
  "testData": {
    "libraryItemId": "li_notification_test",
    "libraryId": "lib_test",
    "libraryName": "Podcasts",
    "podcastTitle": "Abs Test Podcast",
    "episodeId": "ep_notification_test",
    "episodeTitle": "Successful Test"
  }
}
```

The notification events that are available are [predefined here](https://github.com/advplyr/audiobookshelf/blob/master/server/utils/notifications.js).

Attribute | Type | Description
--------- | ---- | -----------
`name` | String | The name of the notification event.
`requiresLibrary` | Boolean | Whether the notification event depends on a library existing.
`libraryMediaType` | String | The type of media of the library the notification depends on existing. Will not exist if `requiresLibrary` is `false`.
`description` | String | The description of the notification event.
`variables` | Array of String | The variables of the notification event that can be used in the notification templates.
`defaults.title` | String | The default title template for notifications using the notification event.
`defaults.body` | String | The default body template for notifications using the notification event.
`testData` | Object | The keys of the `testData` object will match the list of `variables`. The values will be the data used when sending a test notification.


## Server Settings

> Server Settings

```json
{
  "id": "server-settings",
  "scannerFindCovers": false,
  "scannerCoverProvider": "google",
  "scannerParseSubtitle": false,
  "scannerPreferAudioMetadata": false,
  "scannerPreferOpfMetadata": false,
  "scannerPreferMatchedMetadata": false,
  "scannerDisableWatcher": true,
  "scannerPreferOverdriveMediaMarker": false,
  "scannerUseSingleThreadedProber": true,
  "scannerMaxThreads": 0,
  "scannerUseTone": false,
  "storeCoverWithItem": false,
  "storeMetadataWithItem": false,
  "rateLimitLoginRequests": 10,
  "rateLimitLoginWindow": 600000,
  "backupSchedule": "30 1 * * *",
  "backupsToKeep": 2,
  "maxBackupSize": 1,
  "backupMetadataCovers": true,
  "loggerDailyLogsToKeep": 7,
  "loggerScannerLogsToKeep": 2,
  "homeBookshelfView": 1,
  "bookshelfView": 1,
  "sortingIgnorePrefix": false,
  "sortingPrefixes": [
    "the",
    "a"
  ],
  "chromecastEnabled": false,
  "enableEReader": false,
  "dateFormat": "MM/dd/yyyy",
  "language": "en-us",
  "logLevel": 2,
  "version": "2.2.5"
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the server settings.
`scannerFindCovers` | Boolean | Whether the scanner will attempt to find a cover if your audiobook does not have an embedded cover or a cover image inside the folder. Note: This will extend scan time.
`scannerCoverProvider` | String | If `scannerFindCovers` is `true`, which metadata provider to use. See [Metadata Providers](#metadata-providers) for options.
`scannerParseSubtitle` | Boolean | Whether to extract subtitles from audiobook folder names. Subtitles must be separated by ` - `, i.e. `/audiobooks/Book Title - A Subtitle Here/` has the subtitle `A Subtitle Here`.
`scannerPreferAudioMetadata` | Boolean | Whether to use audio file ID3 meta tags instead of folder names for book details.
`scannerPreferOpfMetadata` | Boolean | Whether to use OPF file metadata instead of folder names for book details.
`scannerPreferMatchedMetadata` | Boolean | Whether matched data will override item details when using Quick Match. By default, Quick Match will only fill in missing details.
`scannerDisableWatcher` | Boolean | Whether to disable the automatic adding/updating of items when file changes are detected. *Requires server restart* for changes to take effect.
`scannerPreferOverdriveMediaMarker` | Boolean | Whether to use the custom metadata in MP3 files from Overdrive for chapter timings automatically.
`storeCoverWithItem` | Boolean | Whether to store covers in the library item's folder. By default, covers are stored in `/metadata/items`. Only one file named `cover` will be kept.
`storeMetadataWithItem` | Boolean | Whether to store metadata files in the library item's folder. By default, metadata files are stored in `/metadata/items`. Uses the `.abs` file extension.
`rateLimitLoginRequests` | Integer | The maximum number of login requests per `rateLimitLoginWindow`.
`rateLimitLoginWindow` | Integer | The length (in ms) of each login rate limit window.
`backupSchedule` | String | The [cron expression](https://en.wikipedia.org/wiki/Cron#CRON_expression) for when to do automatic backups.
`backupsToKeep` | Integer | The number of backups to keep.
`maxBackupSize` | Integer | The maximum backup size (in GB) before they fail, a safeguard against misconfiguration.
`backupMetadataCovers` | Boolean | Whether backups should include library item covers and author images located in metadata.
`loggerDailyLogsToKeep` | Integer | The number of daily logs to keep.
`loggerScannerLogsToKeep` | Integer | The number of scanner logs to keep.
`homeBookshelfView` | Binary | Whether the home page should use a skeuomorphic design with wooden shelves.
`bookshelfView` | Binary | Whether other bookshelf pages should use a skeuomorphic design with wooden shelves.
`sortingIgnorePrefix` | Boolean | Whether to ignore prefixes when sorting. For example, for the prefix `the`, the book title `The Book Title` would sort as `Book Title, The`.
`sortingPrefixes` | Array of String | If `sortingIgnorePrefix` is `true`, what prefixes to ignore.
`chromecastEnabled` | Boolean | Whether to enable streaming to Chromecast devices.
`enableEReader` | Boolean | Whether to enable experimental e-reader support.
`dateFormat` | String | What date format to use. Options are `MM/dd/yyyy`, `dd/MM/yyyy`, or `yyyy-MM-dd`.
`language` | String | The default server language.
`logLevel` | Integer | What log level the server should use when logging. `1` for debug, `2` for info, or `3` for warnings.
`version` | String | The server's version.


## RSS Feed

> RSS Feed

```json
{
  "id": "li_bufnnmp4y5o2gbbxfm",
  "slug": "li_bufnnmp4y5o2gbbxfm",
  "userId": "root",
  "entityType": "item",
  "entityId": "li_bufnnmp4y5o2gbbxfm",
  "coverPath": "/metadata/items/li_bufnnmp4y5o2gbbxfm/cover.jpg",
  "serverAddress": "https://abs.example.com",
  "feedUrl": "https://abs.example.com/feed/li_bufnnmp4y5o2gbbxfm",
  "meta": {...},
  "episodes": [...],
  "createdAt": 1669031843179,
  "updatedAt": 1669031843179
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the RSS feed.
`slug` | String | The slug (the last part of the URL) for the RSS feed.
`userId` | String | The ID of the user that created the RSS feed.
`entityType` | String | The type of entity the RSS feed is for.
`entityId` | String | The ID of the entity the RSS feed is for.
`coverPath` | String | The path of the cover to use for the RSS feed.
`serverAddress` | String | The server's address.
`feedUrl` | String | The full URL of the RSS feed.
`meta` | [RSS Feed Metadata](#rss-feed-metadata) Object | The RSS feed's metadata.
`episodes` | Array of [RSS Feed Episode](#rss-feed-episode) | The RSS feed's episodes.
`createdAt` | Integer | The time (in ms since POSIX epoch) when the RSS feed was created.
`updatedAt` | Integer | The time (in ms since POSIX epoch) when the RSS feed was last updated.


## RSS Feed Metadata

> Feed Metadata

```json
{
  "title": "Welcome to Night Vale",
  "description": "\n      Twice-monthly community updates for the small desert town of Night Vale, where every conspiracy theory is true. Turn on your radio and hide. Never listened before? It's an ongoing radio show. Start with the current episode, and you'll catch on in no time. Or, go right to Episode 1 if you wanna binge-listen.\n    ",
  "author": "Night Vale Presents",
  "imageUrl": "https://abs.example.com/feed/li_bufnnmp4y5o2gbbxfm/cover",
  "feedUrl": "https://abs.example.com/feed/li_bufnnmp4y5o2gbbxfm",
  "link": "https://abs.example.com/item/li_bufnnmp4y5o2gbbxfm",
  "explicit": false
}
```

Attribute | Type | Description
--------- | ---- | -----------
`title` | String | The title of the entity the RSS feed is for.
`description` | String | The description of the entity the RSS feed is for.
`author` | String | The author of the entity the RSS feed is for. 
`imageUrl` | String | The URL of the RSS feed's image.
`feedUrl` | String | The URL of the RSS feed.
`link` | String | The URL of the entity the RSS feed is for.
`explicit` | Boolean | Whether the RSS feed's contents are explicit.


## RSS Feed Episode

> Feed Episode

```json
{
  "id": "ep_lh6ko39pumnrma3dhv",
  "title": "1 - Pilot",
  "description": "<div><br>Pilot Episode. A new dog park opens in Night Vale. Carlos, a scientist, visits and discovers some interesting things. Seismic things. Plus, a helpful guide to surveillance helicopter-spotting.<br><br></div><div><br>Weather: \"These and More Than These\" by Joseph Fink<br><br></div><div><br>Music: Disparition, disparition.info<br><br></div><div><br>Logo: Rob Wilson, silastom.com<br><br></div><div><br>Produced by Night Vale Presents. Written by Joseph Fink and Jeffrey Cranor. Narrated by Cecil Baldwin. More Info: welcometonightvale.com, and follow @NightValeRadio on Twitter or Facebook.<br><br></div>",
  "enclosure": {
    "url": "https://abs.example.com/feed/li_bufnnmp4y5o2gbbxfm/item/ep_lh6ko39pumnrma3dhv/1 - Pilot.mp3",
    "type": "audio/mpeg",
    "size": 23653735
  },
  "pubDate": "Fri, 15 Jun 2012 12:00:00 -0000",
  "link": "https://abs.example.com/item/li_bufnnmp4y5o2gbbxfm",
  "author": "Night Vale Presents",
  "explicit": false,
  "duration": 1454.18449,
  "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
  "episodeId": "ep_lh6ko39pumnrma3dhv",
  "trackIndex": 0,
  "fullPath": "/podcasts/Welcome to Night Vale/1 - Pilot.mp3"
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the RSS feed episode.
`title` | String | The title of the RSS feed episode.
`description` | String | An HTML encoded description of the RSS feed episode.
`enclosure` | Similar to [Podcast Episode Enclosure](#podcast-episode-enclosure) | Download information for the RSS feed episode.
`pubDate` | String | The RSS feed episode's publication date.
`link` | String | A URL to display to the RSS feed user.
`explicit` | Boolean | Whether the RSS feed episode is explicit.
`duration` | Float | The duration (in seconds) of the RSS feed episode.
`libraryItemId` | String | The ID of the library item the RSS feed is for.
`episodeId` | String or null | The ID of the podcast episode the RSS feed episode is for. Will be `null` if the RSS feed is for a book.
`trackIndex` | Integer | The RSS feed episode's track index.
`fullPath` | String | The path on the server of the audio file the RSS feed episode is for.
