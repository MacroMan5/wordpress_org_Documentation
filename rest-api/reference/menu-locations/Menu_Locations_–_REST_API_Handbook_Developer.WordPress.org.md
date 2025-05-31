# Menu Locations – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/menu-locations/](https://developer.wordpress.org/rest-api/reference/menu-locations/)  
**Last Updated:** 2025-05-23T01:01:22.432Z  
**Extracted:** 2025-05-31 16:56:23

---

# Menu Locations – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a menu location record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `name` | The name of the menu location.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `description` | The description of the menu location.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `menu` | The ID of the assigned menu.<br><br>JSON data type: integer<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/menu-locations`

Query this endpoint to retrieve a specific menu location record.

`$ curl https://example.com/wp-json/wp/v2/menu-locations`

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

### [Definition & Example Request](#definition-example-request-2)

`GET /wp/v2/menu-locations/<location>`

Query this endpoint to retrieve a specific menu location record.

`$ curl https://example.com/wp-json/wp/v2/menu-locations/<location>`

### [Arguments](#arguments-2)

|     |     |
| --- | --- |
| `location` | An alphanumeric identifier for the menu location. |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
