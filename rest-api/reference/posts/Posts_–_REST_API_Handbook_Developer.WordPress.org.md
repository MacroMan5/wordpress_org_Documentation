# Posts – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/posts/](https://developer.wordpress.org/rest-api/reference/posts/)  
**Last Updated:** 2025-05-23T01:01:43.350Z  
**Extracted:** 2025-05-31 16:56:23

---

# Posts – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a post record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `date` | The date the post was published, in the site's timezone.<br><br>JSON data type: string or null,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Context: `view`, `edit`, `embed` |
| `date_gmt` | The date the post was published, as GMT.<br><br>JSON data type: string or null,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Context: `view`, `edit` |
| `guid` | The globally unique identifier for the post.<br><br>JSON data type: object<br><br>Read only<br><br>Context: `view`, `edit` |
| `id` | Unique identifier for the post.<br><br>JSON data type: integer<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `link` | URL to the post.<br><br>JSON data type: string,  <br>Format: uri<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `modified` | The date the post was last modified, in the site's timezone.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Read only<br><br>Context: `view`, `edit` |
| `modified_gmt` | The date the post was last modified, as GMT.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Read only<br><br>Context: `view`, `edit` |
| `slug` | An alphanumeric identifier for the post unique to its type.<br><br>JSON data type: string<br><br>Context: `view`, `edit`, `embed` |
| `status` | A named status for the post.<br><br>JSON data type: string<br><br>Context: `view`, `edit`<br><br>One of: `publish`, `future`, `draft`, `pending`, `private` |
| `type` | Type of post.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `password` | A password to protect access to the content and excerpt.<br><br>JSON data type: string<br><br>Context: `edit` |
| `permalink_template` | Permalink template for the post.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `edit` |
| `generated_slug` | Slug automatically generated from the post title.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `edit` |
| `title` | The title for the post.<br><br>JSON data type: object<br><br>Context: `view`, `edit`, `embed` |
| `content` | The content for the post.<br><br>JSON data type: object<br><br>Context: `view`, `edit` |
| `author` | The ID for the author of the post.<br><br>JSON data type: integer<br><br>Context: `view`, `edit`, `embed` |
| `excerpt` | The excerpt for the post.<br><br>JSON data type: object<br><br>Context: `view`, `edit`, `embed` |
| `featured_media` | The ID of the featured media for the post.<br><br>JSON data type: integer<br><br>Context: `view`, `edit`, `embed` |
| `comment_status` | Whether or not comments are open on the post.<br><br>JSON data type: string<br><br>Context: `view`, `edit`<br><br>One of: `open`, `closed` |
| `ping_status` | Whether or not the post can be pinged.<br><br>JSON data type: string<br><br>Context: `view`, `edit`<br><br>One of: `open`, `closed` |
| `format` | The format for the post.<br><br>JSON data type: string<br><br>Context: `view`, `edit`<br><br>One of: `standard`, `aside`, `chat`, `gallery`, `link`, `image`, `quote`, `status`, `video`, `audio` |
| `meta` | Meta fields.<br><br>JSON data type: object<br><br>Context: `view`, `edit` |
| `sticky` | Whether or not the post should be treated as sticky.<br><br>JSON data type: boolean<br><br>Context: `view`, `edit` |
| `template` | The theme file to use to display the post.<br><br>JSON data type: string<br><br>Context: `view`, `edit` |
| `categories` | The terms assigned to the post in the category taxonomy.<br><br>JSON data type: array<br><br>Context: `view`, `edit` |
| `tags` | The terms assigned to the post in the post\_tag taxonomy.<br><br>JSON data type: array<br><br>Context: `view`, `edit` |

## [List Posts](#list-posts)

