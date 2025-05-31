# Global_Styles – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/wp_global_styles/](https://developer.wordpress.org/rest-api/reference/wp_global_styles/)  
**Last Updated:** 2025-05-23T01:01:15.450Z  
**Extracted:** 2025-05-31 16:56:23

---

# Global\_Styles – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a global\_styles record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | ID of global styles config.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `styles` | Global styles.<br><br>JSON data type: object<br><br>Context: `view`, `edit` |
| `settings` | Global settings.<br><br>JSON data type: object<br><br>Context: `view`, `edit` |
| `title` | Title of the global styles variation.<br><br>JSON data type: object or string<br><br>Context: `embed`, `view`, `edit` |

## [Retrieve a Global\_Styles](#retrieve-a-global_styles)

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/global-styles/<id>`

Query this endpoint to retrieve a specific global\_styles record.

`$ curl https://example.com/wp-json/wp/v2/global-styles/<id>`

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `id` | The id of a template |

## [Update a Global\_Styles](#update-a-global_styles)

### [Arguments](#arguments-2)

|     |     |
| --- | --- |
| `[styles](#schema-styles)` | Global styles. |
| `[settings](#schema-settings)` | Global settings. |
| `[title](#schema-title)` | Title of the global styles variation. |

### [Definition](#definition)

`POST /wp/v2/global-styles/<id>`

### [Example Request](#example-request)

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
