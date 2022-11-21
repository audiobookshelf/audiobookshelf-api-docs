# Misc

## Upload Files

```shell
curl -X POST "https://abs.example.com/api/upload" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -F 0=@"Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3" \
  -F 1=@"Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3" \
  -F 2=@cover.jpg \
  -d $'{"title": "Wizard\'s First Rule", "author": "Terry Goodkind", "series": "Sword of Truth", "library": "lib_c1u6t4p45c35rf0nzd", "folder": "fol_bev1zuxhb0j0s1wehr"}'
```

This endpoint uploads library item files to the server.

### HTTP Request

`POST http://abs.example.com/api/upload`

### Form Parameters

The form keys can be anything as they are ignored. Each value should be the file to upload.

The following file types are supported:

* `.png`
* `.jpg`
* `.jpeg`
* `.webp`
* `.m4b`
* `.mp3`
* `.m4a`
* `.flac`
* `.opus`
* `.ogg`
* `.oga`
* `.mp4`
* `.aac`
* `.wma`
* `.aiff`
* `.wav`
* `.webm`
* `.webma`
* `.epub`
* `.pdf`
* `.mobi`
* `.azw3`
* `.cbr`
* `.cbz`
* `.nfo`
* `.txt`
* `.opf`
* `.abs`

### JSON Parameters

Parameter | Type | Description
--------- | ---- | -----------
`title` | String | The library item's title.
`author` | String | Optionally, the library item's author.
`series` | String | Optionally, the library item's series.
`library` | String | The ID of the library to put the item in.
`folder` | String | The ID of the folder to put the item in.

The files will be put in a directory at `<folderDir>/<author>/<series>/<title>`.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
403 | Forbidden | A user with upload permissions is required.
404 | Not Found | No library with the given ID exists, or no folder with the given ID exists in the library.
500 | Internal Server Error | No files were provided, or the upload directory already exists.


## Update Server Settings

```shell
curl -X PATCH "https://abs.example.com/api/settings" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"scannerFindCovers": false}'
```

> The above command returns JSON structured like this:

```json
{
  "success": true,
  "serverSettings": {
    "id": "server-settings",
    "scannerFindCovers": false,
    "scannerCoverProvider": "google",
    "scannerParseSubtitle": false,
    "scannerPreferAudioMetadata": false,
    "scannerPreferOpfMetadata": false,
    "scannerPreferMatchedMetadata": false,
    "scannerDisableWatcher": true,
    "scannerPreferOverdriveMediaMarker": false,
    "scannerUseSingleThreadedProber": true,
    "scannerMaxThreads": 0,
    "scannerUseTone": false,
    "storeCoverWithItem": false,
    "storeMetadataWithItem": false,
    "rateLimitLoginRequests": 10,
    "rateLimitLoginWindow": 600000,
    "backupSchedule": "30 1 * * *",
    "backupsToKeep": 2,
    "maxBackupSize": 1,
    "backupMetadataCovers": true,
    "loggerDailyLogsToKeep": 7,
    "loggerScannerLogsToKeep": 2,
    "homeBookshelfView": 1,
    "bookshelfView": 1,
    "sortingIgnorePrefix": false,
    "sortingPrefixes": [
      "the",
      "a"
    ],
    "chromecastEnabled": false,
    "enableEReader": false,
    "dateFormat": "MM/dd/yyyy",
    "language": "en-us",
    "logLevel": 2,
    "version": "2.2.5"
  }
}
```

This endpoint updates the server's settings.

### HTTP Request

`PATCH http://abs.example.com/api/settings`

### Parameters

Provide a [Server Settings](#server-settings) object with the key-value pairs to update.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
403 | Forbidden | An admin user is required to update server settings. |
500 | Internal Server Error | Invalid server settings update object. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`success` | Boolean | Whether the server settings were updated successfully.
`serverSettings` | [Server Settings](#server-settings) Object | The updated server settings.
