# wp media – WP-CLI Command | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/cli/commands/media/](https://developer.wordpress.org/cli/commands/media/)  
**Last Updated:** 2025-05-23T01:15:16.622Z  
**Extracted:** 2025-05-31 16:56:23

---

# wp media – WP-CLI Command

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/media-command)

### [Examples](#examples)

```
# Re-generate all thumbnails, without confirmation.
$ wp media regenerate --yes
Found 3 images to regenerate.
1/3 Regenerated thumbnails for "Sydney Harbor Bridge" (ID 760).
2/3 Regenerated thumbnails for "Boardwalk" (ID 757).
3/3 Regenerated thumbnails for "Sunburst Over River" (ID 756).
Success: Regenerated 3 of 3 images.

# Import a local image and set it to be the featured image for a post.
$ wp media import ~/Downloads/image.png --post_id=123 --title="A downloaded picture" --featured_image
Imported file '/home/person/Downloads/image.png' as attachment ID 1753 and attached to post 123 as featured image.
Success: Imported 1 of 1 images.

# List all registered image sizes
$ wp media image-size
+---------------------------+-------+--------+-------+
| name                      | width | height | crop  |
+---------------------------+-------+--------+-------+
| full                      |       |        | N/A   |
| twentyfourteen-full-width | 1038  | 576    | hard  |
| large                     | 1024  | 1024   | soft  |
| medium_large              | 768   | 0      | soft  |
| medium                    | 300   | 300    | soft  |
| thumbnail                 | 150   | 150    | hard  |
+---------------------------+-------+--------+-------+

# Fix orientation for specific images.
$ wp media fix-orientation 63
1/1 Fixing orientation for "Portrait_6" (ID 63).
Success: Fixed 1 of 1 images.
```

### [Subcommands](#subcommands)

| Name | Description |
| --- | --- |
| [wp media fix-orientation](https://developer.wordpress.org/cli/commands/media/fix-orientation/) | Fix image orientation for one or more attachments. |
| [wp media image-size](https://developer.wordpress.org/cli/commands/media/image-size/) | Lists image sizes registered with WordPress. |
| [wp media import](https://developer.wordpress.org/cli/commands/media/import/) | Creates attachments from local files or URLs. |
| [wp media regenerate](https://developer.wordpress.org/cli/commands/media/regenerate/) | Regenerates thumbnails for one or more attachments. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
