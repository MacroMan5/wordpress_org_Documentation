# Including a Software License – Plugin Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/plugins/plugin-basics/including-a-software-license/](https://developer.wordpress.org/plugins/plugin-basics/including-a-software-license/)  
**Last Updated:** 2025-05-24T13:49:33.483Z  
**Extracted:** 2025-05-31 16:56:23

---

# Including a Software License – Plugin Handbook

Most WordPress plugins are released under the [GPL](http://www.gnu.org/licenses/gpl.html), which is the same license that [WordPress itself uses](https://wordpress.org/about/license/). However, there are other compatible options available. It is always best to clearly indicate the license your plugin uses.

In the [Header Requirements](https://developer.wordpress.org/plugins/the-basics/header-requirements/) section, we briefly mentioned how you can indicate your plugin’s license within the plugin header comment. Another common, and encouraged, practice is to place a license block comment near the top of your main plugin file (the same one that has the plugin header comment).

This license block comment usually looks something like this:

```
/*
{Plugin Name} is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 2 of the License, or
any later version.

{Plugin Name} is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with {Plugin Name}. If not, see {URI to Plugin License}.
*/
```

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
