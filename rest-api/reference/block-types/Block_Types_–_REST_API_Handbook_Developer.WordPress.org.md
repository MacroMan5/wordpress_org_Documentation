# Block Types – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/block-types/](https://developer.wordpress.org/rest-api/reference/block-types/)  
**Last Updated:** 2025-05-23T01:03:01.852Z  
**Extracted:** 2025-05-31 16:56:23

---

# Block Types – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a block type record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `api_version` | Version of block API.<br><br>JSON data type: integer<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `title` | Title of block type.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `name` | Unique name identifying the block type.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `description` | Description of block type.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `icon` | Icon of block type.<br><br>JSON data type: string or null<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `attributes` | Block attributes.<br><br>JSON data type: object or null<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `provides_context` | Context provided by blocks of this type.<br><br>JSON data type: object<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `uses_context` | Context values inherited by blocks of this type.<br><br>JSON data type: array<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `selectors` | Custom CSS selectors.<br><br>JSON data type: object<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `supports` | Block supports.<br><br>JSON data type: object<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `category` | Block category.<br><br>JSON data type: string or null<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `is_dynamic` | Is the block dynamically rendered.<br><br>JSON data type: boolean<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `editor_script_handles` | Editor script handles.<br><br>JSON data type: array<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `script_handles` | Public facing and editor script handles.<br><br>JSON data type: array<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `view_script_handles` | Public facing script handles.<br><br>JSON data type: array<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `editor_style_handles` | Editor style handles.<br><br>JSON data type: array<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `style_handles` | Public facing and editor style handles.<br><br>JSON data type: array<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `styles` | Block style variations.<br><br>JSON data type: array<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `variations` | Block variations.<br><br>JSON data type: array<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `textdomain` | Public text domain.<br><br>JSON data type: string or null<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `parent` | Parent blocks.<br><br>JSON data type: array or null<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `ancestor` | Ancestor blocks.<br><br>JSON data type: array or null<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `keywords` | Block keywords.<br><br>JSON data type: array<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `example` | Block example.<br><br>JSON data type: object or null<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `editor_script` | Editor script handle. DEPRECATED: Use \`editor\_script\_handles\` instead.<br><br>JSON data type: string or null<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `script` | Public facing and editor script handle. DEPRECATED: Use \`script\_handles\` instead.<br><br>JSON data type: string or null<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `view_script` | Public facing script handle. DEPRECATED: Use \`view\_script\_handles\` instead.<br><br>JSON data type: string or null<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `editor_style` | Editor style handle. DEPRECATED: Use \`editor\_style\_handles\` instead.<br><br>JSON data type: string or null<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `style` | Public facing and editor style handle. DEPRECATED: Use \`style\_handles\` instead.<br><br>JSON data type: string or null<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |

## [Retrieve a Block Type](#retrieve-a-block-type)

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/block-types`

Query this endpoint to retrieve a specific block type record.

`$ curl https://example.com/wp-json/wp/v2/block-types`

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |
| `namespace` | Block namespace. |

## [Retrieve a Block Type](#retrieve-a-block-type-2)

### [Definition & Example Request](#definition-example-request-2)

`GET /wp/v2/block-types/<namespace>`

Query this endpoint to retrieve a specific block type record.

`$ curl https://example.com/wp-json/wp/v2/block-types/<namespace>`

### [Arguments](#arguments-2)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |
| `namespace` | Block namespace. |

## [Retrieve a Block Type](#retrieve-a-block-type-3)

### [Definition & Example Request](#definition-example-request-3)

`GET /wp/v2/block-types/<namespace>/<name>`

Query this endpoint to retrieve a specific block type record.

`$ curl https://example.com/wp-json/wp/v2/block-types/<namespace>/<name>`

### [Arguments](#arguments-3)

|     |     |
| --- | --- |
| `name` | Block name. |
| `namespace` | Block namespace. |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
