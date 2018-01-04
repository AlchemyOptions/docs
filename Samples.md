# Configuration object examples

Add this code to your theme's `functions.php`.

## Simplest

```php
function add_custom_options() {
    if( ! class_exists( 'Alchemy_Options\Includes\Options' ) ) {
        return;
    }

    $options = array(
        'options' => array(
            array(
                'id' => 'text-option',
                'type' => 'text',
            ),
        ),
    );

    new Alchemy_Options\Includes\Options( $options );
}

add_action( 'init', 'add_custom_options' );
```

## With two tabs - Main and Inner

```php
function add_custom_options() {
    if( ! class_exists( 'Alchemy_Options\Includes\Options' ) ) {
        return;
    }

    $options = array(
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

    new Alchemy_Options\Includes\Options( $options );
}

add_action( 'init', 'add_custom_options' );
```

## Network options

The config is almost exactly the same, only you should use the `Network_Options` class instead of `Options`. E.g.

```php
function add_custom_network_options() {
    if( ! class_exists( 'Alchemy_Options\Includes\Network_Options' ) ) {
        return;
    }

    $options = array(
        'options' => array(
            array(
                'title' => 'My text field title',
                'id' => 'text-option',
                'desc' => 'Short description for the field',
                'type' => 'text',
            ),
        ),
    );

    new Alchemy_Options\Includes\Network_Options( $options );
}

add_action( 'init', 'add_custom_network_options' );
```

## With a repeater field in one of two tabs

```php
function add_custom_repeaters() {
    if( ! class_exists( 'Alchemy_Options\Includes\Repeaters' ) ) {
        return;
    }

    $repeaters = array(
        array(
            'id' => 'my-repeater',
            'fields' => array(
                array(
                    'title' => 'My content title',
                    'desc' => 'Short description for the field',
                    'id' => 'content',
                    'type' => 'editor',
                ),
            ),
        ),
    );

    new Alchemy_Options\Includes\Repeaters( $repeaters );
}

add_action( 'init', 'add_custom_repeaters' );


function add_custom_options() {
    if( ! class_exists( 'Alchemy_Options\Includes\Options' ) ) {
        return;
    }

    $options = array(
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
                'title' => 'My repeater field title',
                'id' => 'repeater-field',
                'desc' => 'Short description for the field',
                'type' => 'repeater:my-repeater',
                'tab' => 'inner',
            ),
        ),
    );

    new Alchemy_Options\Includes\Options( $options );
}

add_action( 'init', 'add_custom_options' );
```