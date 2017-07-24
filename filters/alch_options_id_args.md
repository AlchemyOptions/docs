# alch_options_id() . '_args'

Dynamic filter `alch_options_id() . '_args'` can be used to filter the main configuration settings before saving them in the database.

## Example

```php
//somewhere in functions.php

function change_alchemy_options_arguments( $args ) {
    // do something useful with the `$args`, it will contain all of the info about `tabs`, `repeaters` and `options` that will be used to create the Alchemy Options page
    
    // do not forget to pass them further
    return $args;
}

add_filter( alch_options_id() . '_args', 'change_alchemy_options_arguments' );
```
