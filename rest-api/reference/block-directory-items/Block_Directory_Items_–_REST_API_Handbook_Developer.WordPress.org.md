# Block Directory Items – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/block-directory-items/](https://developer.wordpress.org/rest-api/reference/block-directory-items/)  
**Last Updated:** 2025-05-23T01:02:47.820Z  
**Extracted:** 2025-05-31 16:56:23

---

# Block Directory Items – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a block directory item record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `name` | The block name, in namespace/block-name format.<br><br>JSON data type: string<br><br>Context: `view` |
| `title` | The block title, in human readable format.<br><br>JSON data type: string<br><br>Context: `view` |
| `description` | A short description of the block, in human readable format.<br><br>JSON data type: string<br><br>Context: `view` |
| `id` | The block slug.<br><br>JSON data type: string<br><br>Context: `view` |
| `rating` | The star rating of the block.<br><br>JSON data type: number<br><br>Context: `view` |
| `rating_count` | The number of ratings.<br><br>JSON data type: integer<br><br>Context: `view` |
| `active_installs` | The number sites that have activated this block.<br><br>JSON data type: integer<br><br>Context: `view` |
| `author_block_rating` | The average rating of blocks published by the same author.<br><br>JSON data type: number<br><br>Context: `view` |
| `author_block_count` | The number of blocks published by the same author.<br><br>JSON data type: integer<br><br>Context: `view` |
| `author` | The WordPress.org username of the block author.<br><br>JSON data type: string<br><br>Context: `view` |
| `icon` | The block icon.<br><br>JSON data type: string,  <br>Format: uri<br><br>Context: `view` |
| `last_updated` | The date when the block was last updated.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Context: `view` |
| `humanized_updated` | The date when the block was last updated, in fuzzy human readable format.<br><br>JSON data type: string<br><br>Context: `view` |

## [List Block Directory Items](#list-block-directory-items)

Query this endpoint to retrieve a collection of block directory items. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](#definition)

`GET /wp/v2/block-directory/search`

### [Example Request](#example-request)

`$ curl https://example.com/wp-json/wp/v2/block-directory/search`

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view` |
| `page` | Current page of the collection.<br><br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set.<br><br>Default: `10` |
| `term` | Limit result set to blocks matching the search term.<br><br>Required: 1 |

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
