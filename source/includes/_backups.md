# Backups

## Create a Backup

```shell
curl -X POST "https://abs.example.com/api/backups" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": "2022-11-14T0130",
    "backupMetadataCovers": true,
    "backupDirPath": "/metadata/backups",
    "datePretty": "Mon, Nov 14 2022 01:30",
    "fullPath": "/metadata/backups/2022-11-14T0130.audiobookshelf",
    "path": "backups/2022-11-14T0130.audiobookshelf",
    "filename": "2022-11-14T0130.audiobookshelf",
    "fileSize": 7776983,
    "createdAt": 1668411000329,
    "serverVersion": "2.2.4"
  },
  {
    "id": "2022-11-15T0105",
    "backupMetadataCovers": true,
    "backupDirPath": "/metadata/backups",
    "datePretty": "Tue, Nov 15 2022 01:05",
    "fullPath": "/metadata/backups/2022-11-15T0105.audiobookshelf",
    "path": "backups/2022-11-15T0105.audiobookshelf",
    "filename": "2022-11-15T0105.audiobookshelf",
    "fileSize": 7777148,
    "createdAt": 1668495954701,
    "serverVersion": "2.2.4"
  }
]
```

This endpoint creates a backup. All existing backups will be returned.

### HTTP Request

`POST http://abs.example.com/api/backups`

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | Array of [Backup](#backup)
403 | Forbidden | An admin user is required to create backups. |
500 | Internal Server Error | The server failed to create a backup. |
