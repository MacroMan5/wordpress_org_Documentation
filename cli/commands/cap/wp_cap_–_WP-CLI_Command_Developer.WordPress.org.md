# wp cap – WP-CLI Command | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/cli/commands/cap/](https://developer.wordpress.org/cli/commands/cap/)  
**Last Updated:** 2025-05-23T01:15:29.566Z  
**Extracted:** 2025-05-31 16:56:23

---

# wp cap – WP-CLI Command

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/role-command)

See references for [Roles and Capabilities](https://codex.wordpress.org/Roles_and_Capabilities) and [WP User class](https://codex.wordpress.org/Class_Reference/WP_User).

### [Examples](#examples)

```
# Add 'spectate' capability to 'author' role.
$ wp cap add 'author' 'spectate'
Success: Added 1 capability to 'author' role.

# Add all caps from 'editor' role to 'author' role.
$ wp cap list 'editor' | xargs wp cap add 'author'
Success: Added 24 capabilities to 'author' role.

# Remove all caps from 'editor' role that also appear in 'author' role.
$ wp cap list 'author' | xargs wp cap remove 'editor'
Success: Removed 34 capabilities from 'editor' role.
```

### [Subcommands](#subcommands)

| Name | Description |
| --- | --- |
| [wp cap add](https://developer.wordpress.org/cli/commands/cap/add/) | Adds capabilities to a given role. |
| [wp cap list](https://developer.wordpress.org/cli/commands/cap/list/) | Lists capabilities for a given role. |
| [wp cap remove](https://developer.wordpress.org/cli/commands/cap/remove/) | Removes capabilities from a given role. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
