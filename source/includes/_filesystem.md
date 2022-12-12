# Filesystem

## Get All Filesystem Paths

```shell
curl "https://abs.example.com/api/filesystem" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
[
  ...,
  {
    "path": "/home",
    "dirname": "home",
    "fullPath": "/home",
    "level": 0,
    "dirs": [
      {
        "path": "/home/node",
        "dirname": "node",
        "fullPath": "/home/node",
        "level": 1,
        "dirs": []
      }
    ]
  },
  {
    "path": "/lib",
    "dirname": "lib",
    "fullPath": "/lib",
    "level": 0,
    "dirs": [
      {
        "path": "/lib/apk",
        "dirname": "apk",
        "fullPath": "/lib/apk",
        "level": 1,
        "dirs": [
          {
            "path": "/lib/apk/db",
            "dirname": "db",
            "fullPath": "/lib/apk/db",
            "level": 2,
            "dirs": []
          }
        ]
      },
      {
        "path": "/lib/firmware",
        "dirname": "firmware",
        "fullPath": "/lib/firmware",
        "level": 1,
        "dirs": []
      },
      {
        "path": "/lib/mdev",
        "dirname": "mdev",
        "fullPath": "/lib/mdev",
        "level": 1,
        "dirs": []
      },
      {
        "path": "/lib/modules-load.d",
        "dirname": "modules-load.d",
        "fullPath": "/lib/modules-load.d",
        "level": 1,
        "dirs": []
      },
      {
        "path": "/lib/sysctl.d",
        "dirname": "sysctl.d",
        "fullPath": "/lib/sysctl.d",
        "level": 1,
        "dirs": []
      }
    ]
  },
  ...
]
```

This endpoint retrieves the filesystem paths of the server.

### HTTP Request

`GET http://abs.example.com/api/filesystem`

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.

#### Response Schema

The response will be an array of objects representing the directories of the server's filesystem. Each directory object will be of the following format:

Attribute | Type | Description
--------- | ---- | -----------
`path` | String | The path of the directory.
`dirname` | String | The name of the directory.
`fullPath` | String | The full path of the directory.
`level` | Integer | The depth of the directory. `0` means a root level directory.
`dirs` | Array of Directory | The directories contained in this directory.
