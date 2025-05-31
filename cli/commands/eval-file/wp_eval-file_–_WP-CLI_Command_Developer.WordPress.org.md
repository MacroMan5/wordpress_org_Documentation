# wp eval-file – WP-CLI Command | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/cli/commands/eval-file/](https://developer.wordpress.org/cli/commands/eval-file/)  
**Last Updated:** 2025-05-23T01:15:03.620Z  
**Extracted:** 2025-05-31 16:56:23

---

# wp eval-file – WP-CLI Command

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/eval-command)

This command runs on the `before_wp_load` hook, just before the WP load process begins. Note: because code is executed within a method, global variables need to be explicitly globalized.

### [Options](#options)

<file>

The path to the PHP file to execute. Use ‘-‘ to run code from STDIN.

\[<arg>…\]

One or more positional arguments to pass to the file. They are placed in the $args variable.

\[--skip-wordpress\]

Load and execute file without loading WordPress.

\[--use-include\]

Process the provided file via include instead of evaluating its contents.

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
