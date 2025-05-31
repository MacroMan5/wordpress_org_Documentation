# Comments – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/comments/](https://developer.wordpress.org/rest-api/reference/comments/)  
**Last Updated:** 2025-05-23T01:01:13.552Z  
**Extracted:** 2025-05-31 16:56:23

---

# Comments – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a comment record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | Unique identifier for the comment.<br><br>JSON data type: integer<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `author` | The ID of the user object, if author was a user.<br><br>JSON data type: integer<br><br>Context: `view`, `edit`, `embed` |
| `author_email` | Email address for the comment author.<br><br>JSON data type: string,  <br>Format: email<br><br>Context: `edit` |
| `author_ip` | IP address for the comment author.<br><br>JSON data type: string,  <br>Format: ip<br><br>Context: `edit` |
| `author_name` | Display name for the comment author.<br><br>JSON data type: string<br><br>Context: `view`, `edit`, `embed` |
| `author_url` | URL for the comment author.<br><br>JSON data type: string,  <br>Format: uri<br><br>Context: `view`, `edit`, `embed` |
| `author_user_agent` | User agent for the comment author.<br><br>JSON data type: string<br><br>Context: `edit` |
| `content` | The content for the comment.<br><br>JSON data type: object<br><br>Context: `view`, `edit`, `embed` |
| `date` | The date the comment was published, in the site's timezone.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Context: `view`, `edit`, `embed` |
| `date_gmt` | The date the comment was published, as GMT.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Context: `view`, `edit` |
| `link` | URL to the comment.<br><br>JSON data type: string,  <br>Format: uri<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `parent` | The ID for the parent of the comment.<br><br>JSON data type: integer<br><br>Context: `view`, `edit`, `embed` |
| `post` | The ID of the associated post object.<br><br>JSON data type: integer<br><br>Context: `view`, `edit` |
| `status` | State of the comment.<br><br>JSON data type: string<br><br>Context: `view`, `edit` |
| `type` | Type of the comment.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `author_avatar_urls` | Avatar URLs for the comment author.<br><br>JSON data type: object<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `meta` | Meta fields.<br><br>JSON data type: object<br><br>Context: `view`, `edit` |

Query this endpoint to retrieve a collection of comments. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](#definition)

`GET /wp/v2/comments`

### [Example Request](#example-request)

`$ curl https://example.com/wp-json/wp/v2/comments`

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |
| `page` | Current page of the collection.<br><br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set.<br><br>Default: `10` |
| `search` | Limit results to those matching a string. |
| `after` | Limit response to comments published after a given ISO8601 compliant date. |
| `author` | Limit result set to comments assigned to specific user IDs. Requires authorization. |
| `author_exclude` | Ensure result set excludes comments assigned to specific user IDs. Requires authorization. |
| `author_email` | Limit result set to that from a specific author email. Requires authorization. |
| `before` | Limit response to comments published before a given ISO8601 compliant date. |
| `exclude` | Ensure result set excludes specific IDs. |
| `include` | Limit result set to specific IDs. |
| `offset` | Offset the result set by a specific number of items. |
| `order` | Order sort attribute ascending or descending.<br><br>Default: `desc`<br><br>One of: `asc`, `desc` |
| `orderby` | Sort collection by comment attribute.<br><br>Default: `date_gmt`<br><br>One of: `date`, `date_gmt`, `id`, `include`, `post`, `parent`, `type` |
| `parent` | Limit result set to comments of specific parent IDs. |
| `parent_exclude` | Ensure result set excludes specific parent IDs. |
| `post` | Limit result set to comments assigned to specific post IDs. |
| `status` | Limit result set to comments assigned a specific status. Requires authorization.<br><br>Default: `approve` |
| `type` | Limit result set to comments assigned a specific type. Requires authorization.<br><br>Default: `comment` |
| `password` | The password for the post if it is password protected. |

### [Arguments](#arguments-2)

|     |     |
| --- | --- |
| `[author](#schema-author)` | The ID of the user object, if author was a user. |
| `[author_email](#schema-author_email)` | Email address for the comment author. |
| `[author_ip](#schema-author_ip)` | IP address for the comment author. |
| `[author_name](#schema-author_name)` | Display name for the comment author. |
| `[author_url](#schema-author_url)` | URL for the comment author. |
| `[author_user_agent](#schema-author_user_agent)` | User agent for the comment author. |
| `[content](#schema-content)` | The content for the comment. |
| `[date](#schema-date)` | The date the comment was published, in the site's timezone. |
| `[date_gmt](#schema-date_gmt)` | The date the comment was published, as GMT. |
| `[parent](#schema-parent)` | The ID for the parent of the comment. |
| `[post](#schema-post)` | The ID of the associated post object. |
| `[status](#schema-status)` | State of the comment. |
| `[meta](#schema-meta)` | Meta fields. |

### [Definition](#definition-2)

`POST /wp/v2/comments`

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/comments/<id>`

Query this endpoint to retrieve a specific comment record.

`$ curl https://example.com/wp-json/wp/v2/comments/<id>`

### [Arguments](#arguments-3)

|     |     |
| --- | --- |
| `id` | Unique identifier for the comment. |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |
| `password` | The password for the parent post of the comment (if the post is password protected). |

### [Arguments](#arguments-4)

|     |     |
| --- | --- |
| `[id](#schema-id)` | Unique identifier for the comment. |
| `[author](#schema-author)` | The ID of the user object, if author was a user. |
| `[author_email](#schema-author_email)` | Email address for the comment author. |
| `[author_ip](#schema-author_ip)` | IP address for the comment author. |
| `[author_name](#schema-author_name)` | Display name for the comment author. |
| `[author_url](#schema-author_url)` | URL for the comment author. |
| `[author_user_agent](#schema-author_user_agent)` | User agent for the comment author. |
| `[content](#schema-content)` | The content for the comment. |
| `[date](#schema-date)` | The date the comment was published, in the site's timezone. |
| `[date_gmt](#schema-date_gmt)` | The date the comment was published, as GMT. |
| `[parent](#schema-parent)` | The ID for the parent of the comment. |
| `[post](#schema-post)` | The ID of the associated post object. |
| `[status](#schema-status)` | State of the comment. |
| `[meta](#schema-meta)` | Meta fields. |

### [Definition](#definition-3)

`POST /wp/v2/comments/<id>`

### [Example Request](#example-request-2)

### [Arguments](#arguments-5)

|     |     |
| --- | --- |
| `id` | Unique identifier for the comment. |
| `force` | Whether to bypass Trash and force deletion. |
| `password` | The password for the parent post of the comment (if the post is password protected). |

### [Definition](#definition-4)

`DELETE /wp/v2/comments/<id>`

### [Example Request](#example-request-3)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/comments/<id>`

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
