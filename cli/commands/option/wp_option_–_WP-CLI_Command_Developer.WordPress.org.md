# wp option – WP-CLI Command | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/cli/commands/option/](https://developer.wordpress.org/cli/commands/option/)  
**Last Updated:** 2025-05-23T01:15:13.134Z  
**Extracted:** 2025-05-31 16:56:23

---

# wp option – WP-CLI Command

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/entity-command)

See the [Plugin Settings API](https://developer.wordpress.org/plugins/settings/settings-api/) and the [Theme Options](https://developer.wordpress.org/themes/customize-api/) for more information on adding customized options.

### [Examples](#examples)

```
# Get site URL.
$ wp option get siteurl
http://example.com

# Add option.
$ wp option add my_option foobar
Success: Added 'my_option' option.

# Update option.
$ wp option update my_option '{"foo": "bar"}' --format=json
Success: Updated 'my_option' option.

# Delete option.
$ wp option delete my_option
Success: Deleted 'my_option' option.
```

### [Subcommands](#subcommands)

| Name | Description |
| --- | --- |
| [wp option add](https://developer.wordpress.org/cli/commands/option/add/) | Adds a new option value. |
| [wp option delete](https://developer.wordpress.org/cli/commands/option/delete/) | Deletes an option. |
| [wp option get](https://developer.wordpress.org/cli/commands/option/get/) | Gets the value for an option. |
| [wp option get-autoload](https://developer.wordpress.org/cli/commands/option/get-autoload/) | Gets the ‘autoload’ value for an option. |
| [wp option list](https://developer.wordpress.org/cli/commands/option/list/) | Lists options and their values. |
| [wp option patch](https://developer.wordpress.org/cli/commands/option/patch/) | Updates a nested value in an option. |
| [wp option pluck](https://developer.wordpress.org/cli/commands/option/pluck/) | Gets a nested value from an option. |
| [wp option set-autoload](https://developer.wordpress.org/cli/commands/option/set-autoload/) | Sets the ‘autoload’ value for an option. |
| [wp option update](https://developer.wordpress.org/cli/commands/option/update/) | Updates an option value. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
