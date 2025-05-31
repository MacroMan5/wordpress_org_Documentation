# wp embed – WP-CLI Command | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/cli/commands/embed-2/](https://developer.wordpress.org/cli/commands/embed-2/)  
**Last Updated:** 2025-05-23T01:14:55.469Z  
**Extracted:** 2025-05-31 16:56:23

---

# wp embed – WP-CLI Command

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/embed-command)

### [Examples](#examples)

```
# Get embed HTML for a given URL.
$ wp embed fetch https://www.youtube.com/watch?v=dQw4w9WgXcQ
&lt;iframe width="525" height="295" src="https://www.youtube.com/embed/dQw4w9WgXcQ?feature=oembed" ...

# Find cache post ID for a given URL.
$ wp embed cache find https://www.youtube.com/watch?v=dQw4w9WgXcQ --width=500
123

# List format,endpoint fields of available providers.
$ wp embed provider list
+------------------------------+-----------------------------------------+
| format                       | endpoint                                |
+------------------------------+-----------------------------------------+
| #https?://youtu\.be/.*#i     | https://www.youtube.com/oembed          |
| #https?://flic\.kr/.*#i      | https://www.flickr.com/services/oembed/ |
| #https?://wordpress\.tv/.*#i | https://wordpress.tv/oembed/            |

# List id,regex,priority fields of available handlers.
$ wp embed handler list --fields=priority,id
+----------+-------------------+
| priority | id                |
+----------+-------------------+
| 10       | youtube_embed_url |
| 9999     | audio             |
| 9999     | video             |
+----------+-------------------+
```

### [Subcommands](#subcommands)

| Name | Description |
| --- | --- |
| [wp embed cache](https://developer.wordpress.org/cli/commands/embed-2/cache/) | Finds, triggers, and deletes oEmbed caches. |
| [wp embed fetch](https://developer.wordpress.org/cli/commands/embed-2/fetch/) | Attempts to convert a URL into embed HTML. |
| [wp embed handler](https://developer.wordpress.org/cli/commands/embed-2/handler/) | Retrieves embed handlers. |
| [wp embed provider](https://developer.wordpress.org/cli/commands/embed-2/provider/) | Retrieves oEmbed providers. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
