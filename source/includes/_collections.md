# Collections

## Create a Collection

```shell
curl -X POST "https://abs.example.com/api/collections" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"libraryId": "lib_c1u6t4p45c35rf0nzd", "name": "Favorites"}'
```

> The above command returns JSON structured like this:

```json
{
  "id": "col_fpfstanv6gd7tq2qz7",
  "libraryId": "lib_c1u6t4p45c35rf0nzd",
  "userId": "root",
  "name": "Favorites",
  "description": null,
  "cover": null,
  "coverFullPath": null,
  "books": [],
  "lastUpdate": 1650621073750,
  "createdAt": 1650621073750
}
```

This endpoint creates a collection and returns it.

### HTTP Request

`POST http://abs.example.com/api/collections`

### Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`libraryId` | String | **Required** | The ID of the library the collection belongs to.
`name` | String | **Required** | The name of the collection.
`description` | String or null | `null` | The collection's description.
`cover` | String or null | `null` | The path to the collection's cover.
`coverFullPath` | String or null | `null` | The full path to the collection's cover.
`books` | Array of String | `[]` | The IDs of book library items that are in the collection.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Collection Expanded](#collection-expanded)
403 | Forbidden | A user with update permissions is required to create collections. |
500 | Internal Server Error | `libraryId` and `name` are required parameters. |


## Get all Collections

```shell
curl "https://abs.example.com/api/collections" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": "col_fpfstanv6gd7tq2qz7",
    "libraryId": "lib_c1u6t4p45c35rf0nzd",
    "userId": "root",
    "name": "Favorites",
    "description": null,
    "cover": null,
    "coverFullPath": null,
    "books": [],
    "lastUpdate": 1650621073750,
    "createdAt": 1650621073750
  }
]
```

This endpoint retrieves all collections.

### HTTP Request

`GET http://abs.example.com/api/collections`

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | Array of [Collection Expanded](#collection-expanded)


## Get a Collection

```shell
curl "https://abs.example.com/api/collections/col_fpfstanv6gd7tq2qz7" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "id": "col_fpfstanv6gd7tq2qz7",
  "libraryId": "lib_c1u6t4p45c35rf0nzd",
  "userId": "root",
  "name": "Favorites",
  "description": null,
  "cover": null,
  "coverFullPath": null,
  "books": [],
  "lastUpdate": 1650621073750,
  "createdAt": 1650621073750
}
```

This endpoint retrieves a collection.

### HTTP Request

`GET http://abs.example.com/api/collections/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the collection.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Collection Expanded](#collection-expanded)
404 | Not Found | No collection with the specified ID exists. |


## Update a Collection

```shell
curl -X POST "https://abs.example.com/api/collections/col_fpfstanv6gd7tq2qz7" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"name": "The Best Books"}'
```

> The above command returns JSON structured like this:

```json
{
  "id": "col_fpfstanv6gd7tq2qz7",
  "libraryId": "lib_c1u6t4p45c35rf0nzd",
  "userId": "root",
  "name": "The Best Books",
  "description": null,
  "cover": null,
  "coverFullPath": null,
  "books": [],
  "lastUpdate": 1650621110769,
  "createdAt": 1650621073750
}
```

This endpoint updates a collection and returns it.

### HTTP Request

`POST http://abs.example.com/api/collections/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the collection.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`libraryId` | String | The ID of the library the collection belongs to.
`name` | String | The name of the collection.
`description` | String or null | The collection's description.
`cover` | String or null | The path to the collection's cover.
`coverFullPath` | String or null | The full path to the collection's cover.
`books` | Array of String | The IDs of book library items that are in the collection.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Collection Expanded](#collection-expanded)
403 | Forbidden | A user with update permissions is required to update collections. |
404 | Not Found | No collection with the specified ID exists. |


## Delete a Collection

```shell
curl -X DELETE "https://abs.example.com/api/collections/col_fpfstanv6gd7tq2qz7" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint deletes a collection from the database.

### HTTP Request

`DELETE http://abs.example.com/api/collections/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the collection.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
403 | Forbidden | A user with delete permissions is required to delete a collection.
404 | Not Found | No collection with the specified ID exists.
