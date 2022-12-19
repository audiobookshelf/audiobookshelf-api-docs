# Misc

## Upload Files

```shell
curl -X POST "https://abs.example.com/api/upload" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -F title="Wizard's First Rule" \
  -F author="Terry Goodkind" \
  -F series="Sword of Truth" \
  -F library="lib_c1u6t4p45c35rf0nzd" \
  -F folder="fol_bev1zuxhb0j0s1wehr" \
  -F 0=@"Terry Goodkind - SOT Bk01 - Wizards First Rule 01.mp3" \
  -F 1=@"Terry Goodkind - SOT Bk01 - Wizards First Rule 02.mp3" \
  -F 2=@cover.jpg
```

This endpoint uploads library item files to the server.

### HTTP Request

`POST http://abs.example.com/api/upload`

### Form Parameters

Parameter | Type | Description
--------- | ---- | -----------
`title` | String | The library item's title.
`author` | String | Optionally, the library item's author.
`series` | String | Optionally, the library item's series.
`library` | String | The ID of the library to put the item in.
`folder` | String | The ID of the folder to put the item in.

The files will be put in a directory at `<folderDir>/<author>/<series>/<title>`.

The form keys for the files can be anything as they are ignored.

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


## Get Authorized User and Server Information

```shell
curl -X POST "https://abs.example.com/api/authorize" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "user": {
    "id": "root",
    "username": "root",
    "type": "root",
    "token": "exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY",
    "mediaProgress": [
      {
        "id": "li_bufnnmp4y5o2gbbxfm-ep_lh6ko39pumnrma3dhv",
        "libraryItemId": "li_bufnnmp4y5o2gbbxfm",
        "episodeId": "ep_lh6ko39pumnrma3dhv",
        "duration": 1454.18449,
        "progress": 0.434998929881311,
        "currentTime": 632.568697,
        "isFinished": false,
        "hideFromContinueListening": false,
        "lastUpdate": 1668586015691,
        "startedAt": 1668120083771,
        "finishedAt": null
      }
    ],
    "seriesHideFromContinueListening": [],
    "bookmarks": [],
    "isActive": true,
    "isLocked": false,
    "lastSeen": 1669010786013,
    "createdAt": 1666543632566,
    "permissions": {
      "download": true,
      "update": true,
      "delete": true,
      "upload": true,
      "accessAllLibraries": true,
      "accessAllTags": true,
      "accessExplicitContent": true
    },
    "librariesAccessible": [],
    "itemTagsAccessible": []
  },
  "userDefaultLibraryId": "lib_c1u6t4p45c35rf0nzd",
  "serverSettings": {
    "id": "server-settings",
    "scannerFindCovers": false,
    "scannerCoverProvider": "audible",
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
  },
  "feeds": [],
  "Source": "docker"
}
```

This endpoint retrieves information about the authorized user and the server. Used for logging into a client if an API token was persisted. Returns the same payload as `/login` ([Login](#login)).

### HTTP Request

`POST http://abs.example.com/api/authorize`

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
401 | Unauthorized | No authorization was provided. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`user` | [User](#user) Object | The authenticated user.
`userDefaultLibraryId` | String | The ID of the first library in the list the user has access to.
`serverSettings` | [Server Settings](#server-settings) Object | The server's settings.
`feeds` | Array of [RSS Feed](#rss-feed) | The open RSS feeds.
`Source` | String | The server's installation source.

## Get All Tags

```shell
curl "https://abs.example.com/api/tags" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "tags": [
    "Favorite"
  ]
}
```

This endpoint retrieves all tags assigned to library items.

### HTTP Request

`GET http://abs.example.com/api/tags`

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See Below
404 | Not Found | An admin user is required to get all tags. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`tags` | Array of String | The requested tags.


## Rename a Tag

```shell
curl -X POST "https://abs.example.com/api/tags/rename" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"tag": "Favorite", "newTag": "The Best"}'
```

> The above command returns JSON structured like this:

```json
{
  "tagMerged": false,
  "numItemsUpdated": 1
}
```

This endpoint renames an existing tag.

### HTTP Request

`POST http://abs.example.com/api/tags/rename`

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`tag` | String | The current name of the tag.
`newTag` | String | The new name for the tag.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See Below
400 | Bad Request | `tag` and `newTag` are required parameters. |
404 | Not Found | An admin user is required to rename tags. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`tagMerged` | Boolean | Whether the renamed tag was merged into another tag.
`numItemsUpdated` | Integer | The number of library items that had their tags changed.


## Validate a Cron Expression

```shell
curl -X POST "https://abs.example.com/api/validate-cron" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"expression": "30 1 * * *"}'
```

This endpoint validates a given [cron expression](https://en.wikipedia.org/wiki/Cron#CRON_expression).

### HTTP Request

`POST http://abs.example.com/api/validate-cron`

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`expression` | String | The cron expression to validate.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
400 | Bad Request | The `expression` parameter is required, or the `expression` is invalid.
