# Users – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/users/](https://developer.wordpress.org/rest-api/reference/users/)  
**Last Updated:** 2025-05-23T01:03:19.351Z  
**Extracted:** 2025-05-31 16:56:23

---

# Users – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a user record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `id` | Unique identifier for the user.<br><br>JSON data type: integer<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `username` | Login name for the user.<br><br>JSON data type: string<br><br>Context: `edit` |
| `name` | Display name for the user.<br><br>JSON data type: string<br><br>Context: `embed`, `view`, `edit` |
| `first_name` | First name for the user.<br><br>JSON data type: string<br><br>Context: `edit` |
| `last_name` | Last name for the user.<br><br>JSON data type: string<br><br>Context: `edit` |
| `email` | The email address for the user.<br><br>JSON data type: string,  <br>Format: email<br><br>Context: `edit` |
| `url` | URL of the user.<br><br>JSON data type: string,  <br>Format: uri<br><br>Context: `embed`, `view`, `edit` |
| `description` | Description of the user.<br><br>JSON data type: string<br><br>Context: `embed`, `view`, `edit` |
| `link` | Author URL of the user.<br><br>JSON data type: string,  <br>Format: uri<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `locale` | Locale for the user.<br><br>JSON data type: string<br><br>Context: `edit`<br><br>One of: , `en_US` |
| `nickname` | The nickname for the user.<br><br>JSON data type: string<br><br>Context: `edit` |
| `slug` | An alphanumeric identifier for the user.<br><br>JSON data type: string<br><br>Context: `embed`, `view`, `edit` |
| `registered_date` | Registration date for the user.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Read only<br><br>Context: `edit` |
| `roles` | Roles assigned to the user.<br><br>JSON data type: array<br><br>Context: `edit` |
| `password` | Password for the user (never included).<br><br>JSON data type: string<br><br>Context: |
| `capabilities` | All capabilities assigned to the user.<br><br>JSON data type: object<br><br>Read only<br><br>Context: `edit` |
| `extra_capabilities` | Any extra capabilities assigned to the user.<br><br>JSON data type: object<br><br>Read only<br><br>Context: `edit` |
| `avatar_urls` | Avatar URLs for the user.<br><br>JSON data type: object<br><br>Read only<br><br>Context: `embed`, `view`, `edit` |
| `meta` | Meta fields.<br><br>JSON data type: object<br><br>Context: `view`, `edit` |

## [List Users](#list-users)

Query this endpoint to retrieve a collection of users. The response you receive can be controlled and filtered using the URL query parameters below.

### [Definition](#definition)

`GET /wp/v2/users`

### [Example Request](#example-request)

`$ curl https://example.com/wp-json/wp/v2/users`

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |
| `page` | Current page of the collection.<br><br>Default: `1` |
| `per_page` | Maximum number of items to be returned in result set.<br><br>Default: `10` |
| `search` | Limit results to those matching a string. |
| `exclude` | Ensure result set excludes specific IDs. |
| `include` | Limit result set to specific IDs. |
| `offset` | Offset the result set by a specific number of items. |
| `order` | Order sort attribute ascending or descending.<br><br>Default: `asc`<br><br>One of: `asc`, `desc` |
| `orderby` | Sort collection by user attribute.<br><br>Default: `name`<br><br>One of: `id`, `include`, `name`, `registered_date`, `slug`, `include_slugs`, `email`, `url` |
| `slug` | Limit result set to users with one or more specific slugs. |
| `roles` | Limit result set to users matching at least one specific role provided. Accepts csv list or single role. |
| `capabilities` | Limit result set to users matching at least one specific capability provided. Accepts csv list or single capability. |
| `who` | Limit result set to users who are considered authors.  <br>One of: `authors` |
| `has_published_posts` | Limit result set to users who have published posts. |

## [Create a User](#create-a-user)

### [Arguments](#arguments-2)

