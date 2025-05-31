# Testing of WP-Cron – Plugin Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/plugins/cron/simple-testing/](https://developer.wordpress.org/plugins/cron/simple-testing/)  
**Last Updated:** 2025-05-24T13:48:51.858Z  
**Extracted:** 2025-05-31 16:56:23

---

# Testing of WP-Cron – Plugin Handbook

## [WP-CLI](#wp-cli)

Cron jobs can be tested using [WP-CLI](https://wp-cli.org/). It offers commands like `wp cron event list` and `wp cron event run {job name}`. [Check the documentation](https://developer.wordpress.org/cli/commands/cron/) for more details.

## [WP-Cron Management Plugins](#wp-cron-management-plugins)

[Several plugins are available on the WordPress.org Plugin Directory for viewing, editing, and controlling the scheduled cron events and available schedules on your site.](https://wordpress.org/plugins/tags/cron/)

## [\_get\_cron\_array()](#_get_cron_array)

[The `_get_cron_array()` function](https://developer.wordpress.org/reference/functions/_get_cron_array/) returns an array of all currently scheduled cron events. Use this function if you need to inspect the raw list of events.

## [wp\_get\_schedules()](#wp_get_schedules)

[The `wp_get_schedules()` function](https://developer.wordpress.org/reference/functions/wp_get_schedules/) returns an array of available event recurrence schedules. Use this function if you need to inspect the raw list of available schedules.

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
