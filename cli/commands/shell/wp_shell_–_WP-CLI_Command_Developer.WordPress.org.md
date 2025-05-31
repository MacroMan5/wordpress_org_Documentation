# wp shell – WP-CLI Command | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/cli/commands/shell/](https://developer.wordpress.org/cli/commands/shell/)  
**Last Updated:** 2025-05-23T01:13:33.824Z  
**Extracted:** 2025-05-31 16:56:23

---

# wp shell – WP-CLI Command

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/shell-command)

`wp shell` allows you to evaluate PHP statements and expressions interactively, from within a WordPress environment. Type a bit of code, hit enter, and see the code execute right before you. Because WordPress is loaded, you have access to all the functions, classes and globals that you can use within a WordPress plugin, for example.

### [Options](#options)

\[--basic\]

Force the use of WP-CLI’s built-in PHP REPL, even if the Boris or PsySH PHP REPLs are available.

### [Examples](#examples)

```
# Call get_bloginfo() to get the name of the site.
$ wp shell
wp> get_bloginfo( 'name' );
=> string(6) "WP-CLI"
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
