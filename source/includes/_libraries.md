# Libraries

## Get All Libraries

```shell
curl "https://abs.example.com/api/libraries" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
[
	{
		"id": "lib_5yvub9dqvctlcrza6h",
		"name": "Main",
		"folders": [
			{
				"id": "audiobooks",
				"fullPath": "/audiobooks",
				"libraryId": "main"
			}
		],
		"displayOrder": 1,
		"icon": "audiobook",
		"mediaType": "book",
		"provider": "audible",
		"settings": {
      "coverAspectRatio": 1,
      "disableWatcher": false,
      "skipMatchingMediaWithAsin": false,
      "skipMatchingMediaWithIsbn": false,
      "autoScanCronExpression": null
    },
		"createdAt": 1633522963509,
		"lastUpdate": 1646520916818
	},
	{
		"id": "lib_c1u6t4p45c35rf0nzd",
		"name": "Podcasts",
		"folders": [
			{
				"id": "fol_bev1zuxhb0j0s1wehr",
				"fullPath": "/podcasts",
				"libraryId": "lib_c1u6t4p45c35rf0nzd",
				"addedAt": 1650462940610
			}
		],
		"displayOrder": 4,
		"icon": "database",
		"mediaType": "podcast",
		"provider": "itunes",
		"settings": {
      "coverAspectRatio": 1,
      "disableWatcher": false,
      "skipMatchingMediaWithAsin": false,
      "skipMatchingMediaWithIsbn": false,
      "autoScanCronExpression": null
    },
		"createdAt": 1650462940610,
		"lastUpdate": 1650462940610
	}
]
```

This endpoint retrieves all libraries accessible to the user.

### HTTP Request

`GET http://abs.example.com/api/libraries`

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | Array of [Library](#library)


## Get a Specific Library

```shell
curl "https://abs.example.com/api/libraries/lib_c1u6t4p45c35rf0nzd" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
	"id": "lib_c1u6t4p45c35rf0nzd",
	"name": "Podcasts",
	"folders": [
		{
			"id": "fol_bev1zuxhb0j0s1wehr",
			"fullPath": "/podcasts",
			"libraryId": "lib_c1u6t4p45c35rf0nzd",
			"addedAt": 1650462940610
		}
	],
	"displayOrder": 4,
	"icon": "database",
	"mediaType": "podcast",
	"provider": "itunes",
	"settings": {
    "coverAspectRatio": 1,
    "disableWatcher": false,
    "skipMatchingMediaWithAsin": false,
    "skipMatchingMediaWithIsbn": false,
    "autoScanCronExpression": null
  },
	"createdAt": 1650462940610,
	"lastUpdate": 1650462940610
}
```

This endpoint retrieves a specific library.

<aside class="notice">If the library is not accessible to the user a 404 status code is returned.</aside>

### HTTP Request

`GET https://abs.example.com/api/libraries/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library to retrieve

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Library](#library)


## Create a Library

```shell
curl -X POST "https://abs.example.com/api/libraries" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"name": "Podcasts", "folders": [{"fullPath": "/podcasts"}], "icon": "podcast", "mediaType": "podcast", "provider": "itunes"}'
```

> The above command returns JSON structured like this:

```json
{
	"id": "lib_c1u6t4p45c35rf0nzd",
	"name": "Podcasts",
	"folders": [
		{
			"id": "fol_bev1zuxhb0j0s1wehr",
			"fullPath": "/podcasts",
			"libraryId": "lib_c1u6t4p45c35rf0nzd",
			"addedAt": 1650462940610
		}
	],
	"displayOrder": 4,
	"icon": "podcast",
	"mediaType": "podcast",
	"provider": "itunes",
	"settings": {
    "coverAspectRatio": 1,
    "disableWatcher": false,
    "skipMatchingMediaWithAsin": false,
    "skipMatchingMediaWithIsbn": false,
    "autoScanCronExpression": null
  },
	"createdAt": 1650462940610,
	"lastUpdate": 1655423464567
}
```

This endpoint creates a library with the specified options.

`POST https://abs.example.com/api/libraries`

### Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`name` | String | **Required** | The name of the library.
`folders` | Array of [Folder](#folder) | **Required** | The folders of the library. Only specify the `fullPath`.
`icon` | String | `database` | The icon of the library. Must be `database`, `podcast`, `book`, `audiobook`, or `comic`.
`mediaType` | String | `book` | The type of media that the library contains. Must be `book` or `podcast`.
`provider` | String | `google` | Perferred metadata provider for the library. For book libraries, it must be `google`, `openlibrary`, `itunes`, `audible`, `audible.ca`, `audible.uk`, `audible.au`, `audible.fr`, `audible.de`, `audible.jp`, `audible.it`, `audible.in`, or `audible.es`. For podcast libraries, it must be `itunes`.
`settings` | [Library Settings](#library-settings) Object | See Below | The settings for the library.

#### Library Settings Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`coverAspectRatio` | Integer | `1` | Whether or not the library should use square book covers. Must be `0` (for false) or `1` (for true).
`disableWatcher` | Boolean | `false` | Whether or not to disable the folder watcher for the library.
`skipMatchingMediaWithAsin` | Boolean | `false` | Whether or not to skip matching books that already have an ASIN.
`skipMatchingMediaWithIsbn` | Boolean | `false` | Whether or not to skip matching books that already have an ISBN.
`autoScanCronExpression` | String or null | `null` | The [cron expression](https://en.wikipedia.org/wiki/Cron#CRON_expression) for when to automatically scan the library folders. If `null`, automatic scanning will be disabled.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Library](#library)


## Update a Specific Library

```shell
curl -X PATCH "https://abs.example.com/api/libraries/lib_c1u6t4p45c35rf0nzd" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json"
  -d '{"name": "Pods", "icon": "podcast"}'
```

> The above command returns JSON structured like this:

```json
{
	"id": "lib_c1u6t4p45c35rf0nzd",
	"name": "Pods",
	"folders": [
		{
			"id": "fol_bev1zuxhb0j0s1wehr",
			"fullPath": "/podcasts",
			"libraryId": "lib_c1u6t4p45c35rf0nzd",
			"addedAt": 1650462940610
		}
	],
	"displayOrder": 4,
	"icon": "podcast",
	"mediaType": "podcast",
	"provider": "itunes",
	"settings": {
    "coverAspectRatio": 1,
    "disableWatcher": false,
    "skipMatchingMediaWithAsin": false,
    "skipMatchingMediaWithIsbn": false,
    "autoScanCronExpression": null
  },
	"createdAt": 1650462940610,
	"lastUpdate": 1655423464567
}
```

This endpoint updates a specific library.

### HTTP Request

`PATCH https://abs.example.com/api/libraries/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library to retrieve

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`name` | String | The name of the library.
`folders` | Array of [Folder](#folder) | See the notice below. Only specify the `fullPath` for new folders.
`displayOrder` | Integer | Display position of the library in the list of libraries. Must be `>= 1`.
`icon` | String | The icon of the library. Must be `database`, `podcast`, `book`, `audiobook`, or `comic`.
`provider` | String | Perferred metadata provider for the library. For book libraries, it must be `google`, `openlibrary`, `itunes`, `audible`, `audible.ca`, `audible.uk`, `audible.au`, `audible.fr`, `audible.de`, `audible.jp`, `audible.it`, `audible.in`, or `audible.es`. For podcast libraries, it must be `itunes`.
`settings` | [Library Settings](#library-settings) Object | The settings for the library.

#### Library Settings Parameters

Parameter | Type | Description
--------- | ---- | -----------
`coverAspectRatio` | Integer | Whether or not the library should use square book covers. Must be `0` (for false) or `1` (for true).
`disableWatcher` | Boolean | Whether or not to disable the folder watcher for the library.
`skipMatchingMediaWithAsin` | Boolean | Whether or not to skip matching books that already have an ASIN.
`skipMatchingMediaWithIsbn` | Boolean | Whether or not to skip matching books that already have an ISBN.
`autoScanCronExpression` | String or null | The [cron expression](https://en.wikipedia.org/wiki/Cron#CRON_expression) for when to automatically scan the library folders. If `null`, automatic scanning will be disabled.

<aside class="notice">When updating folders you must pass in the full array of folders. Any missing folders from the array will be removed. New folders must not have an <code>id</code> set because this will be set automatically.</aside>

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Library](#library)


## Delete a Specific Library

```shell
curl -X DELETE "https://abs.example.com/api/libraries/lib_5yvub9dqvctlcrza6h" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> If successful the deleted library will be returned like this:

```json
{
	"id": "lib_5yvub9dqvctlcrza6h",
	"name": "audiobooks",
	"folders": [
		{
			"id": "fol_zdat63120karrt7i52",
			"fullPath": "/audiobooks",
			"libraryId": "lib_5yvub9dqvctlcrza6g",
			"addedAt": 1653396692539
		}
	],
	"displayOrder": 5,
	"icon": "database",
	"mediaType": "book",
	"provider": "audible",
	"settings": {
    "coverAspectRatio": 1,
    "disableWatcher": false,
    "skipMatchingMediaWithAsin": false,
    "skipMatchingMediaWithIsbn": false,
    "autoScanCronExpression": null
  },
	"createdAt": 1653396692539,
	"lastUpdate": 1653396692539
}
```

This endpoint deletes a specific library.

### HTTP Request

`DELETE https://abs.example.com/api/libraries/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library to retrieve

<aside class="notice">Deleting a library will remove all library items including any user progress for those items.</aside>

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Library](#library)


## Get a Library's Items

```shell
curl "https://abs.example.com/api/libraries/lib_c1u6t4p45c35rf0nzd/items?sort=media.metadata.title&filter=authors.YXV0X3ozbGVpbWd5Ymw3dWYzeTRhYg%3D%3D&collapseseries=1" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "results": [
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
      "size": 96335771,
      "collapsedSeries": {
        "id": "ser_cabkj4jeu8be3rap4g",
        "name": "Sword of Truth",
        "nameIgnorePrefix": "Sword of Truth",
        "numBooks": 1
      }
    }
  ],
  "total": 1,
  "limit": 0,
  "page": 0,
  "sortBy": "media.metadata.title",
  "sortDesc": false,
  "filterBy": "authors.YXV0X3ozbGVpbWd5Ymw3dWYzeTRhYg==",
  "mediaType": "book",
  "minified": false,
  "collapseseries": true
}
```

This endpoint returns a library's items, optionally sorted and/or filtered.

### HTTP Request

`GET https://abs.example.com/api/libraries/<ID>/items`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library.

### Optional Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
limit | Integer | Limit the number of returned results per page. If `0`, no limit will be applied.
page | Integer | The page number (0 indexed) to request. If there is no limit applied, then page will have no effect and all results will be returned.
sort | String | What to sort the results by. Specify the attribute to sort by using JavaScript object notation. For example, to sort by title use `sort=media.metadata.title`.
desc | Binary | Whether or not to reverse the sort order. `0` for false, `1` for true.
filter | String | What to filter the results by. See note below.
minified | Binary | Whether or not to request minified objects. `0` for false, `1` for true.
collapseseries | Binary | Whether or not to collapse books in a series to a single entry. `0` for false, `1` for true.g

#### Filtering

Most filters are composed of two parts, a group and a value, put together as `group.value`. The groups are: genres, tags, series, authors, progress, narrators, missing, and languages.

* For the genres, tags, narrators, and languages groups, the value is what genre, tag, narrator, or language to filter by.
* For the series and authors groups, the value is the ID of the series or author.
* For the series group, the value can also be No Series.
* For the progress group, the value can be:
  * Finished
  * Not Started
  * Not Finished
  * In Progress
* For the missing group, the value can be:
  * ASIN
  * ISBN
  * Subtitle
  * Author
  * Publisher Year
  * Series
  * Description
  * Genres
  * Tags
  * Narrator
  * Publisher
  * Language

All values must be first Base64 encoded and then URL encoded.

Other filters are issues and feed-open.

Examples:

* To filter for the Sci Fi genre:
  * `Sci Fi` is Base64 encoded as `U2NpIEZp` 
  * Already URL encoded.
  * Then use `filter=genres.U2NpIEZp`.
* To filter for the author Terry Goodkind who has the ID of aut_z3leimgybl7uf3y4ab:
  * `aut_z3leimgybl7uf3y4ab` is Base64 encoded as `YXV0X3ozbGVpbWd5Ymw3dWYzeTRhYg==`.
  * `YXV0X3ozbGVpbWd5Ymw3dWYzeTRhYg==` is URL encoded as `YXV0X3ozbGVpbWd5Ymw3dWYzeTRhYg%3D%3D`.
  * Then use `filter=authors.YXV0X3ozbGVpbWd5Ymw3dWYzeTRhYg%3D%3D`.
* To filter for items that are in progress:
  * `In Progress` is Base64 encoded as `SW4gUHJvZ3Jlc3M=`.
  * `SW4gUHJvZ3Jlc3M=` is URL encoded as `SW4gUHJvZ3Jlc3M%3D`.
  * Then use `filter=progress.SW4gUHJvZ3Jlc3M%3D`.
* To filter for items with their RSS feed open:
  * Use `filter=feed-open`.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See Below

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`results` | Array of [Library Item](#library-item) | The requested library items. If `minified` or `collapseseries` is `true`, it will be an array of [Library Item Minified](#library-item-minified). If `collapseseries` is `true`, then a [Series Num Books](#series-num-books) object will be added as `collapsedSeries` for titles that belong to a series. Otherwise, if filtering by series, `media.metadata.series` will be replaced by the matching [Series Sequence](#series-sequence) object.
`total` | Integer | The total number of items.
`limit` | Integer | The limit set in the request.
`page` | Integer | The page set in request.
`sortBy` | String | The sort set in the request. Will not exist if no sort was set.
`sortDesc` | Boolean | Whether or not the sort is reversed.
`filterBy` | String | The filter set in the request, URL decoded. Will not exist if no filter was set.
`mediaType` | String | The media type of the library. Will be `book` or `podcast`.
`minified` | Boolean | Whether or not minified was set in the request.
`collapseseries` | Boolean | Whether or not collapseseries was set in the request.
