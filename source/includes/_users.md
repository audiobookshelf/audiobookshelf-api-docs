# Users

## Create a User

```shell
curl -X POST "https://abs.example.com/api/users" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"username": "bob", "password": "12345", "type": "admin"}'
```

> The above command returns JSON structured like this:

```json
{
  "id": "usr_3vn1ywq2yc2aq4kfh4",
  "username": "bob",
  "type": "admin",
  "token": "exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY",
  "mediaProgress": [],
  "seriesHideFromContinueListening": [],
  "bookmarks": [],
  "isActive": true,
  "isLocked": false,
  "lastSeen": 1667687240810,
  "createdAt": 1666569607117,
  "settings": {
    "mobileOrderBy": "recent",
    "mobileOrderDesc": true,
    "mobileFilterBy": "all",
    "orderBy": "media.metadata.title",
    "orderDesc": false,
    "filterBy": "all",
    "playbackRate": 1,
    "bookshelfCoverSize": 120,
    "collapseSeries": false
  },
  "permissions": {
    "download": true,
    "update": true,
    "delete": false,
    "upload": true,
    "accessAllLibraries": true,
    "accessAllTags": true,
    "accessExplicitContent": true
  },
  "librariesAccessible": [],
  "itemTagsAccessible": []
}
```

This endpoint creates a user.

### HTTP Request

`POST http://abs.example.com/api/users`

### Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`username` | String | **Required** | The new user's username.
`password` | String | **Required** | The new user's password.
`type` | String | **Required** | The new user's type. May be `guest`, `user`, or `admin`.
`mediaProgress` | Array of [Media Progress](#media-progress) | `[]` | The new user's media progress.
`bookmarks` | Array of [Audio Bookmark](#audio-bookmark) | `[]` | The new user's bookmarks.
`seriesHideFromContinueListening` | Array of String | `[]` | The IDs of series to hide from the new user's "Continue Series" shelf.
`isActive` | Boolean | `true` | Whether or not the new user's account is active.
`isLocked` | Boolean | `false` | Whether or not the new user is locked.
`lastSeen` | Integer or null | `null` | The time (in ms since POSIX epoch) when the new user was last seen.
`createdAt` | Integer | `Date.now()` | The time (in ms since POSIX epoch) when the new user was created.
`settings` | [User Settings Parameters](#user-settings-parameters) Object | See Below | The new user's settings. 
`permissions` | [User Permissions Parameters](#user-permissions-parameters) Object | See Below | The new user's permissions.
`librariesAccessible` | Array of String | `[]` | The IDs of libraries that are accessible to the new user. An empty array means all libraries are accessible.
`itemTagsAccessible` | Array of String | `[]` | The tags that are accessible to the new user. An empty array means all tags are accessible.

<aside class="notice">
For <code>settings</code> and <code>permissions</code>, all parameters must be present if including them in the request.
</aside>

#### User Settings Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`mobileOrderBy` | String | `recent` | What to order library items by on mobile.
`mobileOrderDesc` | Boolean | `true` | Whether or not to reverse the sort order on mobile.
`mobileFilterBy` | String | `all` | What to filter library items by on mobile.
`orderBy` | String | `media.metadata.title` | What to order library items by.
`orderDesc` | Boolean | `false` | Whether or not to reverse the sort order.
`filterBy` | String | `all` | What to filter library items by.
`playbackRate` | Float | `1` | What speed to play items.
`bookshelfCoverSize` | Integer | `120` | What size to display covers at.
`collapseSeries` | Boolean | `false` | Whether or not to collapse series when viewing library items.

#### User Permissions Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`download` | Boolean | `true` | Whether or not the user can download items to the server.
`update` | Boolean | `true` | Whether or not the user can update library items.
`delete` | Boolean | `false` | Whether or not the user can delete library items.
`upload` | Boolean | `false` | Whether or not the user can upload items to the server. The default value is `true` if the user's `type` is `admin`.
`accessAllLibraries` | Boolean | `true` | Whether or not the user can access all libraries.
`accessAllTags` | Boolean | `true` | Whether or not the user can access all tags.
`accessExplicitContent` | Boolean | `true` | Whether or not the user can access explicit content.

### Response

Status | Meaning | Description | Schema
------ | ------- | ----------- | ------
200 | OK | Success | [User](#user)
403 | Forbidden | The user does not have permission to create new users. |
500 | Internal Server Error | Either the username provided is already taken, or the server failed to save the new user. |
