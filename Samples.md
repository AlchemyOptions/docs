# Configuration object examples

Add this code to your theme's `functions.php`.

## Simplest

```php
function add_custom_options() {
    if ( ! function_exists( 'alch_options_id' ) || ! is_admin() )
        return;

    $saved_settings = get_option( alch_options_id(), array() );

    $custom_settings = array(
        'options' => array(
            array(
                'id' => 'text-option',
                'type' => 'text',
            ),
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

## With two tabs - Main and Inner

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
            'inner' => array(
                'title' => 'Inner'
            ),
        ),
        'options' => array(
            array(
                'title' => 'My text field title',
                'id' => 'text-option',
                'desc' => 'Short description for the field',
                'tab' => 'main',
                'type' => 'text',
            ),
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

## Network options

The config is almost exactly the same, only you should use `alch_network_options_id` instead of `alch_options_id`. E.g.

```php
function add_custom_network_options() {
    if ( ! function_exists( 'alch_network_options_id' ) || ! is_admin() )
        return;

    $saved_settings = get_option( alch_network_options_id(), array() );

    $custom_settings = array(
        'options' => array(
            array(
                'title' => 'My text field title',
                'id' => 'text-option',
                'desc' => 'Short description for the field',
                'type' => 'text',
            ),
        ),
    );

    /* allow settings to be filtered before saving */
    $custom_settings = apply_filters( alch_network_options_id() . '_args', $custom_settings );

    /* settings are not the same update the DB */
    if ( $saved_settings !== $custom_settings ) {
        update_option( alch_network_options_id(), $custom_settings );
    }
}

add_action( 'admin_init', 'add_custom_network_options' );
```