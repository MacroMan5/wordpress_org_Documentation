# Template_Part Revisions – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/](https://developer.wordpress.org/rest-api/reference/wp_template_part-revisions/)  
**Last Updated:** 2025-05-23T01:03:14.130Z  
**Extracted:** 2025-05-31 16:56:23

---

# Template\_Part Revisions – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a template\_part revision record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `author` | The ID for the author of the revision.<br><br>JSON data type: integer<br><br>Context: `view`, `edit`, `embed` |
| `date` | The date the revision was published, in the site's timezone.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Context: `view`, `edit`, `embed` |
| `date_gmt` | The date the revision was published, as GMT.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Context: `view`, `edit` |
| `guid` | GUID for the revision, as it exists in the database.<br><br>JSON data type: string<br><br>Context: `view`, `edit` |
| `id` | Unique identifier for the revision.<br><br>JSON data type: integer<br><br>Context: `view`, `edit`, `embed` |
| `modified` | The date the revision was last modified, in the site's timezone.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Context: `view`, `edit` |
| `modified_gmt` | The date the revision was last modified, as GMT.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Context: `view`, `edit` |
| `parent` | The ID for the parent of the revision.<br><br>JSON data type: integer<br><br>Context: `view`, `edit`, `embed` |
| `slug` | An alphanumeric identifier for the revision unique to its type.<br><br>JSON data type: string<br><br>Context: `view`, `edit`, `embed` |
| `title` | Title of template.<br><br>JSON data type: object or string<br><br>Context: `embed`, `view`, `edit` |
| `content` | Content of template.<br><br>JSON data type: object or string<br><br>Context: `embed`, `view`, `edit` |

## [List Template\_Part Revisions](#list-template_part-revisions)

Query this endpoint to retrieve a collection of template\_part revisions. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](#definition)

`GET /wp/v2/template-parts/<parent>/revisions`

### [Example Request](#example-request)

`$ curl https://example.com/wp-json/wp/v2/template-parts/<parent>/revisions`

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the revision. |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |
| `page` | Current page of the collection.<br><br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set. |
| `search` | Limit results to those matching a string. |
| `exclude` | Ensure result set excludes specific IDs. |
| `include` | Limit result set to specific IDs. |
| `offset` | Offset the result set by a specific number of items. |
| `order` | Order sort attribute ascending or descending.<br><br>Default: `desc`<br><br>One of: `asc`, `desc` |
| `orderby` | Sort collection by object attribute.<br><br>Default: `date`<br><br>One of: `date`, `id`, `include`, `relevance`, `slug`, `include_slugs`, `title` |

## [Retrieve a Template\_Part Revision](#retrieve-a-template_part-revision)

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/template-parts/<parent>/revisions/<id>`

Query this endpoint to retrieve a specific template\_part revision record.

`$ curl https://example.com/wp-json/wp/v2/template-parts/<parent>/revisions/<id>`

### [Arguments](#arguments-2)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the revision. |
| `id` | Unique identifier for the revision. |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

## [Delete a Template\_Part Revision](#delete-a-template_part-revision)

### [Arguments](#arguments-3)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the revision. |
| `id` | Unique identifier for the revision. |
| `force` | Required to be true, as revisions do not support trashing. |

### [Definition](#definition-2)

`DELETE /wp/v2/template-parts/<parent>/revisions/<id>`

### [Example Request](#example-request-2)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/template-parts/<parent>/revisions/<id>`

## [Retrieve a Template\_Part Revision](#retrieve-a-template_part-revision-2)

### [Definition & Example Request](#definition-example-request-2)

`GET /wp/v2/template-parts/<id>/autosaves`

Query this endpoint to retrieve a specific template\_part revision record.

`$ curl https://example.com/wp-json/wp/v2/template-parts/<id>/autosaves`

### [Arguments](#arguments-4)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the autosave. |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

## [Create a Template\_Part Revision](#create-a-template_part-revision)

### [Arguments](#arguments-5)

|     |     |
| --- | --- |
| `[parent](#schema-parent)` | The ID for the parent of the autosave. |
| `[slug](#schema-slug)` | Unique slug identifying the template. |
| `[theme](#schema-theme)` | Theme identifier for the template. |
| `[type](#schema-type)` | Type of template. |
| `[content](#schema-content)` | Content of template. |
| `[title](#schema-title)` | Title of template. |
| `[description](#schema-description)` | Description of template. |
| `[status](#schema-status)` | Status of template.  <br>One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[author](#schema-author)` | The ID for the author of the template. |
| `[area](#schema-area)` | Where the template part is intended for use (header, footer, etc.) |

### [Definition](#definition-3)

`POST /wp/v2/template-parts/<id>/autosaves`

## [Retrieve a Template\_Part Revision](#retrieve-a-template_part-revision-3)

### [Definition & Example Request](#definition-example-request-3)

`GET /wp/v2/template-parts/<parent>/autosaves/<id>`

Query this endpoint to retrieve a specific template\_part revision record.

`$ curl https://example.com/wp-json/wp/v2/template-parts/<parent>/autosaves/<id>`

### [Arguments](#arguments-6)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the autosave. |
| `id` | The ID for the autosave. |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