|     |     |
| --- | --- |
| `[username](#schema-username)` | Login name for the user.<br><br>Required: 1 |
| `[name](#schema-name)` | Display name for the user. |
| `[first_name](#schema-first_name)` | First name for the user. |
| `[last_name](#schema-last_name)` | Last name for the user. |
| `[email](#schema-email)` | The email address for the user.<br><br>Required: 1 |
| `[url](#schema-url)` | URL of the user. |
| `[description](#schema-description)` | Description of the user. |
| `[locale](#schema-locale)` | Locale for the user.  <br>One of: , `en_US` |
| `[nickname](#schema-nickname)` | The nickname for the user. |
| `[slug](#schema-slug)` | An alphanumeric identifier for the user. |
| `[roles](#schema-roles)` | Roles assigned to the user. |
| `[password](#schema-password)` | Password for the user (never included).<br><br>Required: 1 |
| `[meta](#schema-meta)` | Meta fields. |

### [Definition](#definition-2)

`POST /wp/v2/users`

## [Retrieve a User](#retrieve-a-user)

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/users/<id>`

Query this endpoint to retrieve a specific user record.

`$ curl https://example.com/wp-json/wp/v2/users/<id>`

### [Arguments](#arguments-3)

|     |     |
| --- | --- |
| `id` | Unique identifier for the user. |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

## [Update a User](#update-a-user)

### [Arguments](#arguments-4)

|     |     |
| --- | --- |
| `[id](#schema-id)` | Unique identifier for the user. |
| `[username](#schema-username)` | Login name for the user. |
| `[name](#schema-name)` | Display name for the user. |
| `[first_name](#schema-first_name)` | First name for the user. |
| `[last_name](#schema-last_name)` | Last name for the user. |
| `[email](#schema-email)` | The email address for the user. |
| `[url](#schema-url)` | URL of the user. |
| `[description](#schema-description)` | Description of the user. |
| `[locale](#schema-locale)` | Locale for the user.  <br>One of: , `en_US` |
| `[nickname](#schema-nickname)` | The nickname for the user. |
| `[slug](#schema-slug)` | An alphanumeric identifier for the user. |
| `[roles](#schema-roles)` | Roles assigned to the user. |
| `[password](#schema-password)` | Password for the user (never included). |
| `[meta](#schema-meta)` | Meta fields. |

### [Definition](#definition-3)

`POST /wp/v2/users/<id>`

### [Example Request](#example-request-2)

## [Delete a User](#delete-a-user)

### [Arguments](#arguments-5)

|     |     |
| --- | --- |
| `id` | Unique identifier for the user. |
| `force` | Required to be true, as users do not support trashing. |
| `reassign` | Reassign the deleted user's posts and links to this user ID.<br><br>Required: 1 |

### [Definition](#definition-4)

`DELETE /wp/v2/users/<id>`

### [Example Request](#example-request-3)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/users/<id>`

## [Retrieve a User](#retrieve-a-user-2)

### [Definition & Example Request](#definition-example-request-2)

`GET /wp/v2/users/me`

Query this endpoint to retrieve a specific user record.

`$ curl https://example.com/wp-json/wp/v2/users/me`

### [Arguments](#arguments-6)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

## [Update a User](#update-a-user-2)

### [Arguments](#arguments-7)

|     |     |
| --- | --- |
| `[username](#schema-username)` | Login name for the user. |
| `[name](#schema-name)` | Display name for the user. |
| `[first_name](#schema-first_name)` | First name for the user. |
| `[last_name](#schema-last_name)` | Last name for the user. |
| `[email](#schema-email)` | The email address for the user. |
| `[url](#schema-url)` | URL of the user. |
| `[description](#schema-description)` | Description of the user. |
| `[locale](#schema-locale)` | Locale for the user.  <br>One of: , `en_US` |
| `[nickname](#schema-nickname)` | The nickname for the user. |
| `[slug](#schema-slug)` | An alphanumeric identifier for the user. |
| `[roles](#schema-roles)` | Roles assigned to the user. |
| `[password](#schema-password)` | Password for the user (never included). |
| `[meta](#schema-meta)` | Meta fields. |

### [Definition](#definition-5)

`POST /wp/v2/users/me`

### [Example Request](#example-request-4)

## [Delete a User](#delete-a-user-2)

### [Arguments](#arguments-8)

|     |     |
| --- | --- |
| `force` | Required to be true, as users do not support trashing. |
| `reassign` | Reassign the deleted user's posts and links to this user ID.<br><br>Required: 1 |

### [Definition](#definition-6)

`DELETE /wp/v2/users/me`

### [Example Request](#example-request-5)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/users/me`

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
