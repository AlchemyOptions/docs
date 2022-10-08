# Samples

Add code to your theme's `functions.php`.

## Create an options page with 2 tabs

```php
function add_custom_options_pages( $pages ) {
    $myPages = array(
        array(
            'id' => 'my-options-page',
            'name' => 'My options page',
            'tabs' => array(
                array(
                    'id' => 'main',
                    'name' => 'Main',
                ),
                array(
                    'id' => 'inner',
                    'name' => 'Inner',
                ),
            ),
        ),
    );

    return array_merge( $pages, $myPages );
}

add_filter( 'alch_options_pages', 'add_custom_options_pages' );
```

## Simple text field

The following will add a text field to the 'My options page'. If you don't specify a `tab` the field is going to render in each of them.

```php
function add_custom_options( $options ) {
    $myOptions = array(
        array(
            'id' => 'text-option',
            'type' => 'text',
            'place' => array(
                'page' => 'my-options-page',
            ),
        ),
    );

    return array_merge( $options, $myOptions );
}

add_filter( 'alch_options', 'add_custom_options' );
```

To restrict the field to a particular tab use the `tab` key.

```php
function add_custom_options( $options ) {
    $myOptions = array(
        array(
            'id' => 'text-option',
            'type' => 'text',
            'place' => array(
                'page' => 'my-options-page',
                'tab' => 'inner',
            ),
        ),
    );

    return array_merge( $options, $myOptions );
}

add_filter( 'alch_options', 'add_custom_options' );
```

## With a repeater field in one of two tabs

```php
function add_custom_repeaters( $repeaters ) {
	$myRepeaters = array(
		array(
			'id' => 'my-repeater',
			'fields' => array(
				array(
					'title' => 'My editor field',
					'id' => 'my-editor-field',
					'type' => 'editor',
				),
			),
		),
	);

	return array_merge( $repeaters, $myRepeaters );
}

add_filter( 'alch_repeaters', 'add_custom_repeaters' );


function add_custom_options( $options ) {
    $myOptions = array(
        array(
            'id' => 'text-option',
            'type' => 'text',
            'place' => array(
                'page' => 'my-options-page',
            ),
        ),
        array(
            'id' => 'repeater-option',
            'type' => 'repeater:my-repeater',
            'place' => array(
                'page' => 'my-options-page',
            ),
        ),
    );

    return array_merge( $options, $myOptions );
}

add_filter( 'alch_options', 'add_custom_options' );
```

## Network options

The config is almost exactly the same as for regular options, only you should use the `alch_network_options` action instead of `alch_options`. E.g.

```php
function add_custom_network_options( $options ) {
    $myOptions = array(
        array(
            'title' => 'My slider field title',
            'id' => 'slider-option',
            'desc' => 'Short description for the field',
            'place' => array(
                'page' => 'my-network-page',
                'tab' => 'tab-1'
            ),
            'type' => 'slider',
            'values' => array(
                'min' => 0,
                'max' => 200,
                'step' => 5,
            ),
        ),
    );

    return array_merge( $options, $myOptions );
}

add_action( 'alch_network_options', 'add_custom_network_options' );
```