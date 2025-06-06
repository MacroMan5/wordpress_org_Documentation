# wp import – WP-CLI Command | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/cli/commands/import/](https://developer.wordpress.org/cli/commands/import/)  
**Last Updated:** 2025-05-23T01:15:06.638Z  
**Extracted:** 2025-05-31 16:56:23

---

# wp import – WP-CLI Command

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/import-command)

Provides a command line interface to the WordPress Importer plugin, for performing data migrations. Use `define( 'IMPORT_DEBUG', true );` for more verbosity during importing.

### [Options](#options)

<file>…

Path to one or more valid WXR files for importing. Directories are also accepted.

\--authors=<authors>

How the author mapping should be handled. Options are ‘create’, ‘mapping.csv’, or ‘skip’. The first will create any non-existent users from the WXR file. The second will read author mapping associations from a CSV, or create a CSV for editing if the file path doesn’t exist. The CSV requires two columns, and a header row like “old\_user\_login,new\_user\_login”. The last option will skip any author mapping.

\[--skip=<data-type>\]

Skip importing specific data. Supported options are: ‘attachment’ and ‘image\_resize’ (skip time-consuming thumbnail generation).

### [Examples](#examples)

```
# Import content from a WXR file
$ wp import example.wordpress.2016-06-21.xml --authors=create
Starting the import process...
Processing post #1 ("Hello world!") (post_type: post)
-- 1 of 1
-- Tue, 21 Jun 2016 05:31:12 +0000
-- Imported post as post_id #1
Success: Finished importing from 'example.wordpress.2016-06-21.xml' file.
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
