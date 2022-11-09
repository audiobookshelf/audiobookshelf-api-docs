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
`provider` | String | Perferred metadata provider for the library. See [Library Metadata Providers](#library-metadata-providers) for a list of possible providers.
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
`coverAspectRatio` | Integer | Whether or not the library should use square book covers. Must be `0` (for false) or `1` (for true).
`disableWatcher` | Boolean | Whether or not to disable the folder watcher for the library.
`skipMatchingMediaWithAsin` | Boolean | Whether or not to skip matching books that already have an ASIN.
`skipMatchingMediaWithIsbn` | Boolean | Whether or not to skip matching books that already have an ISBN.
`autoScanCronExpression` | String or null | The [cron expression](https://en.wikipedia.org/wiki/Cron#CRON_expression) for when to automatically scan the library folders. If `null`, automatic scanning will be disabled.


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
`libraryId` | String | The ID of the library the library item belongs to.
`folderId` | String | The ID of the folder the library item is in.
`path` | String | The path of the library item on the server.
`relPath` | String | The path, relative to the library folder, of the library item.
`isFile` | Boolean | Whether or not the library item is a single file in the root of the library folder.
`mtimeMs` | Integer | The time (in ms since POSIX epoch) when the library item was last modified on disk.
`ctimeMs` | Integer | The time (in ms since POSIX epoch) when the library item status was changed on disk.
`birthtimeMs` | Integer | The time (in ms since POSIX epoch) when the library item was created on disk. Will be `0` if unknown.
`addedAt` | Integer | The time (in ms since POSIX epoch) when the library item was added to the library.
`updatedAt` | Integer | The time (in ms since POSIX epoch) when the library item was last updated. (Read Only)
`lastScan` | Integer or null | The time (in ms since POSIX epoch) when the library item was last scanned. Will be `null` if it has not been scanned.
`scanVersion` | String or null | The version of the scanner when last scanned. Will be `null` if it has not been scanned.
`isMissing` | Boolean | Whether or not the library item was scanned and no longer exists.
`isInvalid` | Boolean | Whether or not the library item was scanned and no longer has media files.
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
`explicit` | Boolean | Whether or not the book has been marked as explicit.

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
`autoDownloadEpisodes` | Boolean | Whether or not the server will automatically download podcast episodes according to the schedule.
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
`explicit` | Boolean | Whether or not the podcast has been marked as explicit.
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
`length` | The size (in bytes) that was reported when downloading the podcast episode's audio file.


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
`manuallyVerified` | Boolean | Whether or not the audio file has been manually verified by a user.
`invalid` | Boolean | Whether or not the audio file is missing from the server.
`exclude` | Boolean | Whether or not the audio file has been marked for exclusion.
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
`contentUrl` | String | The URL on the serve of the audio file.
`mimeType` | String | The MIME type of the audio file.
`metadata` | [File Metadta](#file-metadata) Object or null | The metadata of the audio file.


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
`squence` | String or null | The position in the series the book is.


## Collection

> Collection

```json
{
  "id": "usr_fpfstanv6gd7tq2qz7",
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
  "id": "usr_fpfstanv6gd7tq2qz7",
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
