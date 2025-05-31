# wp find – WP-CLI Command | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/cli/commands/find/](https://developer.wordpress.org/cli/commands/find/)  
**Last Updated:** 2025-05-23T01:15:05.944Z  
**Extracted:** 2025-05-31 16:56:23

---

# wp find – WP-CLI Command

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/find-command)

This command runs on the `before_wp_load` hook, just before the WP load process begins. Recursively iterates subdirectories of provided <path> to find and report WordPress installations. A WordPress installation is a wp-includes directory with a version.php file. Avoids recursing some known paths (e.g. /node\_modules/, hidden sys dirs) to significantly improve performance. Indicates depth at which the WordPress installations was found, and its alias, if it has one.

### [Installing](#installing)

Use the `wp find` command by installing the command’s package:

```
wp package install wp-cli/find-command
```

Once the package is successfully installed, the `wp find` command will appear in the list of available commands.

### [Options](#options)

<path>

Path to search the subdirectories of.

\[--skip-ignored-paths\]

Skip the paths that are ignored by default.

\[--include\_ignored\_paths=<paths>\]

Include additional ignored paths as CSV (e.g. ‘/sys-backup/,/temp/’).

\[--max\_depth=<max-depth>\]

Only recurse to a specified depth, inclusive.

\[--fields=<fields>\]

Limit the output to specific row fields.

\[--field=<field>\]

Output a specific field for each row.

\[--format=<format>\]

Render output in a specific format.  
—  
default: table  
options:  
– table  
– json  
– csv  
– yaml  
– count  
—  

\[--verbose\]

Log useful information to STDOUT.

### [Available Fields](#available-fields)

These fields will be displayed by default for each installation:

*   version\_path – Path to the version.php file.
*   version – WordPress version.
*   depth – Directory depth at which the installation was found.
*   alias – WP-CLI alias, if one is registered.

These fields are optionally available:

*   wp\_path – Path that can be passed to `--path=&lt;path&gt;` global parameter.
*   db\_host – Host name for the database.
*   db\_user – User name for the database.
*   db\_name – Database name for the database.

### [Examples](#examples)

```
# Find WordPress installations.
$ wp find ./
+--------------------------------------+---------------------+-------+--------+
| version_path                         | version             | depth | alias  |
+--------------------------------------+---------------------+-------+--------+
| /Users/wpcli/wp-includes/version.php | 4.8-alpha-39357-src | 2     | @wpcli |
+--------------------------------------+---------------------+-------+--------+
```

### [Global Parameters](#global-parameters)

These [global parameters](https://make.wordpress.org/cli/handbook/config/) have the same behavior across all commands and affect how WP-CLI interacts with WordPress.

| **Argument** | **Description** |
| --- | --- |
| `--path=<path>` | Path to the WordPress files. |
| `--url=<url>` | Pretend request came from given URL. In multisite, this argument is how the target site is specified. |
| `--ssh=[<scheme>:][<user>@]<host\\|container>[:<port>][<path>]` | Perform operation against a remote server over SSH (or a container using scheme of “docker”, “docker-compose”, “docker-compose-run”, “vagrant”). |
| `--http=<http>` | Perform operation against a remote WordPress installation over HTTP. |
| `--user=<id\\|login\\|email>` | Set the WordPress user. |
| `--skip-plugins[=<plugins>]` | Skip loading all plugins, or a comma-separated list of plugins. Note: mu-plugins are still loaded. |
| `--skip-themes[=<themes>]` | Skip loading all themes, or a comma-separated list of themes. |
| `--skip-packages` | Skip loading all installed packages. |
| `--require=<path>` | Load PHP file before running the command (may be used more than once). |
| `--exec=<php-code>` | Execute PHP code before running the command (may be used more than once). |
| `--context=<context>` | Load WordPress in a given context. |
| `--[no-]color` | Whether to colorize the output. |
| `--debug[=<group>]` | Show all PHP errors and add verbosity to WP-CLI output. Built-in groups include: bootstrap, commandfactory, and help. |
| `--prompt[=<assoc>]` | Prompt the user to enter values for all command arguments, or a subset specified as comma-separated values. |
| `--quiet` | Suppress informational messages. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
