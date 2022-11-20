# Search

## Search for Covers

```shell
curl "https://abs.example.com/api/search/covers?title=Wizards%20First%20Rule&author=Terry%20Goodkind&provider=openlibrary" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
[
  "https://covers.openlibrary.org/b/id/1005963-L.jpg",
  "https://covers.openlibrary.org/b/id/791977-L.jpg",
  "https://covers.openlibrary.org/b/id/766531-L.jpg",
  "https://covers.openlibrary.org/b/id/910943-L.jpg",
  "https://covers.openlibrary.org/b/id/8782857-L.jpg",
  "https://covers.openlibrary.org/b/id/8788596-L.jpg",
  "https://covers.openlibrary.org/b/id/8783892-L.jpg",
  "https://covers.openlibrary.org/b/id/8993240-L.jpg",
  "https://covers.openlibrary.org/b/id/10505009-L.jpg",
  "https://covers.openlibrary.org/b/id/1005881-L.jpg",
  "https://covers.openlibrary.org/b/id/8776837-L.jpg",
  "https://covers.openlibrary.org/b/id/10778344-L.jpg",
  "https://covers.openlibrary.org/b/id/11239659-L.jpg",
  "https://covers.openlibrary.org/b/id/12224404-L.jpg",
  "https://covers.openlibrary.org/b/OLID/OL9034948M-L.jpg",
  "https://covers.openlibrary.org/b/id/8785389-L.jpg"
]
```

This endpoint searches a metadata provider for covers. An array of URLs for cover images is returned.

### HTTP Request

`GET http://abs.example.com/api/search/covers`

