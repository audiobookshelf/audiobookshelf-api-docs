# Notifications

## Get Notifications

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
