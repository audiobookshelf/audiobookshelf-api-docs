# Series Endpoints

## Search for Series

```shell
curl "https://abs.example.com/api/series/search?q=Sword" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": "ser_cabkj4jeu8be3rap4g",
    "name": "Sword of Truth",
    "description": null,
    "addedAt": 1650621073750,
    "updatedAt": 1650621073750
  }
]
```

This endpoint searches for series that match the query and returns the results.

### HTTP Request

`GET https://abs.example.com/api/series/search?<q>`

### Query Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
q | String | **Required** | The URL encoded search query.
limit | Integer | `25` | Limit the number of returned results.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | Array of [Series](#series)
