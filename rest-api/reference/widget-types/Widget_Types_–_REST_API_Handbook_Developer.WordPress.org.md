# Widget Types – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/widget-types/](https://developer.wordpress.org/rest-api/reference/widget-types/)  
**Last Updated:** 2025-05-23T01:13:12.835Z  
**Extracted:** 2025-05-31 16:56:23

---

# Widget Types – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a widget type record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | Unique slug identifying the widget type.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `name` | Human-readable name identifying the widget type.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `description` | Description of the widget.<br><br>JSON data type: string<br><br>Context: `view`, `edit`, `embed` |
| `is_multi` | Whether the widget supports multiple instances<br><br>JSON data type: boolean<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `classname` | Class name<br><br>JSON data type: string<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/widget-types`

Query this endpoint to retrieve a specific widget type record.

`$ curl https://example.com/wp-json/wp/v2/widget-types`

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

### [Definition & Example Request](#definition-example-request-2)

`GET /wp/v2/widget-types/<id>`

Query this endpoint to retrieve a specific widget type record.

`$ curl https://example.com/wp-json/wp/v2/widget-types/<id>`

### [Arguments](#arguments-2)

|     |     |
| --- | --- |
| `id` | The widget type id. |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
