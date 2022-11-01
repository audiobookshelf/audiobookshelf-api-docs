# Schemas

## Library

```json
{
  "id": "main",
  "name": "Main",
  "folders": [...],
  "displayOrder": 1,
  "icon": "audiobook",
  "mediaType": "book",
  "provider": "audible",
  "settings": {...},
  "createdAt": 1633522963509,
  "lastUpdate": 1646520916818
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the library. (Read Only)
`name` | String | The name of the library.
`folders` | Array of [Folder](#folder) | The folders that the library is composed of on the server.
`displayOrder` | Integer | Display position of the library in the list of libraries. Must be `>= 1`.  
`icon` | String | The selected icon for the library. Must be `database`, `podcast`, `book`, `audiobook`, or `comic`.
`mediaType` | String | The type of media that this library contains. Will be `book` or `podcast`. (Read Only)
`provider` | String | Perferred metadata provider for the library. For book libraries, it must be `google`, `openlibrary`, `itunes`, `audible`, `audible.ca`, `audible.uk`, `audible.au`, `audible.fr`, `audible.de`, `audible.jp`, `audible.it`, `audible.in`, or `audible.es`. For podcast libraries, it must be `itunes`.
`settings` | [Library Settings](#library-settings) Object | The settings for the library.
`createdAt` | Integer | The time (in ms since Unix epoch) when this library was created. (Read Only)
`lastUpdate` | Integer | The time (in ms since Unix epoch) when this library was last updated. (Read Only)

## Library Settings

```json
{
  "coverAspectRatio": 1,
  "disableWatcher": false,
  "skipMatchingMediaWithAsin": false,
  "skipMatchingMediaWithIsbn": false,
  "autoScanCronExpression": null
}
```

Attribute | Type | Description
--------- | ---- | -----------
`coverAspectRatio` | Integer | Whether or not the library should use square book covers. Must be `0` (for false) or `1` (for true).
`disableWatcher` | Boolean | Whether or not to disable the folder watcher for the library.
`skipMatchingMediaWithAsin` | Boolean | Whether or not to skip matching books that already have an ASIN.
`skipMatchingMediaWithIsbn` | Boolean | Whether or not to skip matching books that already have an ISBN.
`autoScanCronExpression` | String or null | The [cron expression](https://en.wikipedia.org/wiki/Cron#CRON_expression) for when to automatically scan the library folders. If `null`, automatic scanning will be disabled.

## Folder

```json
{
  "id": "fol_bev1zuxhb0j0s1wehr",
  "fullPath": "/podcasts",
  "libraryId": "lib_c1u6t4p45c35rf0nzd",
  "addedAt": 1650462940610
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the folder. (Read Only) 
`fullPath` | String | The path on the server for the folder. (Read Only)
`libraryId` | String | The ID of the library this folder belongs to. (Read Only)
`addedAt` | Integer | The time (in ms since Unix epoch) when this folder was added. (Read Only)

<aside class="notice">
  Only provide <code>fullPath</code> when creating a new folder. The other attributes will be automatically set.
</aside>
