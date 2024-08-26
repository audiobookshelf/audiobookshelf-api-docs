# Series Endpoints

## Get a Series

```shell
curl "https://abs.example.com/api/series/ser_cabkj4jeu8be3rap4g?include=progress" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "id": "ser_cabkj4jeu8be3rap4g",
  "name": "Sword of Truth",
  "description": null,
  "addedAt": 1650621073750,
  "updatedAt": 1650621073750,
  "progress": {
    "libraryItemIds": [
      "li_8gch9ve09orgn4fdz8"
    ],
    "libraryItemIdsFinished": [
      "li_8gch9ve09orgn4fdz8"
    ],
    "isFinished": true
  }
}
```

This endpoint retrieves a series.

### HTTP Request

`GET https://abs.example.com/api/series/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the series.

### Optional Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
`include` | String | A comma-separated list of what to include with the series. The options are `progress` and `rssfeed`.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Series](#series) with optional extra attributes from `include` (see below).
404 | Not Found | No series with the provided ID exists. |

#### Extra Attributes

Attribute | Type | Description
--------- | ---- | -----------
`progress` | [Series Progress](#series-progress) Object (See Below) | If `progress` was requested, the series' progress.
`rssFeed` | [RSS Feed Minified](#rss-feed-minified) Object or null | If `rssfeed` was requested, the series' open RSS feed. It will be `null` if the series' RSS feed is closed.

#### Series Progress

Attribute | Type | Description
--------- | ---- | -----------
`libraryItemIds`| Array of String | The IDs of the library items in the series.
`libraryItemIdsFinished` | Array of String | The IDs of the library items in the series that are finished.
`isFinished` | Boolean | Whether the series is finished.


## Update a Series

```shell
curl -X PATCH "https://abs.example.com/api/series/ser_cabkj4jeu8be3rap4g" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"description": "A really cool series."}'
```

> The above command returns JSON structured like this:

```json
{
  "id": "ser_cabkj4jeu8be3rap4g",
  "name": "Sword of Truth",
  "description": "A really cool series.",
  "addedAt": 1650621073750,
  "updatedAt": 1650621073750
}
```

This endpoint updates a series and returns it.

### HTTP Request

`PATCH http://abs.example.com/api/series/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the series.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`name` | String | The name of the series.
`description` | String or null | A description for the series.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Series](#series)
404 | Not Found | No series with provided ID exists. |
