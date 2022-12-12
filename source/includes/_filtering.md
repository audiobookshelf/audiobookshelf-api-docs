# Filtering

Most filters are composed of two parts, a group and a value, put together as `group.value`.

The groups are:

* `genres`
* `tags`
* `series`
* `authors`
* `progress`
* `narrators`
* `missing`
* `languages`
* `tracks`

The `series`, `authors`, `narrators`, `missing`, and `tracks` groups only apply to books.

The available values depend on the group:

* For the `genres`, `tags`, `narrators`, and `languages` groups, the value is what genre, tag, narrator, or language to filter by.
* For the `series` and `authors` groups, the value is the ID of the series or author.
* For the `series` group, the value can also be `no-series`.
* For the `progress` group, the value can be:
  * `finished`
  * `not-started`
  * `not-finished`
  * `in-progress`
* For the `missing` group, the value can be:
  * `asin`
  * `isbn`
  * `subtitle`
  * `authors`
  * `publishedYear`
  * `series`
  * `description`
  * `genres`
  * `tags`
  * `narrators`
  * `publisher`
  * `language`
* For the `tracks` group, the value can be:
  * `single`
  * `multi`

All values must be first Base64 encoded and then URL encoded.

Other filters are `issues` and `feed-open`.

Examples:

* To filter for the Sci Fi genre:
  * `Sci Fi` is Base64 encoded as `U2NpIEZp` 
  * Already URL encoded.
  * Then use `filter=genres.U2NpIEZp`.
* To filter for the author Terry Goodkind who has the ID of aut_z3leimgybl7uf3y4ab:
  * `aut_z3leimgybl7uf3y4ab` is Base64 encoded as `YXV0X3ozbGVpbWd5Ymw3dWYzeTRhYg==`.
  * `YXV0X3ozbGVpbWd5Ymw3dWYzeTRhYg==` is URL encoded as `YXV0X3ozbGVpbWd5Ymw3dWYzeTRhYg%3D%3D`.
  * Then use `filter=authors.YXV0X3ozbGVpbWd5Ymw3dWYzeTRhYg%3D%3D`.
* To filter for in progress items:
  * `in-progress` is Base64 encoded as `aW4tcHJvZ3Jlc3M=`.
  * `aW4tcHJvZ3Jlc3M=` is URL encoded as `aW4tcHJvZ3Jlc3M%3D`.
  * Then use `filter=progress.aW4tcHJvZ3Jlc3M%3D`.
* To filter for items with their RSS feed open:
  * Use `filter=feed-open`.
