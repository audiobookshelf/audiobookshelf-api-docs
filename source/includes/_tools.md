# Tools

## Encode a Book as M4B

```shell
curl -X POST "https://abs.example.com/api/tools/item/li_8gch9ve09orgn4fdz8/encode-m4b" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint starts a task on the server to take the existing audio files of a book, and merge and encode them into an `.m4b` file.

### HTTP Request

`POST http://abs.example.com/api/tools/item/<ID>/encode-m4b`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the book library item.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
403 | Forbidden | The user is not allowed to access the library item, or an admin user is required to make an `.m4b` file.
404 | Not Found | No library item with the given ID exists, or the library item has missing or invalid files.
500 | Internal Server Error | The library item is not a book, or does not have audio tracks.
