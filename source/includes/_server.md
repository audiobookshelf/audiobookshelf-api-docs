# Server

## Login

```shell
curl -X POST "https://abs.example.com/login" \
  -H "Content-Type: application/json" \
  -d '{"username": "root", "password": "*****"}'
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
    "settings": {
      "mobileOrderBy": "addedAt",
      "mobileOrderDesc": true,
      "mobileFilterBy": "all",
      "orderBy": "media.metadata.title",
      "orderDesc": false,
      "filterBy": "all",
      "playbackRate": 1,
      "bookshelfCoverSize": 120,
      "collapseSeries": false,
      "useChapterTrack": true
    },
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

This endpoint logs in a client to the server, returning information about the user and server. The `/api/authorize` ([Get Authorized User and Server Information](#get-authorized-user-and-server-information)) endpoint is also available if an API token was persisted.

### HTTP Request

`POST http://abs.example.com/login`

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`username` | String | The username to log in with.
`password` | String | The password of the user.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See Below
401 | Unauthorized | Invalid username or password. | Error Message

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`user` | [User](#user) Object | The authenticated user.
`userDefaultLibraryId` | String | The ID of the first library in the list the user has access to.
`serverSettings` | [Server Settings](#server-settings) Object | The server's settings.
`feeds` | Array of [RSS Feed](#rss-feed) | The open RSS feeds.
`Source` | String | The server's installation source.


## Logout

```shell
curl -X POST "https://abs.example.com/logout" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"socketId": "AFcTcb7xBLsSPnIzAAAV"}'
```

This endpoint logs out a client from the server. If the `socketId` parameter is provided, the server removes the socket from the client list.

### HTTP Request

`POST http://abs.example.com/logout`

### Optional Parameters

Parameter | Type | Description
--------- | ---- | -----------
`socketId` | String | The ID of the connected socket.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success


## Initialize the Server

```shell
curl -X POST "https://abs.example.com/init" \
  -H "Content-Type: application/json" \
  -d '{"username": "root", "password": "*****"}'
```

This endpoint initializes a server for use with a root user.

### HTTP Request

`POST http://abs.example.com/init`

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`newRoot` | [New Root User](#new-root-user-parameters) Object (See Below) | The new root user.

#### New Root User Parameters

Parameter | Type | Description
--------- | ---- | -----------
`username` | String | The username of the new root user.
`password` | String | The password of the new root user, may be empty.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
500 | Internal Server Error | The server has already been initialized.


## Check the Server's Status

```shell
curl "https://abs.example.com/status"
```

> The above command returns JSON structured like this:

```json
{
  "isInit": true,
  "language": "en-us"
}
```

This endpoint reports the server's initialization status.

### HTTP Request

`GET http://abs.example.com/init`

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See Below

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`isInit` | Boolean | Whether the server has been initialized.
`language` | String | The server's default language.
`ConfigPath` | String | The server's config path. Will only exist if `isInit` is `false`.
`MetadataPath` | String | The server's metadata path. Will only exist if `isInit` is `false`.


## Ping the Server

```shell
curl "https://abs.example.com/ping"
```

> The above command returns JSON structured like this:

```json
{
  "success": true
}
```

This endpoint is a simple check to see if the server is operating and responding with JSON correctly.

### HTTP Request

`GET http://abs.example.com/ping`

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See Below

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`success` | Boolean | Will always be `true`.


## Healthcheck

```shell
curl "https://abs.example.com/healthcheck"
```

This endpoint is a simple check to see if the server is operating and can respond.

### HTTP Request

`GET http://abs.example.com/healthcheck`

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
