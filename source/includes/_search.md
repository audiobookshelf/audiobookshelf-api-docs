# Search

## Search for Covers

```shell
curl "https://abs.example.com/api/search/covers?title=Wizards%20First%20Rule&author=Terry%20Goodkind&provider=openlibrary" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
[
  "https://covers.openlibrary.org/b/id/1005963-L.jpg",
  "https://covers.openlibrary.org/b/id/791977-L.jpg",
  "https://covers.openlibrary.org/b/id/766531-L.jpg",
  "https://covers.openlibrary.org/b/id/910943-L.jpg",
  "https://covers.openlibrary.org/b/id/8782857-L.jpg",
  "https://covers.openlibrary.org/b/id/8788596-L.jpg",
  "https://covers.openlibrary.org/b/id/8783892-L.jpg",
  "https://covers.openlibrary.org/b/id/8993240-L.jpg",
  "https://covers.openlibrary.org/b/id/10505009-L.jpg",
  "https://covers.openlibrary.org/b/id/1005881-L.jpg",
  "https://covers.openlibrary.org/b/id/8776837-L.jpg",
  "https://covers.openlibrary.org/b/id/10778344-L.jpg",
  "https://covers.openlibrary.org/b/id/11239659-L.jpg",
  "https://covers.openlibrary.org/b/id/12224404-L.jpg",
  "https://covers.openlibrary.org/b/OLID/OL9034948M-L.jpg",
  "https://covers.openlibrary.org/b/id/8785389-L.jpg"
]
```

This endpoint searches a metadata provider for covers. An array of URLs for cover images is returned.

### HTTP Request

`GET http://abs.example.com/api/search/covers`

### Query Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`podcast` | Binary | `0` | Whether to search for podcast covers. Only the `title` parameter is needed for podcasts. `0` for false, `1` for true.
`title` | String | **Required** | The media title to search for.
`author` | String or null | `null` | If searching for a book cover, the author to search for.
`provider` | String | **Required for Books** | If searching for a book cover, the metadata provider to use. See [Library Metadata Providers](#library-metadata-providers) for options.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | Array of String
