# wp core – WP-CLI Command | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/cli/commands/core/](https://developer.wordpress.org/cli/commands/core/)  
**Last Updated:** 2025-05-23T01:14:47.440Z  
**Extracted:** 2025-05-31 16:56:23

---

# wp core – WP-CLI Command

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/core-command)

### [Examples](#examples)

```
# Download WordPress core
$ wp core download --locale=nl_NL
Downloading WordPress 4.5.2 (nl_NL)...
md5 hash verified: c5366d05b521831dd0b29dfc386e56a5
Success: WordPress downloaded.

# Install WordPress
$ wp core install --url=example.com --title=Example --admin_user=supervisor --admin_password=strongpassword --admin_email=info@example.com
Success: WordPress installed successfully.

# Display the WordPress version
$ wp core version
4.5.2
```

### [Subcommands](#subcommands)

| Name | Description |
| --- | --- |
| [wp core check-update](https://developer.wordpress.org/cli/commands/core/check-update/) | Checks for WordPress updates via Version Check API. |
| [wp core download](https://developer.wordpress.org/cli/commands/core/download/) | Downloads core WordPress files. |
| [wp core install](https://developer.wordpress.org/cli/commands/core/install/) | Runs the standard WordPress installation process. |
| [wp core is-installed](https://developer.wordpress.org/cli/commands/core/is-installed/) | Checks if WordPress is installed. |
| [wp core multisite-convert](https://developer.wordpress.org/cli/commands/core/multisite-convert/) | Transforms an existing single-site installation into a multisite installation. |
| [wp core multisite-install](https://developer.wordpress.org/cli/commands/core/multisite-install/) | Installs WordPress multisite from scratch. |
| [wp core update](https://developer.wordpress.org/cli/commands/core/update/) | Updates WordPress to a newer version. |
| [wp core update-db](https://developer.wordpress.org/cli/commands/core/update-db/) | Runs the WordPress database update procedure. |
| [wp core verify-checksums](https://developer.wordpress.org/cli/commands/core/verify-checksums/) | Verifies WordPress files against WordPress.org’s checksums. |
| [wp core version](https://developer.wordpress.org/cli/commands/core/version/) | Displays the WordPress version. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
