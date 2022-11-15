# Authors

## Search for Authors

```shell
curl "https://abs.example.com/api/authors/search?q=Terry%20Goodkind" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
[
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
]
```

This endpoint searches for authors that match the query and returns the results.

### HTTP Request

`GET https://abs.example.com/api/authors/search?<q>`

### Query Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
q | String | **Required** | The URL encoded search query.
limit | Integer | `25` | Limit the number of returned results.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | Array of [Author](#author)


## Get an Author

```shell
curl "https://abs.example.com/api/authors/aut_z3leimgybl7uf3y4ab?include=items,series" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

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
  "libraryItems": [
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
      "isMissing": false,
      "isInvalid": false,
      "mediaType": "book",
      "media": {
        "metadata": {
          "title": "Wizards First Rule",
          "titleIgnorePrefix": "Wizards First Rule",
          "subtitle": null,
          "authorName": "Terry Goodkind",
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
        },
        "coverPath": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
        "tags": [],
        "numTracks": 2,
        "numAudioFiles": 2,
        "numChapters": 2,
        "numMissingParts": 0,
        "numInvalidAudioFiles": 0,
        "duration": 12000.946,
        "size": 96010240,
        "ebookFileFormat": null
      },
      "numFiles": 3,
      "size": 96335771
    }
  ],
  "series": [
    {
      "id": "ser_cabkj4jeu8be3rap4g",
      "name": "Sword of Truth",
      "items": [
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
          "isMissing": false,
          "isInvalid": false,
          "mediaType": "book",
          "media": {
            "metadata": {
              "title": "Wizards First Rule",
              "titleIgnorePrefix": "Wizards First Rule",
              "subtitle": null,
              "authorName": "Terry Goodkind",
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
              "explicit": false,
              "series": {
                "id": "ser_cabkj4jeu8be3rap4g",
                "name": "Sword of Truth",
                "sequence": "1"
              }
            },
            "coverPath": "/audiobooks/Terry Goodkind/Sword of Truth/Wizards First Rule/cover.jpg",
            "tags": [],
            "numTracks": 2,
            "numAudioFiles": 2,
            "numChapters": 2,
            "numMissingParts": 0,
            "numInvalidAudioFiles": 0,
            "duration": 12000.946,
            "size": 96010240,
            "ebookFileFormat": null
          },
          "numFiles": 3,
          "size": 96335771
        }
      ]
    }
  ]
}
```

This endpoint retrieves an author.

### HTTP Request

`GET https://abs.example.com/api/authors/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the author.

### Optional Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
`include` | String | A comma separated list of what to include with the author. The options are `items` and `series`. `series` will only have an effect if `items` are included.
`library` | String | The ID of the library to filter included items from.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Author](#author) with optional extra attributes from `include` (see below).
404 | Not Found | No author with provided ID exists. |

#### Extra Attributes

Attribute | Type | Description
--------- | ---- | -----------
`libraryItems` | Array of [Library Item Minified](#library-item-minified) | If `items` was requested, the library items written by the author.
`series` | Array of [Author Series](#author-series) (See Below) | If `items` and `series` were requested, the series that have books written by the author.

#### Author Series

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the series.
`name` | String | The name of the series.
`items` | Array of [Library Item Minified](#library-item-minified) | The items in the series. Each library item's media's metadata will have a `series` attribute, a [Series Sequence](#series-sequence), which is the matching series.


## Update an Author

```shell
curl -X PATCH "https://abs.example.com/api/authors/aut_z3leimgybl7uf3y4ab" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"asin": "B000APZOQA"}'
```

> The above command returns JSON structured like this:

```json
{
  "author": {
    "id": "aut_z3leimgybl7uf3y4ab",
    "asin": "B000APZOQA",
    "name": "Terry Goodkind",
    "description": null,
    "imagePath": null,
    "relImagePath": null,
    "addedAt": 1650621073750,
    "updatedAt": 1668506755298
  },
  "success": true
}
```

This endpoint updates an author. It also allows for merging of two authors if the name of this author is set to the name of another author.

### HTTP Request

`PATCH http://abs.example.com/api/authors/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the author.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`asin` | String or null | The ASIN of the author.
`name` | String | The name of the author.
`description` | String or null | A description of the author.
`imagePath` | String or null | The absolute path for the author image.
`relImagePath` | String or null | The path for the author image.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
404 | Not Found | No author with provided ID exists. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`author` | [Author](#author) Object | The updated author.
`merged` | Boolean | Will only exist and be `true` if the author was merged with another author.
`updated` | Boolean | Whether or not the author was updated normally. Will only exist if the author was not merged.


## Match an Author

```shell
curl -X POST "https://abs.example.com/api/authors/aut_z3leimgybl7uf3y4ab/match" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"q": "Terry Goodkind"}'
```

> The above command returns JSON structured like this:

```json
{
  "updated": true,
  "author": {
    "id": "aut_z3leimgybl7uf3y4ab",
    "asin": "B000APZOQA",
    "name": "Terry Goodkind",
    "description": "Terry Goodkind is a #1 New York Times Bestselling Author and creator of the critically acclaimed masterwork, ‘The Sword of Truth’. He has written 30+ major, bestselling novels, has been published in more than 20 languages world-wide, and has sold more than 26 Million books. ‘The Sword of Truth’ is a revered literary tour de force, comprised of 17 volumes, borne from over 25 years of dedicated writing. Terry Goodkind's brilliant books are character-driven stories, with a focus on the complexity of the human psyche. Goodkind has an uncanny grasp for crafting compelling stories about people like you and me, trapped in terrifying situations. With masterful storytelling, Goodkind brings us into the lives of his characters; characters that must rise to face not only challenges, but their deepest fears. For that reason, Goodkind’s characters speak to the best and worst in all of us. While ‘The Sword of Truth’ series is confirmation enough of Goodkind’s incredible storytelling abilities, his broad talents are also clearly evident in his contemporary novels, set within our own world. His post-‘Sword of Truth’ books are a thrilling, dizzying, mix of modern narrative, with every bit of Goodkind’s masterful voice intact. The bond built between the reader and one of the world’s great authors, rises above worlds and settings, mere backdrops for Goodkind’s uniquely intricate stories of life, love, challenge, and triumph. \"My privilege in life is the joy of writing books and telling stories about people who fascinate me, the good and the bad. I am grateful to all of my readers for the critical role they play in making these books possible. Your passion is my passion, and I thank you.\" - Terry Goodkind For more, please visit: http://terrygoodkind.com",
    "imagePath": "/metadata/authors/aut_z3leimgybl7uf3y4ab.jpg",
    "relImagePath": "/metadata/authors/aut_z3leimgybl7uf3y4ab.jpg",
    "addedAt": 1650621073750,
    "updatedAt": 1668506755298
  }
}
```

This endpoint matches the author using quick match. Quick match updates the author's description and image (if no image already existed) with information from audible.

### HTTP Request

`POST http://abs.example.com/api/authors/<ID>/match`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the author.

### Parameters

Either `asin` or `q` are **required**. If both are provided, `asin` will be used.

Parameter | Type | Description
--------- | ---- | -----------
`asin` | String | The ASIN to search for.
`q` | String | The author name to search for.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
404 | Not Found | No author with provided ID exists. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`updated` | Boolean | Whether or not the author was updated.
`author` | [Author](#author) Object | The updated author.
