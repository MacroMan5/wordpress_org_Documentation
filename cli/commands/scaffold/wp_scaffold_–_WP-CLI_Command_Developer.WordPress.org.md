# wp scaffold – WP-CLI Command | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/cli/commands/scaffold/](https://developer.wordpress.org/cli/commands/scaffold/)  
**Last Updated:** 2025-05-23T01:13:26.826Z  
**Extracted:** 2025-05-31 16:56:23

---

# wp scaffold – WP-CLI Command

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/scaffold-command)

### [Examples](#examples)

```
# Generate a new plugin with unit tests.
$ wp scaffold plugin sample-plugin
Success: Created plugin files.
Success: Created test files.

# Generate theme based on _s.
$ wp scaffold _s sample-theme --theme_name="Sample Theme" --author="John Doe"
Success: Created theme 'Sample Theme'.

# Generate code for post type registration in given theme.
$ wp scaffold post-type movie --label=Movie --theme=simple-life
Success: Created '/var/www/example.com/public_html/wp-content/themes/simple-life/post-types/movie.php'.
```

### [Subcommands](#subcommands)

| Name | Description |
| --- | --- |
| [wp scaffold block](https://developer.wordpress.org/cli/commands/scaffold/block/) | Generates PHP, JS and CSS code for registering a Gutenberg block for a plugin or theme. |
| [wp scaffold child-theme](https://developer.wordpress.org/cli/commands/scaffold/child-theme/) | Generates child theme based on an existing theme. |
| [wp scaffold package](https://developer.wordpress.org/cli/commands/scaffold/package/) | Generate the files needed for a basic WP-CLI command. |
| [wp scaffold package-github](https://developer.wordpress.org/cli/commands/scaffold/package-github/) | Generate GitHub configuration files for your command. |
| [wp scaffold package-readme](https://developer.wordpress.org/cli/commands/scaffold/package-readme/) | Generate a README.md for your command. |
| [wp scaffold package-tests](https://developer.wordpress.org/cli/commands/scaffold/package-tests/) | Generate files for writing Behat tests for your command. |
| [wp scaffold plugin](https://developer.wordpress.org/cli/commands/scaffold/plugin/) | Generates starter code for a plugin. |
| [wp scaffold plugin-tests](https://developer.wordpress.org/cli/commands/scaffold/plugin-tests/) | Generates files needed for running PHPUnit tests in a plugin. |
| [wp scaffold post-type](https://developer.wordpress.org/cli/commands/scaffold/post-type/) | Generates PHP code for registering a custom post type. |
| [wp scaffold taxonomy](https://developer.wordpress.org/cli/commands/scaffold/taxonomy/) | Generates PHP code for registering a custom taxonomy. |
| [wp scaffold theme-tests](https://developer.wordpress.org/cli/commands/scaffold/theme-tests/) | Generates files needed for running PHPUnit tests in a theme. |
| [wp scaffold underscores](https://developer.wordpress.org/cli/commands/scaffold/underscores/) | Generates starter code for a theme based on \_s. |
| [wp scaffold \_s](https://developer.wordpress.org/cli/commands/scaffold/_s/) | Generates starter code for a theme based on \_s. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
