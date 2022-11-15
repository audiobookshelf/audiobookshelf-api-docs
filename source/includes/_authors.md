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
