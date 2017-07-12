# Configuration

To use Alchemy Options in your theme, add a function to the `admin_init` hook in your `functions.php`. If you've used Option Tree before, this should be pretty familiar. A [sample configuration object](Sample.md) for a quick copy and paste is available.

```php
function add_custom_options() {
    if ( ! function_exists( 'alch_options_id' ) || ! is_admin() )
        return;

    $saved_settings = get_option( alch_options_id(), array() );

    $custom_settings = array(
        'tabs' => array(
            'main' => array(
                'title' => 'Main'
            ),
        ),
        'options' => array(
            /* options will go here */
        ),
    );

    /* allow settings to be filtered before saving */
    $custom_settings = apply_filters( alch_options_id() . '_args', $custom_settings );

    /* settings are not the same update the DB */
    if ( $saved_settings !== $custom_settings ) {
        update_option( alch_options_id(), $custom_settings );
    }
}

add_action( 'admin_init', 'add_custom_options' );
```

## Concept

All Alchemy Options are split into tabs. Each tab's options may further be grouped within sections.

That's it, just add [some options](fields/README.md) instead of `/* options will go here */` and see them appear on the Alchemy Options page.