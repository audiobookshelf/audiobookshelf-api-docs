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
filter | String | What to filter the results by. See [Filtering](#filtering).
minified | Binary | Whether or not to request minified objects. `0` for false, `1` for true.
collapseseries | Binary | Whether or not to collapse books in a series to a single entry. `0` for false, `1` for true.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See Below

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`results` | Array of [Library Item](#library-item) | The requested library items. If `minified` or `collapseseries` is `true`, it will be an array of [Library Item Minified](#library-item-minified). If `collapseseries` is `true`, then a [Series Num Books](#series-num-books) object will be added as `collapsedSeries` for titles that belong to a series. Otherwise, if filtering by series, `media.metadata.series` will be replaced by the matching [Series Sequence](#series-sequence) object.
`total` | Integer | The total number of results.
`limit` | Integer | The limit set in the request.
`page` | Integer | The page set in request.
`sortBy` | String | The sort set in the request. Will not exist if no sort was set.
`sortDesc` | Boolean | Whether or not the sort is reversed.
`filterBy` | String | The filter set in the request, URL decoded. Will not exist if no filter was set.
`mediaType` | String | The media type of the library. Will be `book` or `podcast`.
`minified` | Boolean | Whether or not minified was set in the request.
`collapseseries` | Boolean | Whether or not collapseseries was set in the request.


## Remove a Library's Items With Issues

```shell
curl -X DELETE "https://abs.example.com/api/libraries/lib_c1u6t4p45c35rf0nzd/issues" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint removes a library's items that have issues.

### HTTP Request

`DELETE https://abs.example.com/api/libraries/<ID>/issues`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success


## Get a Library's Series

```shell
curl "https://abs.example.com/api/libraries/lib_c1u6t4p45c35rf0nzd/series?minified=1" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "results": [
    {
      "id": "ser_cabkj4jeu8be3rap4g",
      "name": "Sword of Truth",
      "nameIgnorePrefix": "Sword of Truth",
      "nameIgnorePrefixSort": "Sword of Truth",
      "type": "series",
      "books": [
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
          "sequence": "1"
        }
      ],
      "addedAt": 1650621073750,
      "totalDuration": 12000.946
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

This endpoint returns a library's series.

### HTTP Request

`GET https://abs.example.com/api/libraries/<ID>/series`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library.

### Optional Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
limit | Integer | Limit the number of returned results per page. If `0`, no limit will be applied.
page | Integer | The page number (0 indexed) to request. If there is no limit applied, then page will have no effect and all results will be returned.
sort | String | What to sort the results by. By default, the results will be sorted by series name. Other sort options are: numBooks, totalDuration, and addedAt.
desc | Binary | Whether or not to reverse the sort order. `0` for false, `1` for true.
filter | String | What to filter the results by. See [Filtering](#filtering). The issues and feed-open filters are not available for this endpoint.
minified | Binary | Whether or not to request minified objects. `0` for false, `1` for true.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See Below

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`results` | Array of [Series Books](#series-books) | The requested series. If `minified` is `true`, the library items contained in the series will be [Library Item Minified](#library-item-minified).
`total` | Integer | The total number of results.
`limit` | Integer | The limit set in the request.
`page` | Integer | The page set in request.
`sortBy` | String | The sort set in the request. Will not exist if no sort was set.
`sortDesc` | Boolean | Whether or not the sort is reversed.
`filterBy` | String | The filter set in the request, URL decoded. Will not exist if no filter was set.
`minified` | Boolean | Whether or not minified was set in the request.


## Get a Library's Collections

```shell
curl "https://abs.example.com/api/libraries/lib_c1u6t4p45c35rf0nzd/collections?minified=1" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "id": "usr_fpfstanv6gd7tq2qz7",
  "libraryId": "lib_c1u6t4p45c35rf0nzd",
  "userId": "root",
  "name": "Favorites",
  "description": null,
  "cover": null,
  "coverFullPath": null,
  "books": [
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
  "lastUpdate": 1650621110769,
  "createdAt": 1650621073750
}
```

This endpoint returns a library's collections.

### HTTP Request

`GET https://abs.example.com/api/libraries/<ID>/collections`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library.

### Optional Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
limit | Integer | Limit the number of returned results per page. If `0`, no limit will be applied.
page | Integer | The page number (0 indexed) to request. If there is no limit applied, then page will have no effect and all results will be returned.
sort | String | What to sort the results by.
desc | Binary | Whether or not to reverse the sort order. `0` for false, `1` for true.
filter | String | What to filter the results by. See [Filtering](#filtering).
minified | Binary | Whether or not to request minified objects. `0` for false, `1` for true.

<!-- TODO: remove warning once sorting and filtering are implemented in LibraryController.getCollectionsForLibrary -->
<aside class="warning">Sorting and filtering are not yet implemented.</aside>

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See Below

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`results` | Array of [Collection Expanded](#collection-expanded) | The requested collections. If `minified` is `true`, the library items contained in the collections will be [Library Item Minified](#library-item-minified).
`total` | Integer | The total number of results.
`limit` | Integer | The limit set in the request.
`page` | Integer | The page set in request.
`sortBy` | String | The sort set in the request. Will not exist if no sort was set.
`sortDesc` | Boolean | Whether or not the sort is reversed.
`filterBy` | String | The filter set in the request, URL decoded. Will not exist if no filter was set.
`minified` | Boolean | Whether or not minified was set in the request.


## Get a Library's Personalized View

```shell
curl "https://abs.example.com/api/libraries/lib_c1u6t4p45c35rf0nzd/personalized" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": "continue-listening",
    "label": "Continue Listening",
    "type": "book",
    "entities": [
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
        "progressLastUpdate": 1650621110769
      }
    ],
    "category": "recentlyListened"
  },
  {
    "id": "continue-series",
    "label": "Continue Series",
    "type": "book",
    "entities": [
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
        "size": 96335771,
        "prevBookInProgressLastUpdate": 1650621110769
      }
    ],
    "category": "continueSeries"
  },
  {
    "id": "recently-added",
    "label": "Recently Added",
    "type": "book",
    "entities": [
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
    "category": "newestItems"
  },
  {
    "id": "recent-series",
    "label": "Recent Series",
    "type": "series",
    "entities": [
      {
        "id": "ser_cabkj4jeu8be3rap4g",
        "name": "Sword of Truth",
        "description": null,
        "addedAt": 1650621073750,
        "updatedAt": 1650621073750,
        "books": [
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
            "seriesSequence": "1"
          }
        ],
        "inProgress": true,
        "hideFromContinueListening": false,
        "bookInProgressLastUpdate": 1650621110769,
        "firstBookUnread": null
      }
    ],
    "category": "newestSeries"
  },
  {
    "id": "listen-again",
    "label": "Listen Again",
    "type": "book",
    "entities": [
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
        "finishedAt": 1650621110769
      }
    ],
    "category": "recentlyFinished"
  },
  {
    "id": "newest-authors",
    "label": "Newest Authors",
    "type": "authors",
    "entities": [
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
    ],
    "category": "newestAuthors"
  }
]
```

This endpoint returns a library's personalized view for home page display.

### HTTP Request

`GET https://abs.example.com/api/libraries/<ID>/personalized`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library.

### Optional Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
limit | Integer | Limit the number of items in each 'shelf' of the response. Default value is `10`.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | Array of Shelf (See Below)

#### Response Schema: Shelf

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the shelf.
`label` | String | The label of the shelf.
`type` | String | The type of items the shelf represents. Can be `book`, `series`, `authors`, `episode`, or `podcast`.
`entities` | Array | The entities to be displayed on the shelf. See below.
`category` | String | The category of the shelf.

#### Shelf Enitities

* `type` is `book`, `podcast`, or `episode`:
    * `entities` will be an array of [Library Item Minified](#library-item-minified).
* `type` is `episode`:
    * `id` is `continue-listening`, `listen-again`, or `episodes-recently-added`:
        * Library items will have a `recentEpisode` attribute, a [Podcast Episode](#podcast-episode), the episode to display.
* `type` is `series`:
    * `entities` will be an array of [Series](#series), with added attributes:
        * `books`, an array of [Library Item Minified](#library-item-minified), the books in the series.
            * Each library item in `books` will have a `seriesSequence` attribute, a String or null, the position of the book in the series.
        * `inProgress`, a Boolean, whether or not the user has started listening to the series.
        * `hideFromContinueListening`, a Boolean, whether or not the series has been marked to hide it from the "Continue Series" shelf.
        * `bookInProgressLastUpdate`, an Integer, the latest time (in ms since POSIX epoch) when the progress of a book in the series was updated.
        * `firstBookUnread`, a [Library Item Minified](#library-item-minified) or null, the first book in the series (by sequence) to have not been started or finished. Will be `null` if all books in the series are finished.
            * This library item will also have a `seriesSequence` attribute.
* `type` is `author`:
    * `entities` will be an array of [Author Expanded](#author-expanded).
* `id` is `listen-again`:
    * Library items will have a `finishedAt` attribute, an Integer, the time (in ms since POSIX epoch) when the book or episode was finished.
* `id` is `continue-listening`:
    * Library items will have a `progressLastUpdate` attribute, an Integer, the time (in ms since POSIX epoch) when the book's or episode's progress was last updated.
* `id` is `continue-series`:
    * Library items will have a `prevBookInProgressLastUpdate` attribute, an Integer, the time (in ms since POSIX epoch) of the most recent progress update of any book in the series.
    * The [Book Metadata Minified](#book-metadata-minified) in each library item will have a `series` attribute, a [Series Sequence](#series-sequence).


## Get a Library's Filter Data

```shell
curl "https://abs.example.com/api/libraries/lib_c1u6t4p45c35rf0nzd/filterdata" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

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

This endpoint returns a library's filter data that can be used for displaying a filter list.

### HTTP Request

`GET https://abs.example.com/api/libraries/<ID>/filterdata`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See Below

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`authors` | Array of [Author Minified](#author-minified) | The authors of books in the library.
`genres` | Array of String | The genres of books in the library.
`tags` | Array of String | The tags in the library.
`series` | Array of [Series](#series) | The series in the library. The series will only have their `id` and `name`.
`narrators` | Array of String | The narrators of books in the library.
`languages` | Array of String | The languages of books in the library.


## Search a Library

```shell
curl "https://abs.example.com/api/libraries/lib_c1u6t4p45c35rf0nzd/search?q=Terry%20Goodkind" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "book": [
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
  ],
  "tags": [],
  "authors": [
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
  ],
  "series": []
}
```

This endpoint searches a library for the query and returns the results.

### HTTP Request

`GET https://abs.example.com/api/libraries/<ID>/search?<q>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library.

### Query Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
q | String | **Required** | The URL encoded search query.
limit | Integer | `12` | Limit the number of returned results.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See Below
400 | Bad Request | No query string. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`book` or `podcast` | Array of [Library Item Expanded](#library-item-expanded) | The item results of the search. This attribute will be `book` or `podcast` depending on the library's media type.
`tags` | Array of String | The tag results of the search.
`authors` | Array of [Author Expanded](#author-expanded) | The author results of the search.
`sereis` | Array of [Series Books](#series-books) | The series results of the search.


## Get a Library's Stats

```shell
curl "https://abs.example.com/api/libraries/lib_c1u6t4p45c35rf0nzd/stats" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "totalItems": 1,
  "totalAuthors": 1,
  "totalGenres": 1,
  "totalDuration": 12000.946,
  "longestItems": [
    {
      "id": "li_8gch9ve09orgn4fdz8",
      "title": "Wizards First Rule",
      "duration": 12000.946
    }
  ],
  "numAudioTrack": 2,
  "totalSize": 268990279,
  "authorsWithCount": [
    {
      "id": "aut_z3leimgybl7uf3y4ab",
      "name": "Terry Goodkind",
      "count": 1
    }
  ],
  "genresWithCount": [
    {
      "genre": "Fantasy",
      "count": 1
    }
  ]
}
```

This endpoint returns a library's stats.

### HTTP Request

`GET https://abs.example.com/api/libraries/<ID>/stats`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See Below

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`totalItems` | Integer | The total amount of library items in the library.
`totalAuthors` | Integer | The total amount of authors in the library.
`totalGenres` | Integer | The total amount of genres in the library.
`totalDuration` | Float | The total duration (in seconds) of all items in the library.
`longestItems` | Array of Library Item Stats (See Below) | The items with the longest durations in the library.
`numAudioTrack` | Integer | The total number of audio tracks in the library.
`totalSize` | Integer | The total size (in bytes) of all items in the library.
`authorsWithCount` | Array of Author Stats (See Below) | The authors in the library.
`genresWithCount` | Array of Genre Stats (See Below) | The genres in the library.

#### Library Item Stats

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the library item.
`title` | String | The title of the library item.
`duration` | Float | The duration (in seconds) of the library item.

#### Author Stats

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the author.
`name` | String | The title of the author.
`count` | Integer | The number of books by the author in the library.

#### Genre Stats

Attribute | Type | Description
--------- | ---- | -----------
`genre` | String | The name of the genre.
`count` | Integer | The number of items in the library with the genre.
