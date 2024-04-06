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
    "metadataFileFormat": "json",
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
    "dateFormat": "MM/dd/yyyy",
    "language": "en-us",
    "logLevel": 2,
    "version": "2.2.5"
  },
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
`Source` | String | The server's installation source.


## Logout

```shell
curl -X POST "https://abs.example.com/logout" \
  -H "Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY" \
  -H "Content-Type: application/json" \
  -d '{"socketId": "AFcTcb7xBLsSPnIzAAAV"}'
```

This endpoint logs out a client from the server. If the `socketId` parameter is provided, the server removes the socket from the client list. When using a socket connection this allows a client to change the user without needing to re-create the socket connection.

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

## OAuth2 Authorization Request

```shell
curl "https://abs.example.com/auth/openid?code_challenge=1234&code_challenge_method=S256&redirect_uri=audiobookshelf%3A%2F%2Foauth&client_id=Audiobookshelf-App&response_type=code&state=42"
```

> Response header (depending on SSO provider)

```
Location: https://auth.example.com/application/o/authorize/?client_id=G9DbJqJ&scope=openid%20profile%20email&response_type=code&redirect_uri=https%3A%2F%2Fabs.example.com%2Fauth%2Fopenid%2Fmobile-redirect&state=2000&code_challenge=C424242&code_challenge_method=S256
```

