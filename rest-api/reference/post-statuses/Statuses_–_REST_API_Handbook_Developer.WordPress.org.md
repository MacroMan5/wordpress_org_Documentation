# Statuses – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/post-statuses/](https://developer.wordpress.org/rest-api/reference/post-statuses/)  
**Last Updated:** 2025-05-23T01:01:57.337Z  
**Extracted:** 2025-05-31 16:56:23

---

# Statuses – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a status record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `name` | The title for the status.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `private` | Whether posts with this status should be private.<br><br>JSON data type: boolean<br><br>Read only<br><br>Context: `edit` |
| `protected` | Whether posts with this status should be protected.<br><br>JSON data type: boolean<br><br>Read only<br><br>Context: `edit` |
| `public` | Whether posts of this status should be shown in the front end of the site.<br><br>JSON data type: boolean<br><br>Read only<br><br>Context: `view`, `edit` |
| `queryable` | Whether posts with this status should be publicly-queryable.<br><br>JSON data type: boolean<br><br>Read only<br><br>Context: `view`, `edit` |
| `show_in_list` | Whether to include posts in the edit listing for their post type.<br><br>JSON data type: boolean<br><br>Read only<br><br>Context: `edit` |
| `slug` | An alphanumeric identifier for the status.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `date_floating` | Whether posts of this status may have floating published dates.<br><br>JSON data type: boolean<br><br>Read only<br><br>Context: `view`, `edit` |

## [Retrieve a Status](#retrieve-a-status)

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/statuses`

Query this endpoint to retrieve a specific status record.

`$ curl https://example.com/wp-json/wp/v2/statuses`

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

## [Retrieve a Status](#retrieve-a-status-2)

### [Definition & Example Request](#definition-example-request-2)

`GET /wp/v2/statuses/<status>`

Query this endpoint to retrieve a specific status record.

`$ curl https://example.com/wp-json/wp/v2/statuses/<status>`

### [Arguments](#arguments-2)

|     |     |
| --- | --- |
| `status` | An alphanumeric identifier for the status. |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
