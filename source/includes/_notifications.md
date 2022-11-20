# Notifications

## Get Notification Settings

```shell
curl "https://abs.example.com/api/notifications" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "events": [
      {
        "name": "onPodcastEpisodeDownloaded",
        "requiresLibrary": true,
        "libraryMediaType": "podcast",
        "description": "Triggered when a podcast episode is auto-downloaded",
        "variables": [
          "libraryItemId",
          "libraryId",
          "podcastTitle",
          "episodeTitle",
          "libraryName",
          "episodeId"
        ],
        "defaults": {
          "title": "New {{podcastTitle}} Episode!",
          "body": "{{episodeTitle}} has been added to {{libraryName}} library."
        },
        "testData": {
          "libraryItemId": "li_notification_test",
          "libraryId": "lib_test",
          "libraryName": "Podcasts",
          "podcastTitle": "Abs Test Podcast",
          "episodeId": "ep_notification_test",
          "episodeTitle": "Successful Test"
        }
      },
      {
        "name": "onTest",
        "requiresLibrary": false,
        "description": "Event for testing the notification system",
        "variables": [
          "version"
        ],
        "defaults": {
          "title": "Test Notification on Abs {{version}}",
          "body": "Test notificataion body for abs {{version}}."
        },
        "testData": {
          "version": "v2.2.5"
        }
      }
    ]
  },
  "settings": {
    "id": "notification-settings",
    "appriseType": "api",
    "appriseApiUrl": "https://apprise.example.com/notify",
    "notifications": [
      {
        "id": "noti_nod281qwkj5ow7h7fi",
        "libraryId": null,
        "eventName": "onPodcastEpisodeDownloaded",
        "urls": [
          "apprises://apprise.example.com/email"
        ],
        "titleTemplate": "New {{podcastTitle}} Episode!",
        "bodyTemplate": "{{episodeTitle}} has been added to {{libraryName}} library.",
        "enabled": true,
        "type": "info",
        "lastFiredAt": 1668776410792,
        "lastAttemptFailed": false,
        "numConsecutiveFailedAttempts": 0,
        "numTimesFired": 5,
        "createdAt": 1666545142424
      }
    ],
    "maxFailedAttempts": 5,
    "maxNotificationQueue": 20,
    "notificationDelay": 1000
  }
}
```

This endpoint retrieves the server's [Apprise](https://github.com/caronc/apprise-api) notification settings and event data.

### HTTP Request

`GET http://abs.example.com/api/notifications`

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
404 | Not Found | An admin user is required get notification settings. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`data.events` | Array of [Notification Event](#notification-event) | The notification event data.
`settings` | [Notification Settings](#notification-settings) Object | The notification settings of the server.


## Update Notification Settings

```shell
curl -X PATCH "https://abs.example.com/api/notifications" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"appriseApiUrl": "https://apprise.example.com/notify"}'
```

### HTTP Request

`PATCH http://abs.example.com/api/notifications`

### Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`appriseApiUrl` | String or null | | The full URL where the Apprise API to use is located.
`maxFailedAttempts` | Integer | `5` | The maximum number of times a notification fails before being disabled.
`maxNotificationQueue` | Integer | `20` | The maximum number of notifications in the notification queue before events are ignored.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
404 | Not Found | An admin user is required to update notification settings.


## Get Notification Event Data

```shell
curl "https://abs.example.com/api/notificationdata" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "events": [
    {
      "name": "onPodcastEpisodeDownloaded",
      "requiresLibrary": true,
      "libraryMediaType": "podcast",
      "description": "Triggered when a podcast episode is auto-downloaded",
      "variables": [
        "libraryItemId",
        "libraryId",
        "podcastTitle",
        "episodeTitle",
        "libraryName",
        "episodeId"
      ],
      "defaults": {
        "title": "New {{podcastTitle}} Episode!",
        "body": "{{episodeTitle}} has been added to {{libraryName}} library."
      },
      "testData": {
        "libraryItemId": "li_notification_test",
        "libraryId": "lib_test",
        "libraryName": "Podcasts",
        "podcastTitle": "Abs Test Podcast",
        "episodeId": "ep_notification_test",
        "episodeTitle": "Successful Test"
      }
    },
    {
      "name": "onTest",
      "requiresLibrary": false,
      "description": "Event for testing the notification system",
      "variables": [
        "version"
      ],
      "defaults": {
        "title": "Test Notification on Abs {{version}}",
        "body": "Test notificataion body for abs {{version}}."
      },
      "testData": {
        "version": "v2.2.4"
      }
    }
  ]
}
```

This endpoint retrieves the server's notification event data.

### HTTP Request

`GET http://abs.example.com/api/notificationdata`

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | See below.
404 | Not Found | An admin user is required get notification event data. |

#### Response Schema

Attribute | Type | Description
--------- | ---- | -----------
`events` | Array of [Notification Event](#notification-event) | The notification event data.
