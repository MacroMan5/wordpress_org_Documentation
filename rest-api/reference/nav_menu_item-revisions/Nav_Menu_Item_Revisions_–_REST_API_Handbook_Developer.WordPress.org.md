# Nav_Menu_Item Revisions – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/](https://developer.wordpress.org/rest-api/reference/nav_menu_item-revisions/)  
**Last Updated:** 2025-05-23T01:01:29.153Z  
**Extracted:** 2025-05-31 16:56:23

---

# Nav\_Menu\_Item Revisions – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a nav\_menu\_item revision record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `author` | The ID for the author of the revision.<br><br>JSON data type: integer<br><br>Context: `view`, `edit`, `embed` |
| `date` | The date the revision was published, in the site's timezone.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Context: `view`, `edit`, `embed` |
| `date_gmt` | The date the revision was published, as GMT.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Context: `view`, `edit` |
| `guid` | GUID for the revision, as it exists in the database.<br><br>JSON data type: string<br><br>Context: `view`, `edit` |
| `id` | Unique identifier for the revision.<br><br>JSON data type: integer<br><br>Context: `view`, `edit`, `embed` |
| `modified` | The date the revision was last modified, in the site's timezone.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Context: `view`, `edit` |
| `modified_gmt` | The date the revision was last modified, as GMT.<br><br>JSON data type: string,  <br>Format: datetime ([details](https://core.trac.wordpress.org/ticket/41032))<br><br>Context: `view`, `edit` |
| `parent` | The ID for the parent of the revision.<br><br>JSON data type: integer<br><br>Context: `view`, `edit`, `embed` |
| `slug` | An alphanumeric identifier for the revision unique to its type.<br><br>JSON data type: string<br><br>Context: `view`, `edit`, `embed` |
| `title` | The title for the object.<br><br>JSON data type: string or object<br><br>Context: `view`, `edit`, `embed` |
| `preview_link` | Preview link for the post.<br><br>JSON data type: string,  <br>Format: uri<br><br>Read only<br><br>Context: `edit` |

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/menu-items/<id>/autosaves`

Query this endpoint to retrieve a specific nav\_menu\_item revision record.

`$ curl https://example.com/wp-json/wp/v2/menu-items/<id>/autosaves`

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the autosave. |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

### [Arguments](#arguments-2)

|     |     |
| --- | --- |
| `[parent](#schema-parent)` | The ID for the parent of the object. |
| `[title](#schema-title)` | The title for the object. |
| `[type](#schema-type)` | The family of objects originally represented, such as "post\_type" or "taxonomy".  <br>One of: `taxonomy`, `post_type`, `post_type_archive`, `custom` |
| `[status](#schema-status)` | A named status for the object.  <br>One of: `publish`, `future`, `draft`, `pending`, `private` |
| `[attr_title](#schema-attr_title)` | Text for the title attribute of the link element for this menu item. |
| `[classes](#schema-classes)` | Class names for the link element of this menu item. |
| `[description](#schema-description)` | The description of this menu item. |
| `[menu_order](#schema-menu_order)` | The DB ID of the nav\_menu\_item that is this item's menu parent, if any, otherwise 0. |
| `[object](#schema-object)` | The type of object originally represented, such as "category", "post", or "attachment". |
| `[object_id](#schema-object_id)` | The database ID of the original object this menu item represents, for example the ID for posts or the term\_id for categories. |
| `[target](#schema-target)` | The target attribute of the link element for this menu item.  <br>One of: `_blank`, |
| `[url](#schema-url)` | The URL to which this menu item points. |
| `[xfn](#schema-xfn)` | The XFN relationship expressed in the link of this menu item. |
| `[menus](#schema-menus)` | The terms assigned to the object in the nav\_menu taxonomy. |
| `[meta](#schema-meta)` | Meta fields. |

### [Definition](#definition)

`POST /wp/v2/menu-items/<id>/autosaves`

### [Definition & Example Request](#definition-example-request-2)

`GET /wp/v2/menu-items/<parent>/autosaves/<id>`

Query this endpoint to retrieve a specific nav\_menu\_item revision record.

`$ curl https://example.com/wp-json/wp/v2/menu-items/<parent>/autosaves/<id>`

### [Arguments](#arguments-3)

|     |     |
| --- | --- |
| `parent` | The ID for the parent of the autosave. |
| `id` | The ID for the autosave. |
| `context` | Scope under which the request is made; determines fields present in response.<br><br>Default: `view`<br><br>One of: `view`, `embed`, `edit` |

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
