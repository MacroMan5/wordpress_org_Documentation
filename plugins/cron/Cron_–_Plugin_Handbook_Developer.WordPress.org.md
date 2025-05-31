# Cron – Plugin Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/plugins/cron/](https://developer.wordpress.org/plugins/cron/)  
**Last Updated:** 2025-05-24T13:48:53.464Z  
**Extracted:** 2025-05-31 16:56:23

---

# Cron – Plugin Handbook | Developer.WordPress.org

## [What is WP-Cron](#what-is-wp-cron)

WP-Cron is how WordPress handles scheduling time-based tasks in WordPress. Several WordPress core features, such as checking for updates and publishing scheduled post, utilize WP-Cron. The “Cron” part of the name comes from the cron time-based task scheduling system that is available on UNIX systems.

WP-Cron works by checking, on every page load, a list of scheduled tasks to see what needs to be run. Any tasks due to run will be called during that page load.

WP-Cron does not run constantly as the system cron does; it is only triggered on page load.

Scheduling errors could occur if you schedule a task for 2:00PM and no page loads occur until 5:00PM.

## [Why use WP-Cron](#why-use-wp-cron)

*   WordPress core and many plugins need a scheduling system to perform time-based tasks. However, many hosting services are shared and do not provide access to the system scheduler.
*   Using the WordPress API is a simpler method for setting scheduled tasks than going outside of WordPress to the system scheduler.
*   With the system scheduler, if the time passes and the task did not run, it will not be re-attempted. With WP-Cron, all scheduled tasks are put into a queue and will run at the next opportunity (meaning the next page load). So while you can’t be 100% sure _when_ your task will run, you can be 100% sure that it will run _eventually_.

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
