---
title: Audiobookshelf API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://github.com/advplyr/audiobookshelf-slate'>View Doc Source</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - server
  - libraries
  - items
  - users
  - collections
  - playlists
  - me
  - backups
  - filesystem
  - authors
  - series
  - sessions
  - podcasts
  - notifications
  - search
  - cache
  - tools
  - rss_feeds
  - misc
  - socket
  - metadata_providers
  - filtering
  - schemas

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Audiobookshelf API
---

# Introduction

<aside class="warning">These API docs are out-of-date and are no longer maintained. We hope to implement automated OpenAPI docs in the future.</aside>

# Authentication

Audiobookshelf uses a users API token as a Bearer token for requests. For GET requests the API token can optionally be passed in as a query string.

You can find your API token by logging into the Audiobookshelf web app as an admin, go to the config → users page, and click on your account.

You may also get the API token programmatically using the [Login](#login) endpoint. The API token will be in the response at `response.user.token`.

API request header for authentication would look like this:

`Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY`

Optionally GET requests can use the API token like this:

`https://abs.example.com/api/items/li_asdfalwkerioa?token=exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY`

<aside class="notice">
Your API token will be much longer then the one in the examples.
</aside>