This endpoint starts a standard OAuth2 flow with PKCE (required - S256; see [RFC7636](https://datatracker.ietf.org/doc/html/rfc7636#section-4.1)), to log the user in using SSO.

For the `code_challenge`, you must randomly generate a minimum 32-byte string called verifier (PKCE challenge).
With the verifier, you can then generate the challenge. See the examples on the right side.

Also you must generate a random string and send it in the `state` parameter.


> Code Challenge Pseudo-Code

```
code_challenge = BASE64URL-ENCODE(SHA256(ASCII(code_verifier)))
```

> Code Challenge plain Javascript Code (all used functions are available in NodeJS and Browsers)

```js
function base64URLEncode(arrayBuffer) {
  let base64String = btoa(String.fromCharCode.apply(null, new Uint8Array(arrayBuffer)))
  return base64String.replace(/\+/g, '-').replace(/\//g, '_').replace(/=+$/g, '')
}

async function sha256(plain) {
  const encoder = new TextEncoder()
  const data = encoder.encode(plain)
  return await window.crypto.subtle.digest('SHA-256', data)
}

function generateRandomString() {
  var array = new Uint32Array(42)
  window.crypto.getRandomValues(array)
  return Array.from(array, (dec) => ('0' + dec.toString(16)).slice(-2)).join('') // return as hex
}

const verifier = generateRandomString()
const challenge = base64URLEncode(await sha256(verifier))

const state = generateRandomString()
```

On a valid request, it will return a 302-redirect (usually with a `Location:` header), which will point to the ABS-configured OAuth2 Provider.
It will include your generated `state`-parameter, check if it matches.
You would usually then have to open this redirect-URL in a Browser to present to the user.

Note that you will have to preserve the cookies you receive in this call for using it in `/auth/openid/callback` (check if you need to set a parameter for the HTTP library you are using for that).

When the user has logged in (successfully) inside the Browser, the Browser will redirect to the URL `redirect_uri` which should be a URL your website or app can open (like a universal app link). The call to the `redirect_uri` will include state and code GET parameters. Check if the state parameter is the same as above and use the `code` for the call to `/auth/openid/callback`.

> Redirect URL which is opened in the user's browser by the SSO Provider

```txt
redirect_uri?code=42&state=2000
```


### HTTP Request

`GET http://abs.example.com/auth/openid`

### Query Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`code_challenge` | String | **Required** | PKCE code_challenge you generated from `verifier`
`code_challenge_method` | String | S256 | Must be `S256`
`response_type` | String | code | Only `code` is supported
`redirect_uri` | String | **Required** | URL where to redirect after a successful login. Must be whitelisted in ABS
`client_id` | String | **Required** | The name of your app (currently not used, but might be required at some point)
`state` | String | **Required** | A randomly generated string, which must match in subsequent requests

Other parameters are ignored.

### Response

Status | Meaning | Description
------ | ------- | -----------
302 | REDIRECT | Success, save the state-parameter and follow the redirect
400 | Bad Request | You submitted an invalid parameter
500 | Internal Server Error | Error in the flow

## OAuth2 Callback

```shell
curl "https://abs.example.com/auth/openid/callback?state=2000&code=42&code_verifier=1234"
```

> The above command returns a JSON structured like this:

```json
{
   "userDefaultLibraryId":"b2bab335-d9aa-4141-8394-fd98767504d7",
   "serverSettings":{
      "scannerFindCovers":false,
      "metadataFileFormat":"json",
      "backupSchedule":false,
      "authOpenIDJwksURL":"https://auth.example.com/application/o/audiobookshelf/jwks/",
      "authOpenIDAutoLaunch":true,
      "…"
   },
   "Source":"docker",
   "user":{
      "oldUserId":"usr_1234lasdnlk",
      "itemTagsSelected":[],
      "createdAt":1672769098296,
      "librariesAccessible":[  ],
      "mediaProgress":[],
      "oldUserId":"usr_1234lasdnlk",
      "permissions":{
         "accessExplicitContent":true,
         "delete":true,
         "download":true,
         "upload":true,
         "accessAllLibraries":true,
         "…"
      },
      "seriesHideFromContinueListening":[],
      "token":"eyJhbGciOiJIUzI1NiIsInASDLKAMSDklmad.ASLDKlkma.PNKNASDPNdnknsdfoP",
      "type":"admin",
      "username":"example"
   },
   "ereaderDevices":[]
}
```
This API call finalizes the OAuth2 flow. The behavior of this call depends on whether a `redirect_uri` was provided in the `/auth/openid` request:

- If a `redirect_uri` was provided, this call returns user JSON data.
- If a `redirect_uri` was not provided, it will redirect to `/login` (used internally by ABS-web).

It's important to note that the call to `/auth/openid/callback` is stateful. This means that the cookies set during the `/auth/openid` call must be sent along with this request.

### Query Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`state` | String | **Required** | The state string you generated in the first request
`code` | String | **Required** | The code you received when `redirect_uri` was called
`code_verifier` | String | **Required** | This is the verifier you generated when providing the `code_challenge` in the first request

Other parameters are ignored.

### Response

Status | Meaning | Description
------ | ------- | -----------
200 | OK | Success, user data in payload
302 | FOUND | Success, redirect to /login (internal use)
400 | Bad Request | You have no session
401 | Unauthorized | Error from the SSO provider
500 | Internal Server Error | Error in the flow

Error details are provided in the response body and in ABS logs.


## OAuth2 Mobile Redirect

```shell
curl "https://abs.example.com/auth/openid/mobile-redirect"
```

This is an internal endpoint, which should **not** be called directly by an application. It is intended purely for the redirection of SSO providers.

When you provide a `redirect_uri` in `/auth/openid`, ABS performs an important operation: it saves your `redirect_uri` and instructs the SSO provider to use `/auth/openid/mobile-redirect` instead. This endpoint, in turn, redirects to your original `redirect_uri`.

This mechanism allows ABS to provide a `https` callback URL, which is particularly useful for mobile apps.

This call does not require a cookie or session. It matches the `redirect_uri` using the `state` parameter.

### HTTP Request

`GET http://abs.example.com/auth/openid/mobile-redirect`

### Query Parameters

Parameter | Type | Default | Description
--------- | ---- | ------- | -----------
`code` | String | **Required** | OAuth2 state
`state` | String | **Required** | OAuth2 code

Other parameters are ignored.

### Response

Status | Meaning | Description
------ | ------- | -----------
302 | REDIRECT | Success
400 | Bad Request | No state or no redirect_uri associated to state
500 | Internal Server Error | Error in the flow

## Initialize the Server

```shell
curl -X POST "https://abs.example.com/init" \
  -H "Content-Type: application/json" \
  -d '{"newRoot": {"username": "root", "password": "*****"}}'
```

This endpoint initializes a server for use with a root user. This is required for new servers without a root user yet.

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

`GET http://abs.example.com/status`

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
