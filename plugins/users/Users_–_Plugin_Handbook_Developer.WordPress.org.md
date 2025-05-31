# Users – Plugin Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/plugins/users/](https://developer.wordpress.org/plugins/users/)  
**Last Updated:** 2025-05-24T13:53:28.662Z  
**Extracted:** 2025-05-31 16:56:23

---

# Users – Plugin Handbook | Developer.WordPress.org

A _User_ is an access account with corresponding capabilities within the WordPress installation. Each WordPress user has, at the bare minimum, a username, password and email address.

Once a user account is created, that user may log in using the WordPress Admin (or programmatically) to access WordPress functions and data. WordPress stores the Users in the `users` table.

## [Roles and Capabilities](#roles-and-capabilities)

Users are assigned [roles](https://developer.wordpress.org/plugins/users/roles-and-capabilities/#roles), and each role has a set of [capabilities](https://developer.wordpress.org/plugins/users/roles-and-capabilities/#capabilities).

You can create new roles with their own set of capabilities. Custom capabilities can also be created and assigned to existing roles or new roles.

In WordPress, developers can take advantage of user roles to limit the set of actions an account can perform.

## [The Principle of Least Privileges](#the-principle-of-least-privileges)

WordPress adheres to the principal of least privileges, the practice of giving a user _only_ the privileges that are essential for performing the desired work. You should follow this lead when possible by creating roles where appropriate and checking capabilities before performing sensitive tasks.

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
