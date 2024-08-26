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

### Query Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`bitrate` | String | `64k` | The bitrate to pass to ffmpeg.
`codec` | String | `aac` | The audio codec to pass to ffmpeg.
`channels` | Integer | `2` | The number of audio channels to pass to ffmpeg.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
403 | Forbidden | The user is not allowed to access the library item, or an admin user is required to make a `.m4b` file.
404 | Not Found | No library item with the given ID exists, or the library item has missing or invalid files.
500 | Internal Server Error | The library item is not a book, or does not have audio tracks.


## Cancel an M4B Encode Task

```shell
curl -X DELETE "https://abs.example.com/api/tools/item/li_8gch9ve09orgn4fdz8/encode-m4b" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint cancels an in-progress M4B encode task on the server.

### HTTP Request

`DELETE http://abs.example.com/api/tools/item/<ID>/encode-m4b`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the book library item.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
403 | Forbidden | The user is not allowed to access the library item, or an admin user is required to cancel an M4B encode task.
404 | Not Found | No library item with the given ID exists, or no M4B encode task is in progress for the library item.


## Update a Library Item's Audio Files' Embedded Metadata

```shell
curl -X POST "https://abs.example.com/api/tools/item/li_bufnnmp4y5o2gbbxfm/embed-metadata" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint updates a library item's audio files' embedded metadata.

### HTTP Request

`POST http://abs.example.com/api/tools/item/<ID>/embed-metadata`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the library item.

### Optional Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
`backup` | Binary | Whether to backup original audio files in `/metadata/cache/items`. The default is true if not specified. `0` for false, `1` for true.
`forceEmbedChapters` | Binary | Chapters are not embedded in multi-track audiobooks by default. Enable this setting to embed chapters in every audio file. `0` for false, `1` for true.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
403 | Forbidden | The user is not allowed to access the library item, or an admin user is required to update a library item's audio files' embedded metadata.
404 | Not Found | No library item with the given ID exists.
500 | Internal Server Error | The library item has missing parts, does not have audio files, or is not a book.
