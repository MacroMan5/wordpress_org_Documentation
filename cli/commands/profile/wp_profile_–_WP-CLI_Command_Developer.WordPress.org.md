# wp profile – WP-CLI Command | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/cli/commands/profile/](https://developer.wordpress.org/cli/commands/profile/)  
**Last Updated:** 2025-05-23T01:13:23.036Z  
**Extracted:** 2025-05-31 16:56:23

---

# wp profile – WP-CLI Command

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/profile-command)

### [Examples](#examples)

```
# See an overview for each stage of the load process.
$ wp profile stage --fields=stage,time,cache_ratio
+------------+---------+-------------+
| stage      | time    | cache_ratio |
+------------+---------+-------------+
| bootstrap  | 0.7994s | 93.21%      |
| main_query | 0.0123s | 94.29%      |
| template   | 0.792s  | 91.23%      |
+------------+---------+-------------+
| total (3)  | 1.6037s | 92.91%      |
+------------+---------+-------------+

# Dive into hook performance for a given stage.
$ wp profile stage bootstrap --fields=hook,time,cache_ratio --spotlight
+--------------------------+---------+-------------+
| hook                     | time    | cache_ratio |
+--------------------------+---------+-------------+
| muplugins_loaded:before  | 0.1767s | 33.33%      |
| plugins_loaded:before    | 0.103s  | 78.13%      |
| plugins_loaded           | 0.0194s | 19.32%      |
| setup_theme              | 0.0018s | 75%         |
| after_setup_theme:before | 0.0116s | 95.45%      |
| after_setup_theme        | 0.0049s | 96%         |
| init                     | 0.1428s | 76.74%      |
| wp_loaded:after          | 0.0236s |             |
+--------------------------+---------+-------------+
| total (8)                | 0.4837s | 67.71%      |
+--------------------------+---------+-------------+
```

### [Installing](#installing)

Use the `wp profile` command by installing the command’s package:

```
wp package install wp-cli/profile-command
```

Once the package is successfully installed, the `wp profile` command will appear in the list of available commands.

### [Subcommands](#subcommands)

| Name | Description |
| --- | --- |
| [wp profile eval](https://developer.wordpress.org/cli/commands/profile/eval/) | Profile arbitrary code execution. |
| [wp profile eval-file](https://developer.wordpress.org/cli/commands/profile/eval-file/) | Profile execution of an arbitrary file. |
| [wp profile hook](https://developer.wordpress.org/cli/commands/profile/hook/) | Profile key metrics for WordPress hooks (actions and filters). |
| [wp profile stage](https://developer.wordpress.org/cli/commands/profile/stage/) | Profile each stage of the WordPress load process (bootstrap, main\_query, template). |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
