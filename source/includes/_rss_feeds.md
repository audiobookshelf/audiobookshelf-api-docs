# RSS Feeds

## Close an RSS Feed

```shell
curl -X POST "https://abs.example.com/api/feeds/li_bufnnmp4y5o2gbbxfm/close" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint closes an RSS feed.

### HTTP Request

`POST http://abs.example.com/api/feeds/<ID>/close`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the RSS feed.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
403 | Forbidden | An admin user is required to close an RSS feed.

## Open an RSS Feed for a Collection

```shell
curl -X POST "https://abs.example.com/api/feeds/collection/col_fpfstanv6gd7tq2qz7/open" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"serverAddress": "https://abs.example.com", "slug": "col_fpfstanv6gd7tq2qz7"}'
```

> The above command returns JSON structured like this:

```json
{
  "feed": {
    "id": "col_fpfstanv6gd7tq2qz7",
    "entityType": "collection",
    "entityId": "col_fpfstanv6gd7tq2qz7",
    "feedUrl": "https://abs.example.com/feed/col_fpfstanv6gd7tq2qz7",
    "meta": {
      "title": "Favorites",
      "description": null,
      "preventIndexing": true,
      "ownerName": null,
      "ownerEmail": null
    }
  }
}
```

This endpoint opens an RSS feed for a collection.

### HTTP Request

`POST http://abs.example.com/api/feeds/collection/<CollectionID>/open`

### URL Parameters

Parameter | Description
--------- | -----------
CollectionID | The ID of the collection.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`serverAddress` | String | The URL address of the server.
`slug` | String | The slug (the last part of the URL) to use for the RSS feed.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
400 | Bad Request | The `serverAddress` and `slug` parameters are required, or the collection does not have audio tracks, or the `slug` is already in use. |
403 | Forbidden | An admin user is required to open an RSS feed. |
404 | Not Found | No collection with the given ID exists. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`feed` | [RSS Feed Minified](#rss-feed-minified) Object | The RSS feed that was opened.


## Open an RSS Feed for a Library Item

```shell
curl -X POST "https://abs.example.com/api/feeds/item/li_bufnnmp4y5o2gbbxfm/open" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"serverAddress": "https://abs.example.com", "slug": "li_bufnnmp4y5o2gbbxfm"}'
```

> The above command returns JSON structured like this:

```json
{
  "feed": {
    "id": "li_bufnnmp4y5o2gbbxfm",
    "entityType": "item",
    "entityId": "li_bufnnmp4y5o2gbbxfm",
    "feedUrl": "https://abs.example.com/feed/li_bufnnmp4y5o2gbbxfm",
    "meta": {
      "title": "Welcome to Night Vale",
      "description": "\n      Twice-monthly community updates for the small desert town of Night Vale, where every conspiracy theory is true. Turn on your radio and hide. Never listened before? It's an ongoing radio show. Start with the current episode, and you'll catch on in no time. Or, go right to Episode 1 if you wanna binge-listen.\n    ",
      "preventIndexing": true,
      "ownerName": null,
      "ownerEmail": null
    }
  }
}
```

This endpoint opens an RSS feed for a library item.

### HTTP Request

`POST http://abs.example.com/api/feeds/item/<LibraryItemID>/open`

### URL Parameters

Parameter | Description
--------- | -----------
LibraryItemID | The ID of the library item.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`serverAddress` | String | The URL address of the server.
`slug` | String | The slug (the last part of the URL) to use for the RSS feed.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
400 | Bad Request | The `serverAddress` and `slug` parameters are required, or the item does not have audio tracks, or the `slug` is already in use. |
403 | Forbidden | An admin user is required to open an RSS feed. |
404 | Not Found | No library item with the given ID exists. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`feed` | [RSS Feed Minified](#rss-feed-minified) Object | The RSS feed that was opened.


## Open an RSS Feed for a Series

```shell
curl -X POST "https://abs.example.com/api/feeds/series/ser_cabkj4jeu8be3rap4g/open" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"serverAddress": "https://abs.example.com", "slug": "ser_cabkj4jeu8be3rap4g"}'
```

> The above command returns JSON structured like this:

```json
{
  "feed": {
    "id": "ser_cabkj4jeu8be3rap4g",
    "entityType": "series",
    "entityId": "ser_cabkj4jeu8be3rap4g",
    "feedUrl": "https://abs.example.com/feed/ser_cabkj4jeu8be3rap4g",
    "meta": {
      "title": "Sword of Truth",
      "description": null,
      "preventIndexing": true,
      "ownerName": null,
      "ownerEmail": null
    }
  }
}
```

This endpoint opens an RSS feed for a series.

### HTTP Request

`POST http://abs.example.com/api/feeds/series/<SeriesID>/open`

### URL Parameters

Parameter | Description
--------- | -----------
SeriesID | The ID of the series.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`serverAddress` | String | The URL address of the server.
`slug` | String | The slug (the last part of the URL) to use for the RSS feed.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
400 | Bad Request | The `serverAddress` and `slug` parameters are required, or the series does not have audio tracks, or the `slug` is already in use. |
403 | Forbidden | An admin user is required to open an RSS feed. |
404 | Not Found | No series with the given ID exists. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`feed` | [RSS Feed Minified](#rss-feed-minified) Object | The RSS feed that was opened.
