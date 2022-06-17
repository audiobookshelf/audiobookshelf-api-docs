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
		"disableWatcher": false,
		"skipMatchingMediaWithAsin": false,
		"skipMatchingMediaWithIsbn": false
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

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
name | String | The name of the library
folders | Array | See notice below
displayOrder | Number | Library order shown in clients
icon | String | Library icon (database|podcast|book|audiobook|comic)
provider | String | Preferred provider for library

<aside class="notice">When updating folders you must pass in the full array of folders. Any missing folders from the array will be removed. New folders must not have an "id" set because this will be set automatically.</aside>