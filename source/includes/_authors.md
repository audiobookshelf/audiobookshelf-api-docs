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
