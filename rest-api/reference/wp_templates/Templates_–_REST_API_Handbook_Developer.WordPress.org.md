# Templates – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/wp_templates/](https://developer.wordpress.org/rest-api/reference/wp_templates/)  
**Last Updated:** 2025-05-23T01:02:04.323Z  
**Extracted:** 2025-05-31 16:56:23

---

# Templates – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a template record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | ID of template.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `slug` | Unique slug identifying the template.<br><br>JSON data type: string<br><br>Context: `embed`, `view`, `edit` |
| `theme` | Theme identifier for the template.<br><br>JSON data type: string<br><br>Context: `embed`, `view`, `edit` |
| `type` | Type of template.<br><br>JSON data type: string<br><br>Context: `embed`, `view`, `edit` |
| `source` | Source of template<br><br>JSON data type: string<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `origin` | Source of a customized template<br><br>JSON data type: string<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `content` | Content of template.<br><br>JSON data type: object or string<br><br>Context: `embed`, `view`, `edit` |
| `title` | Title of template.<br><br>JSON data type: object or string<br><br>Context: `embed`, `view`, `edit` |
| `description` | Description of template.<br><br>JSON data type: string<br><br>Context: `embed`, `view`, `edit` |
| `status` | Status of template.<br><br>JSON data type: string<br><br>Context: `embed`, `view`, `edit`<br><br>One of: `publish`, `future`, `draft`, `pending`, `private` |
| `wp_id` | Post ID.<br><br>JSON data type: integer<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `has_theme_file` | Theme file exists.<br><br>JSON data type: bool<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `author` | The ID for the author of the template.<br><br>JSON data type: integer<br><br>Context: `view`, `edit`, `embed` |
| `modified` | The date the template was last modified, in the site's timezone.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Read only<br><br>Context: `view`, `edit` |
| `is_custom` | Whether a template is a custom template.<br><br>JSON data type: bool<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |

## [Retrieve a Template](#retrieve-a-template)

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/templates`

Query this endpoint to retrieve a specific template record.

`$ curl https://example.com/wp-json/wp/v2/templates`

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |
| `wp_id` | Limit to the specified post id. |
| `area` | Limit to the specified template part area. |
| `post_type` | Post type to get the templates for. |

## [Create a Template](#create-a-template)

### [Arguments](#arguments-2)

|     |     |
| --- | --- |
| `[slug](#schema-slug)` | Unique slug identifying the template.<br><br>Required: 1 |
| `[theme](#schema-theme)` | Theme identifier for the template. |
| `[type](#schema-type)` | Type of template. |
| `[content](#schema-content)` | Content of template. |
| `[title](#schema-title)` | Title of template. |
| `[description](#schema-description)` | Description of template. |
| `[status](#schema-status)` | Status of template.<br><br>Default: `publish`<br><br>One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[author](#schema-author)` | The ID for the author of the template. |

### [Definition](#definition)

`POST /wp/v2/templates`

## [Retrieve a Template](#retrieve-a-template-2)

### [Definition & Example Request](#definition-example-request-2)

`GET /wp/v2/templates/<id>?)[\/\w%-]+)`

Query this endpoint to retrieve a specific template record.

`$ curl https://example.com/wp-json/wp/v2/templates/<id>?)[\/\w%-]+)`

### [Arguments](#arguments-3)

|     |     |
| --- | --- |
| `id` | The id of a template |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

## [Update a Template](#update-a-template)

### [Arguments](#arguments-4)

|     |     |
| --- | --- |
| `[id](#schema-id)` | The id of a template |
| `[slug](#schema-slug)` | Unique slug identifying the template. |
| `[theme](#schema-theme)` | Theme identifier for the template. |
| `[type](#schema-type)` | Type of template. |
| `[content](#schema-content)` | Content of template. |
| `[title](#schema-title)` | Title of template. |
| `[description](#schema-description)` | Description of template. |
| `[status](#schema-status)` | Status of template.  <br>One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[author](#schema-author)` | The ID for the author of the template. |

### [Definition](#definition-2)

`POST /wp/v2/templates/<id>?)[\/\w%-]+)`

### [Example Request](#example-request)

## [Delete a Template](#delete-a-template)

### [Arguments](#arguments-5)

|     |     |
| --- | --- |
| `id` | The id of a template |
| `force` | Whether to bypass Trash and force deletion. |

### [Definition](#definition-3)

`DELETE /wp/v2/templates/<id>?)[\/\w%-]+)`

### [Example Request](#example-request-2)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/templates/<id>?)[\/\w%-]+)`

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
