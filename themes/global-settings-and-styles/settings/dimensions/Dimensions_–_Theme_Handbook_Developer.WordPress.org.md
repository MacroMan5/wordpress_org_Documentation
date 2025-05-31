# Dimensions – Theme Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/themes/global-settings-and-styles/settings/dimensions/](https://developer.wordpress.org/themes/global-settings-and-styles/settings/dimensions/)  
**Last Updated:** 2025-05-24T13:58:25.855Z  
**Extracted:** 2025-05-31 16:56:23

---

# Dimensions – Theme Handbook | Developer.WordPress.org

The `settings.dimensions` property in `theme.json` gives you control over the global dimensions settings for blocks. This property lets you decide which dimension controls are available in the user interface.

In this document, you will learn what the `dimensions` property is for and how you can use it in your theme.

## [Dimensions settings](#dimensions-settings)

`dimensions` is an object that’s nested directly within the top-level `settings` property in `theme.json`. Currently, it only lets you set a single property: 

*   **`minHeight`:** A boolean value for enabling block support for the **Minimum Height** control.

Take a look at the `dimensions` property in the context of a `theme.json` file with its default values:

```
{
	"version": 2,
	"settings": {
		"dimensions": {
			"minHeight": false
		}
	}
}
```

### [Minimum Height](#minimum-height)

The `settings.dimensions.minHeight` property lets you control whether the **Minimum Height** field appears for blocks that have opted into support for the feature. As of WordPress 6.3, the only core WordPress blocks that do are Group and Post Content.

To enable support for the control, you must set the property’s value to `true` in `theme.json`:

```
{
	"version": 2,
	"settings": {
		"dimensions": {
			"minHeight": true
		}
	}
}
```

This will enable the control in the interface. As shown in this screenshot, the **Minimum Height** field appears for the Group block (Stack variation):

[![WordPress post editor with a Stack block in the content canvas. Its minimum height is set in the sidebar.](https://i0.wp.com/developer.wordpress.org/files/2023/10/group-min-height.jpg?resize=2048%2C1066&ssl=1)](https://i0.wp.com/developer.wordpress.org/files/2023/10/group-min-height.jpg?ssl=1)

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
