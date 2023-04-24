# Notifications

## Create a Notification

```shell
curl -X POST "https://abs.example.com/api/notifications" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"eventName": "onPodcastEpisodeDownloaded", "urls": ["apprises://apprise.example.com/email"], "titleTemplate": "New {{podcastTitle}} Episode!", "bodyTemplate": "{{episodeTitle}} has been added to {{libraryName}} library.", "enabled": true, "type": "info"}'
```

> The above command returns JSON structured like this:

```json
{
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
```

This endpoint creates a notification and returns the server's updated notification settings.

### HTTP Request

`POST http://abs.example.com/api/notifications`

### Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`libraryId` | String or null | `null` | The ID of the library the notification is associated with.
`eventName` | String | **Required** | The name of the event the notification will fire on.
`urls` | Array of String | **Required** | The Apprise URLs to use for the notification.
`titleTemplate` | String | **Required** | The template for the notification title.
`bodyTemplate` | String | **Required** | The template for the notification body.
`enabled` | Boolean | `false` | Whether the notification is enabled.
`type` | String or null | `null` | The notification's type.

<aside class="notice">
The <code>urls</code> array parameter must have a non-zero length for the notification to be saved.
</aside>

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Notification Settings](#notification-settings)
404 | Not Found | An admin user is required create notifications. |


## Delete a Notification

```shell
curl -X DELETE "https://abs.example.com/api/notifications/noti_nod281qwkj5ow7h7fi" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

> The above command returns JSON structured like this:

```json
{
  "id": "notification-settings",
  "appriseType": "api",
  "appriseApiUrl": "https://apprise.example.com/notify",
  "notifications": [],
  "maxFailedAttempts": 5,
  "maxNotificationQueue": 20,
  "notificationDelay": 1000
}
```

This endpoint deletes a notification and returns the server's updated notification settings.

### HTTP Request

`DELETE http://abs.example.com/api/notifications/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the notification.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Notification Settings](#notification-settings)
404 | Not Found | An admin user is required delete notifications, or no notification with the given ID exists. |


## Fire Test Notification Event

```shell
curl "https://abs.example.com/api/notifications/test" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint fires the test notification event.

### HTTP Request

`GET http://abs.example.com/api/notifications/test`

### Optional Query Parameters

Parameter | Type | Description
--------- | ---- | -----------
`fail` | Binary | Whether to intentionally cause the notification to fail. `0` for false, `1` for true.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
404 | Not Found | An admin user is required to fire notification events.


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
        "libraryName",
        "mediaTags",
        "podcastTitle",
        "podcastAuthor",
        "podcastDescription",
        "podcastGenres",
        "episodeId",
        "episodeTitle",
        "episodeSubtitle",
        "episodeDescription"
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
          "libraryName",
          "mediaTags",
          "podcastTitle",
          "podcastAuthor",
          "podcastDescription",
          "podcastGenres",
          "episodeId",
          "episodeTitle",
          "episodeSubtitle",
          "episodeDescription"
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


## Send Notification Test

```shell
curl "https://abs.example.com/api/notifications/noti_nod281qwkj5ow7h7fi/test" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY"
```

This endpoint sends a test to the given notification.

### HTTP Request

`GET http://abs.example.com/api/notifications/<ID>/test`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the notification.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success
404 | Not Found | An admin user is required to send notification tests, or no notification with the given ID exists.
500 | Internal Server Error | The Apprise URL is not set, or the notification failed to send.

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


## Update a Notification

```shell
curl -X PATCH "https://abs.example.com/api/notifications/noti_nod281qwkj5ow7h7fi" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"id": "noti_nod281qwkj5ow7h7fi", "titleTemplate": "New {{podcastTitle}} Episode: {{episodeTitle}}"}'
```

> The above command returns JSON structured like this:

```json
{
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
      "titleTemplate": "New {{podcastTitle}} Episode: {{episodeTitle}}",
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
```

This endpoint updates a notification and returns the server's updated notification settings.

### HTTP Request

`PATCH http://abs.example.com/api/notifications/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the notification.

### Parameters

Parameter | Type | Description
--------- | ---- | -----------
`id` | String | **Required** The ID of the notification.
`libraryId` | String or null | The ID of the library the notification is associated with.
`eventName` | String | The name of the event the notification will fire on.
`urls` | Array of String | The Apprise URLs to use for the notification.
`titleTemplate` | String | The template for the notification title.
`bodyTemplate` | String | The template for the notification body.
`enabled` | Boolean | Whether the notification is enabled.
`type` | String or null | The notification's type.

<aside class="notice">
The <code>id</code> parameter must be included for the notification to be saved.
</aside>

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [Notification Settings](#notification-settings)
404 | Not Found | An admin user is required update notifications, or no notification with the given ID exists. |
