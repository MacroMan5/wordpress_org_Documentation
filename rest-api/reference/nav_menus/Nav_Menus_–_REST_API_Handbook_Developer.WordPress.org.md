# Nav_Menus – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/nav_menus/](https://developer.wordpress.org/rest-api/reference/nav_menus/)  
**Last Updated:** 2025-05-23T01:01:28.622Z  
**Extracted:** 2025-05-31 16:56:23

---

# Nav\_Menus – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a nav\_menu record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | Unique identifier for the term.<br><br>JSON data type: integer<br><br>Read only<br><br>Context: `view`, `embed`, `edit` |
| `description` | HTML description of the term.<br><br>JSON data type: string<br><br>Context: `view`, `edit` |
| `name` | HTML title for the term.<br><br>JSON data type: string<br><br>Context: `view`, `embed`, `edit` |
| `slug` | An alphanumeric identifier for the term unique to its type.<br><br>JSON data type: string<br><br>Context: `view`, `embed`, `edit` |
| `meta` | Meta fields.<br><br>JSON data type: object<br><br>Context: `view`, `edit` |
| `locations` | The locations assigned to the menu.<br><br>JSON data type: array<br><br>Context: `view`, `edit` |
| `auto_add` | Whether to automatically add top level pages to this menu.<br><br>JSON data type: boolean<br><br>Context: `view`, `edit` |

Query this endpoint to retrieve a collection of nav\_menus. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](#definition)

`GET /wp/v2/menus`

### [Example Request](#example-request)

`$ curl https://example.com/wp-json/wp/v2/menus`

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |
| `page` | Current page of the collection.<br><br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set.<br><br>Default: `10` |
| `search` | Limit results to those matching a string. |
| `exclude` | Ensure result set excludes specific IDs. |
| `include` | Limit result set to specific IDs. |
| `offset` | Offset the result set by a specific number of items. |
| `order` | Order sort attribute ascending or descending.<br><br>Default: `asc`<br><br>One of: `asc`, `desc` |
| `orderby` | Sort collection by term attribute.<br><br>Default: `name`<br><br>One of: `id`, `include`, `name`, `slug`, `include_slugs`, `term_group`, `description`, `count` |
| `hide_empty` | Whether to hide terms not assigned to any posts. |
| `post` | Limit result set to terms assigned to a specific post. |
| `slug` | Limit result set to terms with one or more specific slugs. |

### [Arguments](#arguments-2)

|     |     |
| --- | --- |
| `[description](#schema-description)` | HTML description of the term. |
| `[name](#schema-name)` | HTML title for the term.<br><br>Required: 1 |
| `[slug](#schema-slug)` | An alphanumeric identifier for the term unique to its type. |
| `[meta](#schema-meta)` | Meta fields. |
| `[locations](#schema-locations)` | The locations assigned to the menu. |
| `[auto_add](#schema-auto_add)` | Whether to automatically add top level pages to this menu. |

### [Definition](#definition-2)

`POST /wp/v2/menus`

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/menus/<id>`

Query this endpoint to retrieve a specific nav\_menu record.

`$ curl https://example.com/wp-json/wp/v2/menus/<id>`

### [Arguments](#arguments-3)

|     |     |
| --- | --- |
| `id` | Unique identifier for the term. |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

### [Arguments](#arguments-4)

|     |     |
| --- | --- |
| `[id](#schema-id)` | Unique identifier for the term. |
| `[description](#schema-description)` | HTML description of the term. |
| `[name](#schema-name)` | HTML title for the term. |
| `[slug](#schema-slug)` | An alphanumeric identifier for the term unique to its type. |
| `[meta](#schema-meta)` | Meta fields. |
| `[locations](#schema-locations)` | The locations assigned to the menu. |
| `[auto_add](#schema-auto_add)` | Whether to automatically add top level pages to this menu. |

### [Definition](#definition-3)

`POST /wp/v2/menus/<id>`

### [Example Request](#example-request-2)

### [Arguments](#arguments-5)

|     |     |
| --- | --- |
| `id` | Unique identifier for the term. |
| `force` | Required to be true, as terms do not support trashing. |

### [Definition](#definition-4)

`DELETE /wp/v2/menus/<id>`

### [Example Request](#example-request-3)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/menus/<id>`

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
