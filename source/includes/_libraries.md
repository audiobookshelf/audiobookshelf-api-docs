# Libraries

## Get All Libraries

```shell
curl "https://abs.yourserver.com/api/libraries" \
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
		"id": "libkug8ylp8",
		"name": "Books",
		"folders": [
			{
				"id": "folkug8ylqz",
				"fullPath": "/books",
				"libraryId": "libkug8ylp8",
				"addedAt": 1633569261477
			}
		],
		"displayOrder": 2,
		"icon": "book",
		"mediaType": "book",
		"provider": "google",
		"settings": {
			"disableWatcher": false,
			"skipMatchingMediaWithAsin": false,
			"skipMatchingMediaWithIsbn": false
		},
		"createdAt": 1633569261477,
		"lastUpdate": 1646520922976
	},
	{
		"id": "libkuujrhzf",
		"name": "Comics",
		"folders": [
			{
				"id": "folkuujrhyp",
				"fullPath": "/comics",
				"libraryId": "libkuujrhzf",
				"addedAt": 1634433932839
			}
		],
		"displayOrder": 3,
		"icon": "comic",
		"mediaType": "book",
		"provider": "google",
		"settings": {
			"disableWatcher": false,
			"skipMatchingMediaWithAsin": false,
			"skipMatchingMediaWithIsbn": false
		},
		"createdAt": 1634433932839,
		"lastUpdate": 1646520929464
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

`GET http://abs.yourserver.com/api/libraries`

## Get a Specific Library

```shell
curl "https://abs.yourserver.com/api/libraries/lib_c1u6t4p45c35rf0nzd" \
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

`GET https://abs.yourserver.com/libraries/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library to retrieve
