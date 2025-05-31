# Rendered Blocks – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/rendered-blocks/](https://developer.wordpress.org/rest-api/reference/rendered-blocks/)  
**Last Updated:** 2025-05-23T01:01:49.631Z  
**Extracted:** 2025-05-31 16:56:23

---

# Rendered Blocks – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a Rendered Block record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `rendered` | The rendered block.<br><br>JSON data type: string<br><br>Context: `edit` |

## [Create a Rendered Block](#create-a-rendered-block)

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `[name](#schema-name)` | Unique registered name for the block. |
| `[context](#schema-context)` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `edit` |
| `[attributes](#schema-attributes)` | Attributes for the block. |
| `[post_id](#schema-post_id)` | ID of the post context. |

### [Definition](#definition)

`POST /wp/v2/block-renderer/<name>`

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