### Query Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`podcast` | Binary | `0` | Whether to search for podcast covers. Only the `title` parameter is needed for podcasts. `0` for false, `1` for true.
`title` | String | **Required** | The media title to search for.
`author` | String or null | `null` | If searching for a book cover, the author to search for.
`provider` | String | **Required for Books** | If searching for a book cover, the metadata provider to use. See [Library Metadata Providers](#library-metadata-providers) for options.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | Array of String


## Search for Books

> Metadata Provider: Google

```shell
curl "https://abs.example.com/api/search/books?title=Wizard's%20First%20Rule&author=Terry%20Goodkind&provider=google" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": "WzO7jSs6XTYC",
    "title": "Wizard's First Rule",
    "subtitle": null,
    "author": "Terry Goodkind",
    "publisher": "RosettaBooks",
    "publishedYear": null,
    "description": "The “wonderfully creative, seamless, and stirring” debut novel in the Sword of Truth epic fantasy series by the #1 New York Times bestselling author (Kirkus). Terry Goodkind’s debut novel, Wizard’s First Rule, was a phenomenon from the moment it was first published by Tor Books in 1994. In it, readers are drawn into the magical New World, where ordinary Westland forest guide Richard Cypher accepts his extraordinary destiny. As a Seeker of Truth, Richard is the only one who can stop the tyrannical wizard Darken Rahl from seizing the all-powerful Boxes of Orden. When the beautiful and mysterious Kahlan Amnell appears in Richard's forest seeking help, his humble world is turned on its head. After proving that he can wield the Sword of Truth, Richard knows that a confrontation with Darken Rahl looms. But Kahlan beseeches him to reach beyond his sword and invoke his inner nobility in order to face the dangerous challenges ahead.",
    "cover": "http://books.google.com/books/content?id=WzO7jSs6XTYC&printsec=frontcover&img=1&zoom=1&edge=curl&source=gbs_api",
    "genres": [
      "Fiction"
    ],
    "isbn": "9780795330766"
  },
  ...
]
```

> Metadata Provider: Open Library

```shell
curl "https://abs.example.com/api/search/books?title=Wizard's%20First%20Rule&author=Terry%20Goodkind&provider=openlibrary" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
[
  {
    "title": "Wizard's First Rule",
    "author": "Terry Goodkind",
    "publishedYear": null,
    "cover": null,
    "id": "OL20134604W",
    "key": "/works/OL20134604W",
    "covers": [
      "https://covers.openlibrary.org/b/id/8785389-L.jpg"
    ],
    "description": null,
    "cleanedTitle": "wizards first rule",
    "titleDistance": 1,
    "totalPossibleDistance": 33,
    "cleanedAuthor": "terry goodkind",
    "authorDistance": 0,
    "includesAuthor": "terry goodkind",
    "totalDistance": 1,
    "includesTitle": "wizards first rule"
  },
  ...
]
```

> Metadata Provider: iTunes

```shell
curl "https://abs.example.com/api/search/books?title=Wizard's%20First%20Rule&author=Terry%20Goodkind&provider=itunes" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 293863242,
    "artistId": 279725677,
    "title": "Wizard's First Rule: Sword of Truth, Book 1 (Unabridged)",
    "author": "Terry Goodkind",
    "description": "The masterpiece that started Terry Goodkind's New York Times bestselling epic Sword of TruthIn the aftermath of the brutal murder of his father, a mysterious woman, Kahlan Amnell, appears in Richard Cypher's forest sanctuary seeking help...and more. His world, his very beliefs, are shattered when ancient debts come due with thundering violence.In a dark age it takes courage to live, and more than mere courage to challenge those who hold dominion, Richard and Kahlan must take up that challenge or become the next victims. Beyond awaits a bewitching land where even the best of their hearts could betray them. Yet, Richard fears nothing so much as what secrets his sword might reveal about his own soul. Falling in love would destroy them - for reasons Richard can't imagine and Kahlan dare not say.In their darkest hour, hunted relentlessly, tormented by treachery and loss, Kahlan calls upon Richard to reach beyond his sword - to invoke within himself something more noble. Neither knows that the rules of battle have just changed...or that their time has run out.Wizard's First Rule is the beginning. One book. One Rule. Witness the birth of a legend.",
    "publishedYear": "2008",
    "genres": [
      "Sci-Fi & Fantasy"
    ],
    "cover": "https://is1-ssl.mzstatic.com/image/thumb/Music123/v4/e7/f9/05/e7f90571-b5be-be74-064e-81da7ce94143/rm_image.jpg/600x600bb.jpg"
  }
]
```

> Metadata Provider: Audible

```shell
curl "https://abs.example.com/api/search/books?title=Wizard's%20First%20Rule&author=Terry%20Goodkind&provider=audible" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
[
  {
    "title": "Wizard's First Rule",
    "subtitle": "Sword of Truth, Book 1",
    "author": "Terry Goodkind",
    "narrator": "Sam Tsoutsouvas",
    "publisher": "Brilliance Audio",
    "publishedYear": "2008",
    "description": "The masterpiece that started Terry Goodkind's New York Times bestselling epic Sword of Truth In the aftermath of the brutal murder of his father, a mysterious woman, Kahlan Amnell, appears in Richard Cypher's forest sanctuary seeking help...and more. His world, his very beliefs, are shattered when ancient debts come due with thundering violence. In a dark age it takes courage to live, and more than mere courage to challenge those who hold dominion, Richard and Kahlan must take up that challenge or become the next victims. Beyond awaits a bewitching land where even the best of their hearts could betray them. Yet, Richard fears nothing so much as what secrets his sword might reveal about his own soul. Falling in love would destroy them - for reasons Richard can't imagine and Kahlan dare not say. In their darkest hour, hunted relentlessly, tormented by treachery and loss, Kahlan calls upon Richard to reach beyond his sword - to invoke within himself something more noble. Neither knows that the rules of battle have just changed...or that their time has run out. Wizard's First Rule is the beginning. One book. One Rule. Witness the birth of a legend.",
    "cover": "https://m.media-amazon.com/images/I/81E153-vqwL.jpg",
    "asin": "B002V0QK4C",
    "genres": [
      "Literature & Fiction",
      "Science Fiction & Fantasy"
    ],
    "tags": "Genre Fiction, Movie, TV & Video Game Tie-Ins, Fantasy, Epic",
    "series": [
      {
        "series": "Sword of Truth",
        "sequence": "1"
      }
    ],
    "language": "English",
    "duration": 2046,
    "region": null,
    "rating": "4.5"
  }
]
```

This endpoint searches a metadata provider for a book. An array of book search results is returned.

### HTTP Request

`GET http://abs.example.com/api/search/books`

### Query Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`title` | String | `''` | The book title to search for. If using Audible for `provider`, can also be the book's ASIN.
`author` | String | `''` | The author to search for.
`provider` | String | `google` | The metadata provider to use. See [Library Metadata Providers](#library-metadata-providers) for options.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See Below

#### Response Schema

Each response will be an array of objects with the attributes depending on the requested metadata provider.

#### Metadata Provider: Google

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The book's Google ID.
`title` | String | The book's title.
`subtitle` | String or null | The book's subtitle.
`author` | String or null | The book's author.
`publisher` | String or null | The book's publisher.
`description` | String or null | The book's description.
`cover` | String or null | The URL of the book's cover image.
`genres` | Array of String | The book's genres.
`isbn` | String | The book's ISBN.

#### Metadata Provider: Open Library

Attribute | Type | Description
--------- | ---- | -----------
`title` | String | The book's title.
`author` | String or null | The book's author.
`publishedYear` | Integer | The year the book was published.
`cover` | String or null | The URL of the book's cover image.
`id` | String | The book's Open Library ID.
`key` | String | The path of the book's Open Library URL.
`covers` | Array of String | URLs of cover images for the book.
`description` | String or null | The book's description.
`cleanedTitle` | String | A cleaned version of the query title used for searching.
`titleDistance` | Integer | The Levenshtein distance between `cleanedTitle` and `title`.
`totalPossibleDistance` | Integer | The maximum for `totalDistance`.
`cleanedAuthor` | String | A cleaned version of the query author used for searching.
`authorDistance` | Integer | The Levenshtein distance between `cleanedAuthor` and `author`.
`includesAuthor` | String | The query author contained in `author`.
`totalDistance` | Integer | `titleDistance` + `authorDistance`
`includesTitle` | String | The query title contained in `title`.

#### Metadata Provider: iTunes

Attribute | Type | Description
--------- | ---- | -----------
`id` | Integer | The book's iTunes ID.
`artistId` | Integer | The book's author's iTunes ID.
`title` | String | The book's title.
`author` | String or null | The book's author.
`description` | String or null | The book's description.
`publishedYear` | String or null | The year the book was published.
`genres` | Array of String | The book's genres.
`cover` | String or null | The URL of the book's cover image.

#### Metadata Provider: Audible

Attribute | Type | Description
--------- | ---- | -----------
`title` | String | The book's title.
`subtitle` | String or null | The book's subtitle.
`author` | String or null | The book's author.
`narrator` | String or null | The book's narrator.
`publisher` | String or null | The book's publisher.
`publishedYear` | String or null | The year the book was published.
`description` | String or null | The book's description.
`cover` | String or null | The URL of the book's cover image.
`asin` | String | The book's ASIN.
`genres` | Array of String | The book's genres.
`tags` | String | A comma and space separated list of the book's tags.
`series` | Array of [Series Sequence](#series-sequence) | The book's series.
`language` | String | The book's language.
`duration` | Integer | The total duration (in minutes) of the book.
`region` | String or null | The Audible region that was searched.
`rating` | String or null | The book's Audible rating.


## Search for Podcasts

```shell
curl "https://abs.example.com/api/search/podcast?term=Welcome%20To%20Night%20Vale" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 536258179,
    "artistId": 718704794,
    "title": "Welcome to Night Vale",
    "artistName": "Night Vale Presents",
    "description": "",
    "descriptionPlain": "",
    "releaseDate": "2022-11-15T05:00:00Z",
    "genres": [
      "Science Fiction",
      "Podcasts",
      "Fiction"
    ],
    "cover": "https://is4-ssl.mzstatic.com/image/thumb/Podcasts125/v4/4a/31/35/4a3135d0-1fe7-a2d7-fb43-d182ec175402/mza_8232698753950666850.jpg/600x600bb.jpg",
    "trackCount": 280,
    "feedUrl": "http://feeds.nightvalepresents.com/welcometonightvalepodcast",
    "pageUrl": "https://podcasts.apple.com/us/podcast/welcome-to-night-vale/id536258179?uo=4"
  },
  ...
]
```

This endpoint searches iTunes for podcasts and returns an array of the results.

### HTTP Request

`GET http://abs.example.com/api/search/podcast`

### Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
`term` | String | The search term to search for (i.e. the title of the podcast).

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See Below

#### Response Schema

The response will be an array of objects with the following attributes:

Attribute | Type | Description
--------- | ---- | -----------
`id` | Integer | The iTunes ID of the podcast.
`artistId` | Integer | The podcast's author's iTunes ID.
`title` | String | The tile of the podcast.
`artistName` | String | The podcast's author.
`description` | String | An HTML encoded description of the podcast.
`descriptionPlain` | String | A plain text description of the podcast.
`releaseDate` | String | The podcast's release date.
`genres` | Array of String | The podcast's genres.
`cover` | String | The URL of the podcast's cover image.
`trackCount` | Integer | The number of episodes the podcast has.
`feedUrl` | String | The URL of the podcast's RSS feed.
`pageUrl` | String | The URL of the podcast's iTunes page.


## Search for an Author

```shell
curl "https://abs.example.com/api/search/authors?q=Terry%20Goodkind" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "asin": "B000APZOQA",
  "description": "Terry Goodkind is a #1 New York Times Bestselling Author and creator of the critically acclaimed masterwork, ‘The Sword of Truth’. He has written 30+ major, bestselling novels, has been published in more than 20 languages world-wide, and has sold more than 26 Million books. ‘The Sword of Truth’ is a revered literary tour de force, comprised of 17 volumes, borne from over 25 years of dedicated writing. Terry Goodkind's brilliant books are character-driven stories, with a focus on the complexity of the human psyche. Goodkind has an uncanny grasp for crafting compelling stories about people like you and me, trapped in terrifying situations. With masterful storytelling, Goodkind brings us into the lives of his characters; characters that must rise to face not only challenges, but their deepest fears. For that reason, Goodkind’s characters speak to the best and worst in all of us. While ‘The Sword of Truth’ series is confirmation enough of Goodkind’s incredible storytelling abilities, his broad talents are also clearly evident in his contemporary novels, set within our own world. His post-‘Sword of Truth’ books are a thrilling, dizzying, mix of modern narrative, with every bit of Goodkind’s masterful voice intact. The bond built between the reader and one of the world’s great authors, rises above worlds and settings, mere backdrops for Goodkind’s uniquely intricate stories of life, love, challenge, and triumph. \"My privilege in life is the joy of writing books and telling stories about people who fascinate me, the good and the bad. I am grateful to all of my readers for the critical role they play in making these books possible. Your passion is my passion, and I thank you.\" - Terry Goodkind For more, please visit: http://terrygoodkind.com",
  "image": "https://images-na.ssl-images-amazon.com/images/I/51NoQTm33OL.jpg",
  "name": "Terry Goodkind"
}
```

This endpoint searches [Audnexus](https://github.com/laxamentumtech/audnexus) (which mostly uses Audible for its data) for authors.

### HTTP Request

`GET http://abs.example.com/api/search/authors`

### Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
`q` | String | The search query. The provided name must match the author's name on Audnexus exactly to get a result.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See Below

#### Response Schema

Either `null` or an object with the following attributes will be returned.

Attribute | Type | Description
--------- | ---- | -----------
`asin` | String | The author's ASIN.
`description` | String | The author's description.
`image` | String | The URL of the author's image.
`name` | String | The author's name.
