# Cache

## Purge All Cache

```shell
curl -X POST "https://abs.example.com/api/cache/purge" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint purges all cache on the server, deleting the entire directory at `/metadata/cache`.

### HTTP Request

`POST http://abs.example.com/api/cache/purge`

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
403 | Forbidden | An admin user is required to purge the cache.


## Purge Items Cache

```shell
curl -X POST "https://abs.example.com/api/cache/items/purge" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint purges the items cache on the server, deleting the entire directory at `/metadata/cache/items`.

### HTTP Request

`POST http://abs.example.com/api/cache/items/purge`

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
403 | Forbidden | An admin user is required to purge the items cache.
