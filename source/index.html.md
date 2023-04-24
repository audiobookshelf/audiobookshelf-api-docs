---
title: Audiobookshelf API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://github.com/advplyr/audiobookshelf-slate'>View Doc Source</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - authors
  - backups
  - cache
  - collections
  - filesystem
  - filtering
  - items
  - libraries
  - me
  - metadata_providers
  - misc
  - notifications
  - playlists
  - podcasts
  - rss_feeds
  - schemas
  - search
  - series
  - server
  - sessions
  - socket
  - tools
  - users

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Audiobookshelf API
---

# Introduction

Audiobookshelf API and this documentation is a work in progress.

Contributions to this documentation are welcome! [View API docs GitHub repo](https://github.com/advplyr/audiobookshelf-slate)

If you are a .NET developer we could use your help with a Windows installer for audiobookshelf server.

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

