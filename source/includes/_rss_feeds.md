# RSS Feeds

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
    "feedUrl": "https://abs.example.com/feed/li_bufnnmp4y5o2gbbxfm"
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
