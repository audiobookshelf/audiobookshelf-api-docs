# Library Items

## Get a Specific Library Item

```shell
curl "https://abs.yourserver.com/api/items/li_v3fa59h43yk3rn6ryx" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "id": "li_v3fa59h43yk3rn6ryx"
}
```

This endpoint retrieves a specific library item.

### HTTP Request

`GET http://abs.yourserver.com/api/items/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item to retrieve
