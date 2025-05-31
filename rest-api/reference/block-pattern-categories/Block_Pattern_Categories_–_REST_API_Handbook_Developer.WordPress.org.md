# Block Pattern Categories – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/block-pattern-categories/](https://developer.wordpress.org/rest-api/reference/block-pattern-categories/)  
**Last Updated:** 2025-05-23T01:02:54.334Z  
**Extracted:** 2025-05-31 16:56:23

---

# Block Pattern Categories – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a block pattern category record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `name` | The category name.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `label` | The category label, in human readable format.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |
| `description` | The category description, in human readable format.<br><br>JSON data type: string<br><br>Read only<br><br>Context: `view`, `edit`, `embed` |

## [Retrieve a Block Pattern Category](#retrieve-a-block-pattern-category)

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/block-patterns/categories`

Query this endpoint to retrieve a specific block pattern category record.

`$ curl https://example.com/wp-json/wp/v2/block-patterns/categories`

There are no arguments for this endpoint.

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
