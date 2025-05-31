# Block Patterns – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/block-patterns/](https://developer.wordpress.org/rest-api/reference/block-patterns/)  
**Last Updated:** 2025-05-23T01:02:54.548Z  
**Extracted:** 2025-05-31 16:56:23

---

# Block Patterns – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a block pattern record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `name` | The pattern name.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `title` | The pattern title, in human readable format.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `content` | The pattern content.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `description` | The pattern detailed description.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `viewport_width` | The pattern viewport width for inserter preview.<br><br>JSON data type: number<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `inserter` | Determines whether the pattern is visible in inserter.<br><br>JSON data type: boolean<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `categories` | The pattern category slugs.<br><br>JSON data type: array<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `keywords` | The pattern keywords.<br><br>JSON data type: array<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `block_types` | Block types that the pattern is intended to be used with.<br><br>JSON data type: array<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `post_types` | An array of post types that the pattern is restricted to be used with.<br><br>JSON data type: array<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `template_types` | An array of template types where the pattern fits.<br><br>JSON data type: array<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `source` | Where the pattern comes from e.g. core<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `edit`, `embed`<br><br>One of: `core`, `plugin`, `theme`, `pattern-directory/core`, `pattern-directory/theme`, `pattern-directory/featured` |

## [Retrieve a Block Pattern](#retrieve-a-block-pattern)

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/block-patterns/patterns`

Query this endpoint to retrieve a specific block pattern record.

`$ curl https://example.com/wp-json/wp/v2/block-patterns/patterns`

There are no arguments for this endpoint.

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
