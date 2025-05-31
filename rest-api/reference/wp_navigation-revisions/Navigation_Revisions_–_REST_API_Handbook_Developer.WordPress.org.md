# Navigation Revisions – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/](https://developer.wordpress.org/rest-api/reference/wp_navigation-revisions/)  
**Last Updated:** 2025-05-23T01:01:22.750Z  
**Extracted:** 2025-05-31 16:56:23

---

# Navigation Revisions – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a navigation revision record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `author` | The ID for the author of the revision.<br><br>JSON data type: integer<br><br>Context: `view`, `edit`, `embed` |
| `date` | The date the revision was published, in the site's timezone.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Context: `view`, `edit`, `embed` |
| `date_gmt` | The date the revision was published, as GMT.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Context: `view`, `edit` |
| `guid` | The globally unique identifier for the post.<br><br>JSON data type: object<br><br>Read only<br><br>Context: `view`, `edit` |
| `id` | Unique identifier for the revision.<br><br>JSON data type: integer<br><br>Context: `view`, `edit`, `embed` |
| `modified` | The date the revision was last modified, in the site's timezone.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Context: `view`, `edit` |
| `modified_gmt` | The date the revision was last modified, as GMT.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Context: `view`, `edit` |
| `parent` | The ID for the parent of the revision.<br><br>JSON data type: integer<br><br>Context: `view`, `edit`, `embed` |
| `slug` | An alphanumeric identifier for the revision unique to its type.<br><br>JSON data type: string<br><br>Context: `view`, `edit`, `embed` |
| `title` | The title for the post.<br><br>JSON data type: object<br><br>Context: `view`, `edit`, `embed` |
| `content` | The content for the post.<br><br>JSON data type: object<br><br>Context: `view`, `edit`, `embed` |

## [List Navigation Revisions](#list-navigation-revisions)

Query this endpoint to retrieve a collection of navigation revisions. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](#definition)

`GET /wp/v2/navigation/<parent>/revisions`

### [Example Request](#example-request)

`$ curl https://example.com/wp-json/wp/v2/navigation/<parent>/revisions`

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

## [Retrieve a Navigation Revision](#retrieve-a-navigation-revision)

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/navigation/<parent>/revisions/<id>`

Query this endpoint to retrieve a specific navigation revision record.

`$ curl https://example.com/wp-json/wp/v2/navigation/<parent>/revisions/<id>`

### [Arguments](#arguments-2)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the revision. |
| `id` | Unique identifier for the revision. |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

## [Delete a Navigation Revision](#delete-a-navigation-revision)

### [Arguments](#arguments-3)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the revision. |
| `id` | Unique identifier for the revision. |
| `force` | Required to be true, as revisions do not support trashing. |

### [Definition](#definition-2)

`DELETE /wp/v2/navigation/<parent>/revisions/<id>`

### [Example Request](#example-request-2)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/navigation/<parent>/revisions/<id>`

## [Retrieve a Navigation Revision](#retrieve-a-navigation-revision-2)

### [Definition & Example Request](#definition-example-request-2)

`GET /wp/v2/navigation/<id>/autosaves`

Query this endpoint to retrieve a specific navigation revision record.

`$ curl https://example.com/wp-json/wp/v2/navigation/<id>/autosaves`

### [Arguments](#arguments-4)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the autosave. |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

## [Create a Navigation Revision](#create-a-navigation-revision)

### [Arguments](#arguments-5)

|     |     |
| --- | --- |
| `[parent](#schema-parent)` | The ID for the parent of the autosave. |
| `[date](#schema-date)` | The date the post was published, in the site's timezone. |
| `[date_gmt](#schema-date_gmt)` | The date the post was published, as GMT. |
| `[slug](#schema-slug)` | An alphanumeric identifier for the post unique to its type. |
| `[status](#schema-status)` | A named status for the post.  <br>One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[password](#schema-password)` | A password to protect access to the content and excerpt. |
| `[title](#schema-title)` | The title for the post. |
| `[content](#schema-content)` | The content for the post. |
| `[template](#schema-template)` | The theme file to use to display the post. |

### [Definition](#definition-3)

`POST /wp/v2/navigation/<id>/autosaves`

## [Retrieve a Navigation Revision](#retrieve-a-navigation-revision-3)

### [Definition & Example Request](#definition-example-request-3)

`GET /wp/v2/navigation/<parent>/autosaves/<id>`

Query this endpoint to retrieve a specific navigation revision record.

`$ curl https://example.com/wp-json/wp/v2/navigation/<parent>/autosaves/<id>`

### [Arguments](#arguments-6)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the autosave. |
| `id` | The ID for the autosave. |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
