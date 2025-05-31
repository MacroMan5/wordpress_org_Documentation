# Plugins – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/plugins/](https://developer.wordpress.org/rest-api/reference/plugins/)  
**Last Updated:** 2025-05-23T01:01:42.534Z  
**Extracted:** 2025-05-31 16:56:23

---

# Plugins – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a plugin record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `plugin` | The plugin file.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `status` | The plugin activation status.<br><br>JSON data type: string<br><br>Context: `view`, `edit`, `embed`<br><br>One of: `inactive`, `active` |
| `name` | The plugin name.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `plugin_uri` | The plugin's website address.<br><br>JSON data type: string,  <br>Format: uri<br><br>Read only<br><br>Context: `view`, `edit` |
| `author` | The plugin author.<br><br>JSON data type: object<br><br>Read only<br><br>Context: `view`, `edit` |
| `author_uri` | Plugin author's website address.<br><br>JSON data type: string,  <br>Format: uri<br><br>Read only<br><br>Context: `view`, `edit` |
| `description` | The plugin description.<br><br>JSON data type: object<br><br>Read only<br><br>Context: `view`, `edit` |
| `version` | The plugin version number.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `edit` |
| `network_only` | Whether the plugin can only be activated network-wide.<br><br>JSON data type: boolean<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `requires_wp` | Minimum required version of WordPress.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `requires_php` | Minimum required version of PHP.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `textdomain` | The plugin's text domain.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `edit` |

## [Retrieve a Plugin](#retrieve-a-plugin)

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/plugins`

Query this endpoint to retrieve a specific plugin record.

`$ curl https://example.com/wp-json/wp/v2/plugins`

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |
| `search` | Limit results to those matching a string. |
| `status` | Limits results to plugins with the given status. |

## [Create a Plugin](#create-a-plugin)

### [Arguments](#arguments-2)

|     |     |
| --- | --- |
| `[slug](#schema-slug)` | WordPress.org plugin directory slug.<br><br>Required: 1 |
| `[status](#schema-status)` | The plugin activation status.<br><br>Default: `inactive`<br><br>One of: `inactive`, `active` |

### [Definition](#definition)

`POST /wp/v2/plugins`

## [Retrieve a Plugin](#retrieve-a-plugin-2)

### [Definition & Example Request](#definition-example-request-2)

`GET /wp/v2/plugins/<plugin>?)`

Query this endpoint to retrieve a specific plugin record.

`$ curl https://example.com/wp-json/wp/v2/plugins/<plugin>?)`

### [Arguments](#arguments-3)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |
| `plugin` |     |

## [Update a Plugin](#update-a-plugin)

### [Arguments](#arguments-4)

|     |     |
| --- | --- |
| `[context](#schema-context)` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |
| `[plugin](#schema-plugin)` |     |
| `[status](#schema-status)` | The plugin activation status.  <br>One of: `inactive`, `active` |

### [Definition](#definition-2)

`POST /wp/v2/plugins/<plugin>?)`

### [Example Request](#example-request)

## [Delete a Plugin](#delete-a-plugin)

### [Arguments](#arguments-5)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |
| `plugin` |     |

### [Definition](#definition-3)

`DELETE /wp/v2/plugins/<plugin>?)`

### [Example Request](#example-request-2)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/plugins/<plugin>?)`

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
