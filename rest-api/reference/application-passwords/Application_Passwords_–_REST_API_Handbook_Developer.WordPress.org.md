# Application Passwords – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/application-passwords/](https://developer.wordpress.org/rest-api/reference/application-passwords/)  
**Last Updated:** 2025-05-23T01:02:47.558Z  
**Extracted:** 2025-05-31 16:56:23

---

# Application Passwords – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a application password record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `uuid` | The unique identifier for the application password.<br><br>JSON data type: string,  <br>Format: uuid<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `app_id` | A UUID provided by the application to uniquely identify it. It is recommended to use an UUID v5 with the URL or DNS namespace.<br><br>JSON data type: string,  <br>Format: uuid<br><br>Context: `view`, `edit`, `embed` |
| `name` | The name of the application password.<br><br>JSON data type: string<br><br>Context: `view`, `edit`, `embed` |
| `password` | The generated password. Only available after adding an application.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `edit` |
| `created` | The GMT date the application password was created.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Read only<br><br>Context: `view`, `edit` |
| `last_used` | The GMT date the application password was last used.<br><br>JSON data type: string or null,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Read only<br><br>Context: `view`, `edit` |
| `last_ip` | The IP address the application password was last used by.<br><br>JSON data type: string or null,  <br>Format: ip<br><br>Read only<br><br>Context: `view`, `edit` |

## [Retrieve a Application Password](#retrieve-a-application-password)

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/users/<user_id>)/application-passwords`

Query this endpoint to retrieve a specific application password record.

`$ curl https://example.com/wp-json/wp/v2/users/<user_id>)/application-passwords`

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

## [Create a Application Password](#create-a-application-password)

### [Arguments](#arguments-2)

|     |     |
| --- | --- |
| `[app_id](#schema-app_id)` | A UUID provided by the application to uniquely identify it. It is recommended to use an UUID v5 with the URL or DNS namespace. |
| `[name](#schema-name)` | The name of the application password.<br><br>Required: 1 |

### [Definition](#definition)

`POST /wp/v2/users/<user_id>)/application-passwords`

## [Delete a Application Password](#delete-a-application-password)

There are no arguments for this endpoint.

### [Definition](#definition-2)

`DELETE /wp/v2/users/<user_id>)/application-passwords`

### [Example Request](#example-request)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/users/<user_id>)/application-passwords`

## [Retrieve a Application Password](#retrieve-a-application-password-2)

### [Definition & Example Request](#definition-example-request-2)

`GET /wp/v2/users/<user_id>)/application-passwords/introspect`

Query this endpoint to retrieve a specific application password record.

`$ curl https://example.com/wp-json/wp/v2/users/<user_id>)/application-passwords/introspect`

### [Arguments](#arguments-3)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

## [Retrieve a Application Password](#retrieve-a-application-password-3)

### [Definition & Example Request](#definition-example-request-3)

`GET /wp/v2/users/<user_id>)/application-passwords/<uuid>`

Query this endpoint to retrieve a specific application password record.

`$ curl https://example.com/wp-json/wp/v2/users/<user_id>)/application-passwords/<uuid>`

### [Arguments](#arguments-4)

|     |     |
| --- | --- |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

## [Update a Application Password](#update-a-application-password)

### [Arguments](#arguments-5)

|     |     |
| --- | --- |
| `[app_id](#schema-app_id)` | A UUID provided by the application to uniquely identify it. It is recommended to use an UUID v5 with the URL or DNS namespace. |
| `[name](#schema-name)` | The name of the application password. |

### [Definition](#definition-3)

`POST /wp/v2/users/<user_id>)/application-passwords/<uuid>`

### [Example Request](#example-request-2)

## [Delete a Application Password](#delete-a-application-password-2)

There are no arguments for this endpoint.

### [Definition](#definition-4)

`DELETE /wp/v2/users/<user_id>)/application-passwords/<uuid>`

### [Example Request](#example-request-3)

`$ curl -X DELETE https://example.com/wp-json/wp/v2/users/<user_id>)/application-passwords/<uuid>`

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
