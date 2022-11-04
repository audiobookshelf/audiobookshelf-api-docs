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
		"id": "main",
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
			"disableWatcher": false,
			"skipMatchingMediaWithAsin": false,
			"skipMatchingMediaWithIsbn": false
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
			"disableWatcher": false,
			"skipMatchingMediaWithAsin": false,
			"skipMatchingMediaWithIsbn": false
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

`GET https://abs.example.com/libraries/<ID>`

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

`POST https://abs.example.com/libraries`

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
		"disableWatcher": false,
		"skipMatchingMediaWithAsin": false,
		"skipMatchingMediaWithIsbn": false
	},
	"createdAt": 1650462940610,
	"lastUpdate": 1655423464567
}
```

This endpoint updates a specific library.

### HTTP Request

`PATCH https://abs.example.com/libraries/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library to retrieve

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
name | String | The name of the library
folders | Array | See notice below
displayOrder | Number | Library order shown in clients
icon | String | Library icon (database|podcast|book|audiobook|comic)
provider | String | Preferred provider for library

<aside class="notice">When updating folders you must pass in the full array of folders. Any missing folders from the array will be removed. New folders must not have an "id" set because this will be set automatically.</aside>

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
		"disableWatcher": false,
		"skipMatchingMediaWithAsin": false,
		"skipMatchingMediaWithIsbn": false
	},
	"createdAt": 1653396692539,
	"lastUpdate": 1653396692539
}
```

This endpoint deletes a specific library.

### HTTP Request

`DELETE https://abs.example.com/libraries/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library to retrieve

<aside class="notice">Deleting a library will remove all library items including any user progress for those items.</aside>

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Library](#library)
