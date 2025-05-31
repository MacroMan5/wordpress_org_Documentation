# Widgets – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/widgets/](https://developer.wordpress.org/rest-api/reference/widgets/)  
**Last Updated:** 2025-05-23T01:13:07.849Z  
**Extracted:** 2025-05-31 16:56:23

---

# Widgets – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a widget record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | Unique identifier for the widget.<br><br>JSON data type: string<br><br>Context: `view`, `edit`, `embed` |
| `id_base` | The type of the widget. Corresponds to ID in widget-types endpoint.<br><br>JSON data type: string<br><br>Context: `view`, `edit`, `embed` |
| `sidebar` | The sidebar the widget belongs to.<br><br>JSON data type: string<br><br>Context: `view`, `edit`, `embed` |
| `rendered` | HTML representation of the widget.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `rendered_form` | HTML representation of the widget admin form.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `edit` |
| `instance` | Instance settings of the widget, if supported.<br><br>JSON data type: object<br><br>Context: `edit` |
| `form_data` | URL-encoded form data from the widget admin form. Used to update a widget that does not support instance. Write only.<br><br>JSON data type: string<br><br>Context: |

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/widgets`

Query this endpoint to retrieve a specific widget record.

`$ curl https://example.com/wp-json/wp/v2/widgets`

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |
| `sidebar` | The sidebar to return widgets for. |

### [Arguments](#arguments-2)

|     |     |
| --- | --- |
| `[id](#schema-id)` | Unique identifier for the widget. |
| `[id_base](#schema-id_base)` | The type of the widget. Corresponds to ID in widget-types endpoint. |
| `[sidebar](#schema-sidebar)` | The sidebar the widget belongs to.<br><br>Required: 1<br><br>Default: `wp_inactive_widgets` |
| `[instance](#schema-instance)` | Instance settings of the widget, if supported. |
| `[form_data](#schema-form_data)` | URL-encoded form data from the widget admin form. Used to update a widget that does not support instance. Write only. |

### [Definition](#definition)

`POST /wp/v2/widgets`

### [Definition & Example Request](#definition-example-request-2)

`GET /wp/v2/widgets/<id>`

Query this endpoint to retrieve a specific widget record.

`$ curl https://example.com/wp-json/wp/v2/widgets/<id>`

### [Arguments](#arguments-3)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

### [Arguments](#arguments-4)

|     |     |
| --- | --- |
| `[id](#schema-id)` | Unique identifier for the widget. |
| `[id_base](#schema-id_base)` | The type of the widget. Corresponds to ID in widget-types endpoint. |
| `[sidebar](#schema-sidebar)` | The sidebar the widget belongs to. |
| `[instance](#schema-instance)` | Instance settings of the widget, if supported. |
| `[form_data](#schema-form_data)` | URL-encoded form data from the widget admin form. Used to update a widget that does not support instance. Write only. |

### [Definition](#definition-2)

`POST /wp/v2/widgets/<id>`

### [Example Request](#example-request)

### [Arguments](#arguments-5)

|     |     |
| --- | --- |
| `force` | Whether to force removal of the widget, or move it to the inactive sidebar. |

### [Definition](#definition-3)

`DELETE /wp/v2/widgets/<id>`

### [Example Request](#example-request-2)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/widgets/<id>`

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
