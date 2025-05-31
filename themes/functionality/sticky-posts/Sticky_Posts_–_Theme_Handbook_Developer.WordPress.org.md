# Sticky Posts – Theme Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/themes/functionality/sticky-posts/](https://developer.wordpress.org/themes/functionality/sticky-posts/)  
**Last Updated:** 2025-05-24T13:56:36.278Z  
**Extracted:** 2025-05-31 16:56:23

---

# Sticky Posts – Theme Handbook

A Sticky Post is the post will be placed at the top of the front page of posts. This feature is only available for the built-in post type post and not for custom post types.

## [How to stick a post](#how-to-stick-a-post)

1.  Go to **Administration Screen > Posts > Add New** or **Edit**
2.  In the right side menu, Click Edit link of Visibility option in Publish group
3.  Click Stick this post to the front page option

![](https://i0.wp.com/developer.wordpress.org/files/2017/01/sticked_post.jpg?resize=307%2C449&ssl=1)

## [Display Sticky Posts](#display-sticky-posts)

### [Show Sticky Posts](#show-sticky-posts)

Display just the first sticky post. At least one post must be designated as a “sticky post” or else the loop will display all posts:

```
<?php
$sticky = get_option( 'sticky_posts' );
$query  = new WP_Query( 'p=' . $sticky[0] );
```

Display just the first sticky post, if none return the last post published:

```
<?php
$args  = array(
	'posts_per_page'      => 1,
	'post__in'            => get_option( 'sticky_posts' ),
	'ignore_sticky_posts' => 1,
);
$query = new WP_Query( $args );
```

Display just the first sticky post, if none return nothing:

```
<?php
$args   = array(
	'posts_per_page'      => 1,
	'post__in'            => get_option( 'sticky_posts' ),
	'ignore_sticky_posts' => 1,
);
$query  = new WP_Query( $args );
if ( isset( $sticky[0] ) ) {
	// Insert here your stuff...
}
```

### [Don’t Show Sticky Posts](#dont-show-sticky-posts)

Exclude all sticky posts from the query:

```
<?php
$args  = array( 'post__not_in' => get_option( 'sticky_posts' ) );
$query = new WP_Query( $args );
```

Exclude sticky posts from a category. Return ALL posts within the category, but don’t show sticky posts at the top. The ‘sticky posts’ will still show in their natural position (e.g. by date):

```
<?php
$args  = array(
	'ignore_sticky_posts' => 1,
	'posts_per_page'      => 3,
	'cat'                 => 6,
);
$query = new WP_Query( $args );
```

Exclude sticky posts from a category. Return posts within the category, but exclude sticky posts completely, and adhere to paging rules:

```
<?php
$args  = array(
	'cat'                 => 3,
	'ignore_sticky_posts' => 1,
	'post__not_in'        => get_option( 'sticky_posts' ),
	'paged'               => get_query_var( 'paged' ) ? get_query_var( 'paged' ) : 1,
);
$query = new WP_Query( $args );
```

Use get\_query\_var( ‘page’ ) if you want this query to work in a Page template that you’ve set as your static front page.

```
<?php
/* Get all Sticky Posts */
$sticky = get_option( 'sticky_posts' );

/* Sort Sticky Posts, newest at the top */
rsort( $sticky );

/* Get top 5 Sticky Posts */
$sticky = array_slice( $sticky, 0, 5 );

/* Query Sticky Posts */
$query = new WP_Query( array(
	'post__in'            => $sticky,
	'ignore_sticky_posts' => 1,
) );
```

## [Style Sticky Posts](#style-sticky-posts)

To help theme authors perform simpler styling, the [post\_class()](https://developer.wordpress.org/reference/functions/post_class/) function is used to add class=”…” to DIV, just add:

```
<div id="post-<?php the_ID(); ?>" <?php post_class(); ?>>
```

The [post\_class()](https://developer.wordpress.org/reference/functions/post_class/) outputs the class=”whatever” piece for that div. This includes several different classes of value: post, hentry (for hAtom microformat pages), category-X (where X is the slug of every category the post is in), and tag-X (similar, but with tags). It also adds “sticky” for posts marked as Sticky Posts.

The “sticky” class is only added for sticky posts on the first page of the home page ([is\_home()](https://developer.wordpress.org/reference/functions/is_home/) is true and [is\_paged()](https://developer.wordpress.org/reference/functions/is_paged/) is false)

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
