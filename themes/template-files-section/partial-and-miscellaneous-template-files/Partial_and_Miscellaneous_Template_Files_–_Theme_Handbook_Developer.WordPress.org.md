# Partial and Miscellaneous Template Files – Theme Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/themes/template-files-section/partial-and-miscellaneous-template-files/](https://developer.wordpress.org/themes/template-files-section/partial-and-miscellaneous-template-files/)  
**Last Updated:** 2025-05-24T13:58:52.478Z  
**Extracted:** 2025-05-31 16:56:23

---

# Partial and Miscellaneous Template Files – Theme Handbook

## [Introduction](#introduction)

Not all template files generate the entire content that will be rendered by the browser. Some template files are pulled in by other template files such as `comments.php`, `header.php`, `footer.php`, `sidebar.php` and `content-{$slug}.php`. You’ll walk through each of these template files to get an understanding of the purpose and how to build them.

The `header.php` file does exactly what you would expect.  It contains all the code that the browser will render for the header. This is a partial template file because unless a different template file calls the [template tag](https://developer.wordpress.org/themes/basics/template-tags/), `get_header()`, the browser will not render the contents of this file.

Often sites have the same header regardless of the page or post you’re on.  However, some sites have slight variations such as a secondary navigation or different banner image depending on the page. Your `header.php` file can handle all these variations if you use [conditional tags](https://developer.wordpress.org/themes/basics/conditional-tags/).

Almost all themes have a `header.php` file as the functionality and maintainability of this file pretty much demands its creation.

Below is an example of a header.php found in the twenty fifteen theme.

```
<!DOCTYPE html>
<html <?php language_attributes(); ?> class="no-js">
<head>
    <meta charset="<?php bloginfo( 'charset' ); ?>">
    <meta name="viewport" content="width=device-width">
    <link rel="profile" href="http://gmpg.org/xfn/11">
    <link rel="pingback" href="<?php bloginfo( 'pingback_url' ); ?>">
    <!--[if lt IE 9]>
    <script src="<?php echo esc_url( get_template_directory_uri() ); ?>/js/html5.js"></script>
    <![endif]-->
    <?php wp_head(); ?>
</head>
 
<body <?php body_class(); ?>>
    <div id="page" class="hfeed site">
        <a class="skip-link screen-reader-text" href="#content"><?php _e( 'Skip to content', 'twentyfifteen' ); ?></a>
        <div id="sidebar" class="sidebar">
            <header id="masthead" class="site-header" role="banner">
                <div class="site-branding">
                    <?php if ( is_front_page() && is_home() ) : ?>
                    <h1 class="site-title">
                        <a href="<?php echo esc_url( home_url( '/' ) ); ?>" rel="home"><?php bloginfo( 'name' ); ?></a>
                    </h1>
                    <?php else : ?>
                    <a href="<?php echo esc_url( home_url( '/' ) ); ?>" rel="home"><?php bloginfo( 'name' ); ?></a>
                    <?php endif;
                    $description = get_bloginfo( 'description', 'display' );
                    if ( $description || is_customize_preview() ) :
                        echo $description;
                    endif; ?>
                    <button class="secondary-toggle"><?php _e( 'Menu and widgets', 'twentyfifteen' ); ?></button>
                </div><!-- .site-branding -->
            </header><!-- .site-header -->
            <?php get_sidebar(); ?>
        </div><!-- .sidebar -->
        <div id="content" class="site-content">
```

Some of the code may look a little daunting at first, but if we break it down, it becomes simple enough. After the opening commment, the `head` is created. The template tag `wp_head()` pulls in all of our styles and any scripts that would appear in the head rather than the footer that we enqueued in our `functions.php` file.

Next, the `body` is opened and a mix of HTML and PHP are present. You can see some conditional tags in the site branding div that tweak a little bit of what is shown based on the page the user is on. Then the site navigation is pulled in. Lastly, the main site-content div is opened which will be closed most likely in the `footer.php` file.

One important template tag to note is `body_class()` found in the opening `body` tag. This is a super handy tag that makes styling your theme a lot easier by giving your body classes depending on the template file and other settings being used.

Much like the `header.php` file the `footer.php` is a very common template file that most themes utilize. The code in the `footer.php` file will not be rendered unless another template file pulls in the `footer.php` with `get_footer()` [template tag](https://developer.wordpress.org/themes/basics/template-tags/).  Similarly to headers, you can make variations of footers using [conditional tags](https://developer.wordpress.org/themes/basics/conditional-tags/).

Often developers will put [widgetized areas](https://developer.wordpress.org/themes/functionality/widgets/) in the footer so that the end user can easily drop and drag different content types into the footer.

Here is an example of a `footer.php` file from the Twenty Fifteen theme.

```
</div><!-- .site-content -->

<footer id="colophon" class="site-footer" role="contentinfo">

	<div class="site-info">

		<?php
		/**
		 * Fires before the Twenty Fifteen footer text for footer customization.
		 *
		 * @since Twenty Fifteen 1.0
		 */
		do_action( 'twentyfifteen_credits' );
		?>
		<a href="<?php echo esc_url( __( 'https://wordpress.org/', 'twentyfifteen' ) ); ?>"><?php printf( __( 'Proudly powered by %s', 'twentyfifteen' ), 'WordPress' ); ?></a>

	</div><!-- .site-info -->

</footer><!-- .site-footer -->

</div><!-- .site -->

<?php wp_footer(); ?>

</body>
</html>
```

## [404.php](#404-php)

When users try to visit a page on your website that doesn’t exist they’ll be directed to your `index.php` page unless you’ve created a 404.php template.  It’s a good idea to have some sort of message that the explains the page is missing or no longer available.  Creating this template helps keep the visual aspects of your theme consistent and provides your end users with helpful information.

Here is an example of a 404.php template file from the twenty fifteen theme.

```
<?php get_header(); ?>

<div id="primary" class="content-area">

	<main id="main" class="site-main" role="main">

		<section class="error-404 not-found">

			<header class="page-header">
				<h1 class="page-title"><?php _e( 'Oops! That page can’t be found.', 'twentyfifteen' ); ?></h1>
			</header><!-- .page-header -->

			<div class="page-content">
				<?php _e( 'It looks like nothing was found at this location. Maybe try a search?', 'twentyfifteen' ); ?>
				<?php get_search_form(); ?>
			</div><!-- .page-content -->

		</section><!-- .error-404 -->

	</main><!-- .site-main -->

</div><!-- .content-area -->

<?php get_footer(); ?>
```

The `comments.php` file handles exactly what you would expect, comments. This is a partial template that is pulled into other template files to display comments that users leave on a page or post. Several different pages and posts show comments so it makes sense to have one file that can be pulled in when needed.

The code involved in creating comments is expanded upon on the [comment template page](https://developer.wordpress.org/themes/template-files-section/partial-and-miscellaneous-template-files/comments/).

A lot of themes utilize sidebars to display widgets.  For a sidebar to work in a theme it must be registered and then a template file for the sidebar must be created.  You’ll learn more about [registering sidebars](https://developer.wordpress.org/themes/functionality/sidebars/) in a later chapter. Sidebar files often have conditional statements and the `is_active_sidebar( 'sidebar-name' )` function in them to ensure a widget is in use within the sidebar so that empty HTML isn’t added to a page unnecessarily.

Here is an example of a sidebar template file from the twenty fifteen theme. Notice at the bottom the sidebar is pulled in using `<?php dynamic_sidebar( 'sidebar-1' ); >`. Now whatever, widgets are put into that sidebar will display on the page that is using this pulling in this template.

```
<?php if ( has_nav_menu( 'primary' ) || has_nav_menu( 'social' ) || is_active_sidebar( 'sidebar-1' ) ) : ?>

	<div id="secondary" class="secondary">

		<?php if ( is_active_sidebar( 'sidebar-1' ) ) : ?>
			<div id="widget-area" class="widget-area" role="complementary">
				<?php dynamic_sidebar( 'sidebar-1' ); ?>
			</div><!-- .widget-area -->
		<?php endif; ?>

	</div><!-- .secondary -->

<?php endif; ?>
```

## [Content-{$slug}.php](#content-slug-php)

Many theme developers break their template files into small bite sized pieces.  They’ll often put wrappers and page architecture elements in template files like `page.php, home.php, comments.php` etc but then they put the code displaying the content of those pages in another template file. Enter `content-{$slug}.php`: common examples would be `content-page.php, content-post.php, content-portfolio.php, content-none.php`.  These are not file names that WordPress recognizes and will interpret a certain way, rather they are a common approach to display specific types of content.

For example, often on blog posts you want to display the author’s name, the date of the post, and possibly the category of the post.  You’d also likely have links to previous and next posts. That information wouldn’t be appropriate on a regular page. Similarly on a portfolio page you would likely have a featured image or gallery you would want to display in a way differently than say a blog post’s or page’s featured images.

You’ll want to use the `get_template_part()` [template tag](https://developer.wordpress.org/themes/basics/template-tags/) to pull in the `content-{$slug}.php` file. To pull in your `content-page.php` file you would call `get_template_part( 'content', 'page' );`

Here is twenty fifteen’s example of a `content-page.php` template file.

```
<article id="post-<?php the_ID(); ?>" <?php post_class(); ?>>

	<header class="entry-header">
		<?php the_title( '<h1 class="entry-title">', '</h1>' ); ?>
	</header><!-- .entry-header -->

	<div class="entry-content">
		<?php the_content(); ?>
		<?php
		wp_link_pages( array(
			'before'      => '<div class="page-links"><span class="page-links-title">' . __( 'Pages:', 'twentyfifteen' ) . '</span>',
			'after'       => '</div>',
			'link_before' => '<span>',
			'link_after'  => '</span>',
			'pagelink'    => '<span class="screen-reader-text">' . __( 'Page', 'twentyfifteen' ) . ' </span>%',
			'separator'   => '<span class="screen-reader-text">, </span>',
		) );
		?>
	</div><!-- .entry-content -->

	<?php edit_post_link( __( 'Edit', 'twentyfifteen' ), '<footer class="entry-footer"><span class="edit-link">', '</span></footer><!-- .entry-footer -->' ); ?>

</article><!-- #post-## -->
```

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
