# Suggesting text for the site privacy policy – Plugin Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/plugins/privacy/suggesting-text-for-the-site-privacy-policy/](https://developer.wordpress.org/plugins/privacy/suggesting-text-for-the-site-privacy-policy/)  
**Last Updated:** 2025-05-24T13:50:15.479Z  
**Extracted:** 2025-05-31 16:56:23

---

# Suggesting text for the site privacy policy – Plugin Handbook

Every plugin that collects, uses, or stores user data, or passes it to an external source or third party, should add a section of suggested text to the privacy policy postbox. This is best done with `wp_add_privacy_policy_content( $plugin_name, $policy_text )`. This will allow site administrators to pull that information into their site’s privacy policy.

To make this simpler for the users, the text should address the questions provided in the default privacy policy:

*   What personal data we collect and why we collect it
    *   Their own manually input information
    *   WP: Contact forms
    *   WP: Comments
    *   WP: Cookies
    *   WP: Third party embeds
    *   Analytics
*   Who we share your data with
*   How long we retain your data
*   What rights you have over your data
*   Where we send your data
*   Your contact information
*   How we protect your data
*   What data breach procedures we have in place
*   What third parties we receive data from
*   What automated decision making and/or profiling we do with user data
*   Any industry regulatory disclosure requirements

While not all of these questions will be applicable to all plugins, we recommend taking care with the sections on data sharing.

## Code Example

It is recommended to call wp\_add\_privacy\_policy\_content during the admin\_init action. Calling it outside of an action hook can lead to problems, see ticket #44142 for details.

Supplemental information can be provided through the use of the specialized `.privacy-policy-tutorial` CSS class. Any content contained within HTML elements that have this CSS class applied will be omitted from the clipboard when the section content is copied.

```
/**
 * Adds a privacy policy statement.
 */
function wporg_add_privacy_policy_content() {
	if ( ! function_exists( 'wp_add_privacy_policy_content' ) ) {
		return;
	}
	$content = '<p class="privacy-policy-tutorial">' . __( 'Some introductory content for the suggested text.', 'text-domain' ) . '</p>'
			. '<strong class="privacy-policy-tutorial">' . __( 'Suggested Text:', 'my_plugin_textdomain' ) . '</strong> '
			. sprintf(
				__( 'When you leave a comment on this site, we send your name, email address, IP address and comment text to example.com. Example.com does not retain your personal data. The example.com privacy policy is <a href="%1$s" target="_blank">here</a>.', 'text-domain' ),
				'https://example.com/privacy-policy'
			);
	wp_add_privacy_policy_content( 'Example Plugin', wp_kses_post( wpautop( $content, false ) ) );
}

add_action( 'admin_init', 'wporg_add_privacy_policy_content' );
```

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
