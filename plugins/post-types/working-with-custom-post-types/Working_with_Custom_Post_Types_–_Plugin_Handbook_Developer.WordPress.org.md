# Working with Custom Post Types – Plugin Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/plugins/post-types/working-with-custom-post-types/](https://developer.wordpress.org/plugins/post-types/working-with-custom-post-types/)  
**Last Updated:** 2025-05-24T13:53:21.468Z  
**Extracted:** 2025-05-31 16:56:23

---

# Working with Custom Post Types – Plugin Handbook

## [Custom Post Type Templates](#custom-post-type-templates)

You can create custom [templates](https://make.wordpress.org/docs/theme-developer-handbook/theme-basics/theme-files/) for your custom post types. In the same way posts and their archives can be displayed using `single.php` and `archive.php`, you can create the templates:

*   `single-{post_type}.php` – for single posts of a custom post type
*   `archive-{post_type}.php` – for the archive

Where `{post_type}` is the post type identifier, used as the `$post_type` argument of the `register_post_type()` function.

Building upon what we’ve learned previously, you could create `single-wporg_product.php` and `archive-wporg_product.php` template files for single product posts and the archive.

Alternatively, you can use the [is\_post\_type\_archive()](https://developer.wordpress.org/reference/functions/is_post_type_archive/) function in any template file to check if the query shows an archive page of a given post type, and the [post\_type\_archive\_title()](https://developer.wordpress.org/reference/functions/post_type_archive_title/)  function to display the post type title.

## [Querying by Post Type](#querying-by-post-type)

You can query posts of a specific type by passing the `post_type` key in the arguments array of the `WP_Query` class constructor.

```
<?php
$args = array(
	'post_type'      => 'product',
	'posts_per_page' => 10,
);
$loop = new WP_Query($args);
while ( $loop->have_posts() ) {
	$loop->the_post();
	?>
	<div class="entry-content">
		<?php the_title(); ?>
		<?php the_content(); ?>
	</div>
	<?php
}
```

This loops through the latest ten product posts and displays the title and content of them one by one.

## [Altering the Main Query](#altering-the-main-query)

Registering a custom post type does not mean it gets added to the main query automatically.

If you want your custom post type posts to show up on standard archives or include them on your home page mixed up with other post types, use the `[pre_get_posts](https://developer.wordpress.org/reference/hooks/pre_get_posts/)` action hook.

The next example will show posts from `post`, `page` and `movie` post types on the home page:

```
function wporg_add_custom_post_types($query) {
	if ( is_home() && $query->is_main_query() ) {
		$query->set( 'post_type', array( 'post', 'page', 'movie' ) );
	}
	return $query;
}
add_action('pre_get_posts', 'wporg_add_custom_post_types');
```

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
