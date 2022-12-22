# Socket

Audiobookshelf uses [Socket.io](https://socket.io/) for bidirectional communication between clients and the server.
Each client must first authenticate itself using a user's API token in order to subscribe to events for that user.
There is also [an example](https://github.com/advplyr/abs-socket-client-demo) for how to use the socket.

<aside class="notice">
If the socket gets disconnected and then re-connects, it will have a new socket ID and will need to authenticate again.
</aside>

## Client Events

> `auth`

```js
socket.emit('auth', 'exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY')
```

> `cancel_scan`

```js
socket.emit('cancel_scan', 'lib_c1u6t4p45c35rf0nzd')
```

> `set_log_listener`

```js
socket.emit('set_log_listener', 2)
```

> `message_all_users`

```js
socket.emit('message_all_users', { message: 'Message from admin' })
```

These are events that clients can emit.

Name | Description | Schema
---- | ----------- | ------
`auth` | Authenticates the socket connection. Causes the server to emit the `init` or `invalid_token` event. | API Token String
`cancel_scan` | Cancels an in progress library scan. | Library ID String
`set_log_listener` | Makes the server emit `log` events of the given level or below to the client. | Log Level Integer: `1` for debug, `2` for info, or `3` for warnings, `4` for errors.
`remove_log_listener` | Removes the client as a log listener. |
`fetch_daily_logs` | Causes the server to emit the `daily_logs` event. |
`message_all_users` | **Admin Users Only** Send a message to all users using the `admin_message` server event. | [Message All Users](#message-all-users) Object
`ping` | Causes the server to emit the `pong` event. |

### Message All Users

Attribute | Type | Description
--------- | ---- | -----------
`message` | String | The message to send to all users.


## Server Events

The events that the server can emit are in the sections below.
Events marked with "**Admin Only**" are only sent to sockets with an authenticated admin user.


## User Events

Name | Description | Schema
---- | ----------- | ------
`user_online` | **Admin Only** A user is online. | [User with Session and Most Recent Progress](#user-with-session-and-most-recent-progress) Object
`user_offline` | **Admin Only** A user is offline. | [User with Session and Most Recent Progress](#user-with-session-and-most-recent-progress) Object
`user_added` | **Admin Only** A user was created. | [User](#user) Object
`user_updated` | The authenticated user has been updated. | [User](#user) Object
`user_removed` | **Admin Only** A user was deleted. | [User](#user) Object
`user_item_progress_updated` | One of the authenticated user's media progress was created/updated. | [User Item Progress Updated Event](#user-item-progress-updated-event)
`user_stream_update` | **Admin Only** A user started or stopped a playback session. | [User with Session and Most Recent Progress](#user-with-session-and-most-recent-progress) Object

### User Item Progress Updated Event

> User Item Progress Updated Event

```json
{
  "id": "li_bufnnmp4y5o2gbbxfm-ep_lh6ko39pumnrma3dhv",
  "data": {...}
}
```

Attribute | Type | Description
--------- | ---- | -----------
`id` | String | The ID of the updated media progress.
`data` | [Media Progress](#media-progress) Object | The updated media progress.


## Miscellaneous Events

Name | Description | Schema
---- | ----------- | ------
`init` | Successfully authenticated the socket. Response to `auth` client event. | [Init Event](#init-event) Object
`invalid_token` | An invalid token was given when authenticating. Response to `auth` client event. |
`log` | A single log event. Emitted after `set_log_listener` client event is sent. Cancelable with `remove_log_listener` client event. | [Log Event](#log-event) Object
`daily_logs` | The current day's log events. Response to `fetch_daily_logs` client event. | Array of [Log Event](#log-event)
`admin_message` | A message sent by an admin user. | String
`pong` | Response to `ping` client event. |

### Init Event

> Init Event

```json
{
  "userId": "root",
  "username": "root",
  "librariesScanning": [
    "lib_c1u6t4p45c35rf0nzd"
  ],
  "usersOnline": [...]
}
```

Attribute | Type | Description
--------- | ---- | -----------
`userId` | String | The ID of the authenticated user.
`username` | String | The username of the authenticated user.
`librariesScanning` | Array of String | The IDs of libraries currently being scanned.
`usersOnline` | Array of [User with Session and Most Recent Progress](#user-with-session-and-most-recent-progress) | Users that are currently online. Will only exist when the authenticated user is an admin.

### Log Event

> Log Event

```json
{
  "timestamp": "2022-12-21 15:08:47",
  "message": "[Server] Socket Connected dak2d0lroqBoL-MnAAAL",
  "levelName": "INFO",
  "level": 2
}
```

Attribute | Type | Description
--------- | ---- | -----------
`timestamp` | String | The date and time of the log event.
`message` | String | The log event's message.
`levelName` | String | The name of the log level. Can be `DEBUG`, `INFO`, `WARN`, or `ERROR`.
`level` | Integer | The log event's log level. Can be `1` (debug), `2` (info), `3` (warning), or `4` (error).
