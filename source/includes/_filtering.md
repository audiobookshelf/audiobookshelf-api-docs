# Filtering

Most filters are composed of two parts, a group and a value, put together as `group.value`. The groups are: genres, tags, series, authors, progress, narrators, missing, and languages.

* For the genres, tags, narrators, and languages groups, the value is what genre, tag, narrator, or language to filter by.
* For the series and authors groups, the value is the ID of the series or author.
* For the series group, the value can also be No Series.
* For the progress group, the value can be:
  * Finished
  * Not Started
  * Not Finished
  * In Progress
* For the missing group, the value can be:
  * ASIN
  * ISBN
  * Subtitle
  * Author
  * Publisher Year
  * Series
  * Description
  * Genres
  * Tags
  * Narrator
  * Publisher
  * Language

All values must be first Base64 encoded and then URL encoded.

Other filters are issues and feed-open.

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
  * `In Progress` is Base64 encoded as `SW4gUHJvZ3Jlc3M=`.
  * `SW4gUHJvZ3Jlc3M=` is URL encoded as `SW4gUHJvZ3Jlc3M%3D`.
  * Then use `filter=progress.SW4gUHJvZ3Jlc3M%3D`.
* To filter for items with their RSS feed open:
  * Use `filter=feed-open`.
