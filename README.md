# wp-turbolinks
WordPress Turbolinks integration

## Events
https://github.com/turbolinks/turbolinks#full-list-of-events

## Disabling Turbolinks on Specific Links
https://github.com/turbolinks/turbolinks#disabling-turbolinks-on-specific-links

## Change loader styles
Loader has a CSS class `.turbolinks-progress-bar`, without any added style to it.
Basic styles:
```CSS
.turbolinks-progress-bar {
    position: fixed;
    display: block;
    top: 0;
    left: 0;
    height: 3px;
    background: #0076ff;
    z-index: 9999;
    transition: width 300ms ease-out, 
                opacity 150ms 150ms ease-in;
                transform: translate3d(0, 0, 0);
}
```

## WordPress integration
Place `turbolinks.js` file in theme directory under js folder.
Connect file to front-end via functions.php:
```PHP
function turbolinks_js() {
	wp_enqueue_script( 'turbolinks-js', get_template_directory_uri() . '/js/turbolinks.js' );
}
add_action( 'wp_enqueue_scripts', 'turbolinks_js' );
```

Or connect via default action `wp_enqueue_scripts`.
