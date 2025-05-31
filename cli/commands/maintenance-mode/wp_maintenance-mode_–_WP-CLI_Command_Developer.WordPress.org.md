# wp maintenance-mode – WP-CLI Command | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/cli/commands/maintenance-mode/](https://developer.wordpress.org/cli/commands/maintenance-mode/)  
**Last Updated:** 2025-05-23T01:15:14.848Z  
**Extracted:** 2025-05-31 16:56:23

---

# wp maintenance-mode – WP-CLI Command

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/maintenance-mode-command)

### [Examples](#examples)

```
# Activate Maintenance mode.
$ wp maintenance-mode activate
Enabling Maintenance mode...
Success: Activated Maintenance mode.

# Deactivate Maintenance mode.
$ wp maintenance-mode deactivate
Disabling Maintenance mode...
Success: Deactivated Maintenance mode.

# Display Maintenance mode status.
$ wp maintenance-mode status
Maintenance mode is active.

# Get Maintenance mode status for scripting purpose.
$ wp maintenance-mode is-active
$ echo $?
1
```

### [Subcommands](#subcommands)

| Name | Description |
| --- | --- |
| [wp maintenance-mode activate](https://developer.wordpress.org/cli/commands/maintenance-mode/activate/) | Activates maintenance mode. |
| [wp maintenance-mode deactivate](https://developer.wordpress.org/cli/commands/maintenance-mode/deactivate/) | Deactivates maintenance mode. |
| [wp maintenance-mode is-active](https://developer.wordpress.org/cli/commands/maintenance-mode/is-active/) | Detects maintenance mode status. |
| [wp maintenance-mode status](https://developer.wordpress.org/cli/commands/maintenance-mode/status/) | Displays maintenance mode status. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
