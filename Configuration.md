# Configuration

To use Alchemy Options in your theme, add a function to the `admin_init` hook in your `functions.php`. If you've used Option Tree before, this should be pretty familiar. A [sample configuration object](Sample.md) for a quick copy and paste is available.

```php
function add_custom_options() {
    if ( ! function_exists( 'alch_options_id' ) || ! is_admin() )
        return;

    $saved_settings = get_option( alch_options_id(), array() );

    $custom_settings = array(
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

That's it, just add [some options](fields/README.md) instead of `/* options will go here */` and see them appear on the Alchemy Options page.

## Grouping

If there's a need to split options into several groups, Alchemy Options has got you covered. You may add the `tabs` section to the config that looks like this:

```php
'tabs' => array(
    'tab-one-id' => array(
        'title' => 'Tab one'
    ),
    'tab-two-id' => array(
        'title' => 'Tab two'
    ),
)
```

Keys of the `tabs` array should be unique, these values will be used in configuring of each option with the `tab` key. If no `tab` key is found in each option's settings it will be rendered in each tab.

Thus, the `$custom_settings` variable from above will look like this:

```php
$custom_settings = array(
    'tabs' => array(
        'tab-one-id' => array(
            'title' => 'Tab one'
        ),
        'tab-two-id' => array(
            'title' => 'Tab two'
        ),
    ),
    'options' => array(
      /* options will go here */
    )
);
```

If there's a need to split options even further, there's a `sections` type for that.