# Summary – Plugin Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/plugins/javascript/summary/](https://developer.wordpress.org/plugins/javascript/summary/)  
**Last Updated:** 2025-05-24T13:48:37.455Z  
**Extracted:** 2025-05-31 16:56:23

---

# Summary – Plugin Handbook | Developer.WordPress.org

Here are all the example code snippets from the preceding discussion, assembled into two complete code pages: one for jQuery and the other for PHP.

## [PHP](#php)

This code resides on one of your plugin pages.

```
add_action( 'admin_enqueue_scripts', 'my_enqueue' );
function my_enqueue( $hook ) {
   if ( 'myplugin_settings.php' !== $hook ) {
      return;
   }

   wp_enqueue_script(
      'ajax-script',
      plugins_url( '/js/myjquery.js', __FILE__ ),
      array( 'jquery' ),
      '1.0.0',
      true
   );

   $title_nonce = wp_create_nonce( 'title_example' );
   wp_localize_script(
      'ajax-script',
      'my_ajax_obj',
      array(
         'ajax_url' => admin_url( 'admin-ajax.php' ),
         'nonce'    => $title_nonce,
      )
   );
}

add_action( 'wp_ajax_my_tag_count', 'my_ajax_handler' );
function my_ajax_handler() {
   check_ajax_referer( 'title_example' );

   $title = wp_unslash( $_POST['title'] );

   update_user_meta( get_current_user_id(), 'title_preference', $title );

   $args = array(
      'tag' => $title,
   );

   $the_query = new WP_Query( $args );

   echo esc_html( $title ) . ' (' . $the_query->post_count . ') ';

   wp_die(); // all ajax handlers should die when finished
}
```

## [jQuery](#jquery)

This code is in the file `js/myjquery.js` below your plugin folder.

```
jQuery(document).ready(function($) { 	   //wrapper
	$(".pref").change(function() { 		   //event
		var this2 = this; 		           //use in callback
		$.post(my_ajax_obj.ajax_url, { 	   //POST request
	       _ajax_nonce: my_ajax_obj.nonce, //nonce
			action: "my_tag_count",        //action
	  		title: this.value 	           //data
  		}, function(data) {		           //callback
			this2.nextSibling.remove();    //remove the current title
			$(this2).after(data); 	       //insert server response
		});
	});
});
```

And after storing the preference, the resulting post count is added to the selected title.

## [More Information](#more-information)

*   [How To Use AJAX In WordPress](http://wp.smashingmagazine.com/2011/10/18/how-to-use-ajax-in-wordpress/ "External Site")
*   [AJAX for WordPress](http://www.glennmessersmith.com/pages/wpajax.html "External Site")

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
