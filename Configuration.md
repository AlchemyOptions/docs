# Configuration

Make sure you've installed Alchemy Options either as a [plugin](Installation.md#using-alchemy-options-as-a-plugin) or as [part of your theme](Installation.md#using-alchemy-options-in-your-theme). Then add a function to the `init` hook in your `functions.php`. [Sample configuration objects](Samples.md) are available for a quick copy and paste.

```php
function add_custom_options() {
    if( ! class_exists( 'Alchemy_Options\Includes\Options' ) ) {
        return;
    }

    $options = array(
        'options' => array(
            /* options will go here */
        ),
    );

    new Alchemy_Options\Includes\Options( $options );
}

add_action( 'init', 'add_custom_options' );
```

That's it, just add [some options](fields/README.md) instead of `/* options will go here */` and see them appear on the Alchemy Options page.

## Grouping

If there's a need to split options into several groups, Alchemy Options has got you covered. You may add the `tabs` section to the config that looks like this:

```php
...
'tabs' => array(
    'tab-one-id' => array(
        'title' => 'Tab one'
    ),
    'tab-two-id' => array(
        'title' => 'Tab two'
    ),
)
...
```

Keys of the `tabs` array should be unique, these values will be used in configuring of each option with the `tab` key. If no `tab` key is found in each option's settings it will be rendered in each tab.

Thus, the `$options` variable from above will look like this:

```php
...
$options = array(
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
...
```

If there's a need to split options even further, there's a [`sections`](fields/sections.md) type for visual splitting of fields into togglable sections and a [`field-group`](fields/field-group.md) type to group related fields together for an easier [value retrieval](/functions/alch_get_option.md).