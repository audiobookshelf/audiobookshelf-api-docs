# Socket

Audiobookshelf uses [Socket.io](https://socket.io/) for bidirectional communication between clients and the server. Each client must first authenticate itself using a user's API token in order to subscribe to events for that user.

<aside class="notice">
If the socket gets disconnected and then re-connects, it will have a new socket ID and will need to authenticate again.
</aside>

## Client Events

These are events that clients can emit.

Name | Description | Schema
---- | ----------- | ------
`auth` | Authenticate the socket. | API Token String
`cancel_scan` | Cancels an in progress library scan. | Library ID String
`set_log_listener` | Makes the server emit `log` events of the given level or below to the client. | Log Level Integer: `1` for debug, `2` for info, or `3` for warnings.
`remove_log_listener` | Removes the client as a log listener. |
`fetch_daily_logs` | Causes the server to emit the `daily_logs` event. |
`message_all_users` | **Admin Users Only** Send a message to all users using the `admin_message` server event. | Message String
`ping` | Causes the server to emit the `pong` event. |


## Server Events

These are events that the server can emit.

Name | Description | Schema
---- | ----------- | ------
`log` |
`daily_logs` |
`admin_message` |
`pong` |