Query this endpoint to retrieve a collection of posts. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](#definition)

`GET /wp/v2/posts`

### [Example Request](#example-request)

`$ curl https://example.com/wp-json/wp/v2/posts`

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |
| `page` | Current page of the collection.<br><br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set.<br><br>Default: `10` |
| `search` | Limit results to those matching a string. |
| `after` | Limit response to posts published after a given ISO8601 compliant date. |
| `modified_after` | Limit response to posts modified after a given ISO8601 compliant date. |
| `author` | Limit result set to posts assigned to specific authors. |
| `author_exclude` | Ensure result set excludes posts assigned to specific authors. |
| `before` | Limit response to posts published before a given ISO8601 compliant date. |
| `modified_before` | Limit response to posts modified before a given ISO8601 compliant date. |
| `exclude` | Ensure result set excludes specific IDs. |
| `include` | Limit result set to specific IDs. |
| `offset` | Offset the result set by a specific number of items. |
| `order` | Order sort attribute ascending or descending.<br><br>Default: `desc`<br><br>One of: `asc`, `desc` |
| `orderby` | Sort collection by post attribute.<br><br>Default: `date`<br><br>One of: `author`, `date`, `id`, `include`, `modified`, `parent`, `relevance`, `slug`, `include_slugs`, `title` |
| `search_columns` | Array of column names to be searched. |
| `slug` | Limit result set to posts with one or more specific slugs. |
| `status` | Limit result set to posts assigned one or more statuses.<br><br>Default: `publish` |
| `tax_relation` | Limit result set based on relationship between multiple taxonomies.  <br>One of: `AND`, `OR` |
| `categories` | Limit result set to items with specific terms assigned in the categories taxonomy. |
| `categories_exclude` | Limit result set to items except those with specific terms assigned in the categories taxonomy. |
| `tags` | Limit result set to items with specific terms assigned in the tags taxonomy. |
| `tags_exclude` | Limit result set to items except those with specific terms assigned in the tags taxonomy. |
| `sticky` | Limit result set to items that are sticky. |

## [Create a Post](#create-a-post)

### [Arguments](#arguments-2)

|     |     |
| --- | --- |
| `[date](#schema-date)` | The date the post was published, in the site's timezone. |
| `[date_gmt](#schema-date_gmt)` | The date the post was published, as GMT. |
| `[slug](#schema-slug)` | An alphanumeric identifier for the post unique to its type. |
| `[status](#schema-status)` | A named status for the post.  <br>One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[password](#schema-password)` | A password to protect access to the content and excerpt. |
| `[title](#schema-title)` | The title for the post. |
| `[content](#schema-content)` | The content for the post. |
| `[author](#schema-author)` | The ID for the author of the post. |
| `[excerpt](#schema-excerpt)` | The excerpt for the post. |
| `[featured_media](#schema-featured_media)` | The ID of the featured media for the post. |
| `[comment_status](#schema-comment_status)` | Whether or not comments are open on the post.  <br>One of: `open`, `closed` |
| `[ping_status](#schema-ping_status)` | Whether or not the post can be pinged.  <br>One of: `open`, `closed` |
| `[format](#schema-format)` | The format for the post.  <br>One of: `standard`, `aside`, `chat`, `gallery`, `link`, `image`, `quote`, `status`, `video`, `audio` |
| `[meta](#schema-meta)` | Meta fields. |
| `[sticky](#schema-sticky)` | Whether or not the post should be treated as sticky. |
| `[template](#schema-template)` | The theme file to use to display the post. |
| `[categories](#schema-categories)` | The terms assigned to the post in the category taxonomy. |
| `[tags](#schema-tags)` | The terms assigned to the post in the post\_tag taxonomy. |

### [Definition](#definition-2)

`POST /wp/v2/posts`

## [Retrieve a Post](#retrieve-a-post)

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/posts/<id>`

Query this endpoint to retrieve a specific post record.

`$ curl https://example.com/wp-json/wp/v2/posts/<id>`

### [Arguments](#arguments-3)

|     |     |
| --- | --- |
| `id` | Unique identifier for the post. |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |
| `password` | The password for the post if it is password protected. |

## [Update a Post](#update-a-post)

### [Arguments](#arguments-4)

|     |     |
| --- | --- |
| `[id](#schema-id)` | Unique identifier for the post. |
| `[date](#schema-date)` | The date the post was published, in the site's timezone. |
| `[date_gmt](#schema-date_gmt)` | The date the post was published, as GMT. |
| `[slug](#schema-slug)` | An alphanumeric identifier for the post unique to its type. |
| `[status](#schema-status)` | A named status for the post.  <br>One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[password](#schema-password)` | A password to protect access to the content and excerpt. |
| `[title](#schema-title)` | The title for the post. |
| `[content](#schema-content)` | The content for the post. |
| `[author](#schema-author)` | The ID for the author of the post. |
| `[excerpt](#schema-excerpt)` | The excerpt for the post. |
| `[featured_media](#schema-featured_media)` | The ID of the featured media for the post. |
| `[comment_status](#schema-comment_status)` | Whether or not comments are open on the post.  <br>One of: `open`, `closed` |
| `[ping_status](#schema-ping_status)` | Whether or not the post can be pinged.  <br>One of: `open`, `closed` |
| `[format](#schema-format)` | The format for the post.  <br>One of: `standard`, `aside`, `chat`, `gallery`, `link`, `image`, `quote`, `status`, `video`, `audio` |
| `[meta](#schema-meta)` | Meta fields. |
| `[sticky](#schema-sticky)` | Whether or not the post should be treated as sticky. |
| `[template](#schema-template)` | The theme file to use to display the post. |
| `[categories](#schema-categories)` | The terms assigned to the post in the category taxonomy. |
| `[tags](#schema-tags)` | The terms assigned to the post in the post\_tag taxonomy. |

### [Definition](#definition-3)

`POST /wp/v2/posts/<id>`

### [Example Request](#example-request-2)

`$ curl -X POST https://example.com/wp-json/wp/v2/posts/<id> -d '{"title":"My New Title"}'   `

## [Delete a Post](#delete-a-post)

### [Arguments](#arguments-5)

|     |     |
| --- | --- |
| `id` | Unique identifier for the post. |
| `force` | Whether to bypass Trash and force deletion. |

### [Definition](#definition-4)

`DELETE /wp/v2/posts/<id>`

### [Example Request](#example-request-3)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/posts/<id>`

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
