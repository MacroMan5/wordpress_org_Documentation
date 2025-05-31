# wp post-type – WP-CLI Command | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/cli/commands/post-type/](https://developer.wordpress.org/cli/commands/post-type/)  
**Last Updated:** 2025-05-23T01:13:22.135Z  
**Extracted:** 2025-05-31 16:56:23

---

# wp post-type – WP-CLI Command

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

Get information on WordPress’ built-in and the site’s [custom post types](https://developer.wordpress.org/plugins/post-types/).

### [Examples](#examples)

```
# Get details about a post type
$ wp post-type get page --fields=name,label,hierarchical --format=json
{"name":"page","label":"Pages","hierarchical":true}

# List post types with 'post' capability type
$ wp post-type list --capability_type=post --fields=name,public
+---------------+--------+
| name          | public |
+---------------+--------+
| post          | 1      |
| attachment    | 1      |
| revision      |        |
| nav_menu_item |        |
+---------------+--------+
```

### [Subcommands](#subcommands)

| Name | Description |
| --- | --- |
| [wp post-type get](https://developer.wordpress.org/cli/commands/post-type/get/) | Gets details about a registered post type. |
| [wp post-type list](https://developer.wordpress.org/cli/commands/post-type/list/) | Lists registered post types. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
