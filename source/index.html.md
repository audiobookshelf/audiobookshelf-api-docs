---
title: Audiobookshelf API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - libraries
  - items

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Audiobookshelf API
---

# Introduction

Work in progress

# Authentication

Audiobookshelf uses a users API token as a Bearer token for requests. For GET requests the API token can be passed in as a query string.

You can find your API token by logging into the Audiobookshelf web app as an admin, go to the config -> users page, and click on your account.

API request header for authentication would look like this:

`Authorization: Bearer exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY`

Optionally GET requests can use the API token like this:

`https://abs.yourserver.com/api/items/li_asdfalwkerioa?token=exJhbGciOiJI6IkpXVCJ9.eyJ1c2Vyi5NDEyODc4fQ.ZraBFohS4Tg39NszY`

<aside class="notice">
Your API token will be much longer then the one in the examples.
</aside>

