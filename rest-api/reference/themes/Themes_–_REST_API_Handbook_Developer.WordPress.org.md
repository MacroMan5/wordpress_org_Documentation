# Themes – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/themes/](https://developer.wordpress.org/rest-api/reference/themes/)  
**Last Updated:** 2025-05-23T01:03:13.560Z  
**Extracted:** 2025-05-31 16:56:23

---

# Themes – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a theme record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `stylesheet` | The theme's stylesheet. This uniquely identifies the theme.<br><br>JSON data type: string<br><br>Read only<br><br>Context: |
| `template` | The theme's template. If this is a child theme, this refers to the parent theme, otherwise this is the same as the theme's stylesheet.<br><br>JSON data type: string<br><br>Read only<br><br>Context: |
| `author` | The theme author.<br><br>JSON data type: object<br><br>Read only<br><br>Context: |
| `author_uri` | The website of the theme author.<br><br>JSON data type: object<br><br>Read only<br><br>Context: |
| `description` | A description of the theme.<br><br>JSON data type: object<br><br>Read only<br><br>Context: |
| `is_block_theme` | Whether the theme is a block-based theme.<br><br>JSON data type: boolean<br><br>Read only<br><br>Context: |
| `name` | The name of the theme.<br><br>JSON data type: object<br><br>Read only<br><br>Context: |
| `requires_php` | The minimum PHP version required for the theme to work.<br><br>JSON data type: string<br><br>Read only<br><br>Context: |
| `requires_wp` | The minimum WordPress version required for the theme to work.<br><br>JSON data type: string<br><br>Read only<br><br>Context: |
| `screenshot` | The theme's screenshot URL.<br><br>JSON data type: string,  <br>Format: uri<br><br>Read only<br><br>Context: |
| `tags` | Tags indicating styles and features of the theme.<br><br>JSON data type: object<br><br>Read only<br><br>Context: |
| `textdomain` | The theme's text domain.<br><br>JSON data type: string<br><br>Read only<br><br>Context: |
| `theme_supports` | Features supported by this theme.<br><br>JSON data type: object<br><br>Read only<br><br>Context: |
| `theme_uri` | The URI of the theme's webpage.<br><br>JSON data type: object<br><br>Read only<br><br>Context: |
| `version` | The theme's current version.<br><br>JSON data type: string<br><br>Read only<br><br>Context: |
| `status` | A named status for the theme.<br><br>JSON data type: string<br><br>Context:<br><br>One of: `inactive`, `active` |

## [Retrieve a Theme](#retrieve-a-theme)

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/themes`

Query this endpoint to retrieve a specific theme record.

`$ curl https://example.com/wp-json/wp/v2/themes`

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `status` | Limit result set to themes assigned one or more statuses. |

## [Retrieve a Theme](#retrieve-a-theme-2)

### [Definition & Example Request](#definition-example-request-2)

`GET /wp/v2/themes/<stylesheet>?)`

Query this endpoint to retrieve a specific theme record.

`$ curl https://example.com/wp-json/wp/v2/themes/<stylesheet>?)`

### [Arguments](#arguments-2)

|     |     |
| --- | --- |
| `stylesheet` | The theme's stylesheet. This uniquely identifies the theme. |

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
