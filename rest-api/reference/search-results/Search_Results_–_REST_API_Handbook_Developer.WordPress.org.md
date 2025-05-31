# Search Results – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/search-results/](https://developer.wordpress.org/rest-api/reference/search-results/)  
**Last Updated:** 2025-05-23T01:01:49.835Z  
**Extracted:** 2025-05-31 16:56:23

---

# Search Results – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a search result record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | Unique identifier for the object.<br><br>JSON data type: integer or string<br><br>Read only<br><br>Context: `view`, `embed` |
| `title` | The title for the object.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `embed` |
| `url` | URL to the object.<br><br>JSON data type: string,  <br>Format: uri<br><br>Read only<br><br>Context: `view`, `embed` |
| `type` | Object type.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `embed`<br><br>One of: `post`, `term`, `post-format` |
| `subtype` | Object subtype.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `embed`<br><br>One of: `post`, `page`, `category`, `post_tag` |

## [List Search Results](#list-search-results)

Query this endpoint to retrieve a collection of search results. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](#definition)

`GET /wp/v2/search`

### [Example Request](#example-request)

`$ curl https://example.com/wp-json/wp/v2/search`

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed` |
| `page` | Current page of the collection.<br><br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set.<br><br>Default: `10` |
| `search` | Limit results to those matching a string. |
| `type` | Limit results to items of an object type.<br><br>Default: `post`<br><br>One of: `post`, `term`, `post-format` |
| `subtype` | Limit results to items of one or more object subtypes.<br><br>Default: `any` |
| `exclude` | Ensure result set excludes specific IDs. |
| `include` | Limit result set to specific IDs. |

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
