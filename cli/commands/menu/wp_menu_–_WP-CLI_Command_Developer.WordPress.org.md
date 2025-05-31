# wp menu – WP-CLI Command | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/cli/commands/menu/](https://developer.wordpress.org/cli/commands/menu/)  
**Last Updated:** 2025-05-23T01:15:15.927Z  
**Extracted:** 2025-05-31 16:56:23

---

# wp menu – WP-CLI Command

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

See the [Navigation Menus](https://developer.wordpress.org/themes/functionality/navigation-menus/) reference in the Theme Handbook.

### [Examples](#examples)

```
# Create a new menu
$ wp menu create "My Menu"
Success: Created menu 200.

# List existing menus
$ wp menu list
+---------+----------+----------+-----------+-------+
| term_id | name     | slug     | locations | count |
+---------+----------+----------+-----------+-------+
| 200     | My Menu  | my-menu  |           | 0     |
| 177     | Top Menu | top-menu | primary   | 7     |
+---------+----------+----------+-----------+-------+

# Create a new menu link item
$ wp menu item add-custom my-menu Apple http://apple.com --porcelain
1922

# Assign the 'my-menu' menu to the 'primary' location
$ wp menu location assign my-menu primary
Success: Assigned location primary to menu my-menu.
```

### [Subcommands](#subcommands)

| Name | Description |
| --- | --- |
| [wp menu create](https://developer.wordpress.org/cli/commands/menu/create/) | Creates a new menu. |
| [wp menu delete](https://developer.wordpress.org/cli/commands/menu/delete/) | Deletes one or more menus. |
| [wp menu item](https://developer.wordpress.org/cli/commands/menu/item/) | List, add, and delete items associated with a menu. |
| [wp menu list](https://developer.wordpress.org/cli/commands/menu/list/) | Gets a list of menus. |
| [wp menu location](https://developer.wordpress.org/cli/commands/menu/location/) | Assigns, removes, and lists a menu’s locations. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
