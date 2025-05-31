# wp language – WP-CLI Command | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/cli/commands/language/](https://developer.wordpress.org/cli/commands/language/)  
**Last Updated:** 2025-05-23T01:15:14.067Z  
**Extracted:** 2025-05-31 16:56:23

---

# wp language – WP-CLI Command

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/language-command)

### [Examples](#examples)

```
# Install the Dutch core language pack.
$ wp language core install nl_NL
Downloading translation from https://downloads.wordpress.org/translation/core/6.4.3/nl_NL.zip...
Unpacking the update...
Installing the latest version...
Removing the old version of the translation...
Translation updated successfully.
Language 'nl_NL' installed.
Success: Installed 1 of 1 languages.

# Activate the Dutch core language pack.
$ wp site switch-language nl_NL
Success: Language activated.

# Install the Dutch theme language pack for Twenty Ten.
$ wp language theme install twentyten nl_NL
Downloading translation from https://downloads.wordpress.org/translation/theme/twentyten/4.0/nl_NL.zip...
Unpacking the update...
Installing the latest version...
Removing the old version of the translation...
Translation updated successfully.
Language 'nl_NL' installed.
Success: Installed 1 of 1 languages.

# Install the Dutch plugin language pack for Hello Dolly.
$ wp language plugin install hello-dolly nl_NL
Downloading translation from https://downloads.wordpress.org/translation/plugin/hello-dolly/1.7.2/nl_NL.zip...
Unpacking the update...
Installing the latest version...
Removing the old version of the translation...
Translation updated successfully.
Language 'nl_NL' installed.
Success: Installed 1 of 1 languages.
```

### [Subcommands](#subcommands)

| Name | Description |
| --- | --- |
| [wp language core](https://developer.wordpress.org/cli/commands/language/core/) | Installs, activates, and manages core language packs. |
| [wp language plugin](https://developer.wordpress.org/cli/commands/language/plugin/) | Installs, activates, and manages plugin language packs. |
| [wp language theme](https://developer.wordpress.org/cli/commands/language/theme/) | Installs, activates, and manages theme language packs. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
