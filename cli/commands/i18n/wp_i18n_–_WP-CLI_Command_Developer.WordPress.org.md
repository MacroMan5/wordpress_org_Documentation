# wp i18n – WP-CLI Command | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/cli/commands/i18n/](https://developer.wordpress.org/cli/commands/i18n/)  
**Last Updated:** 2025-05-23T01:15:06.522Z  
**Extracted:** 2025-05-31 16:56:23

---

# wp i18n – WP-CLI Command

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/i18n-command)

Unless overridden, these commands run on the `before_wp_load` hook, just before the WP load process begins.

### [Examples](#examples)

```
# Create a POT file for the WordPress plugin/theme in the current directory
$ wp i18n make-pot . languages/my-plugin.pot
```

### [Subcommands](#subcommands)

| Name | Description |
| --- | --- |
| [wp i18n make-json](https://developer.wordpress.org/cli/commands/i18n/make-json/) | Extract JavaScript strings from PO files and add them to individual JSON files. |
| [wp i18n make-mo](https://developer.wordpress.org/cli/commands/i18n/make-mo/) | Create MO files from PO files. |
| [wp i18n make-php](https://developer.wordpress.org/cli/commands/i18n/make-php/) | Create PHP files from PO files. |
| [wp i18n make-pot](https://developer.wordpress.org/cli/commands/i18n/make-pot/) | Create a POT file for a WordPress project. |
| [wp i18n update-po](https://developer.wordpress.org/cli/commands/i18n/update-po/) | Update PO files from a POT file. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
