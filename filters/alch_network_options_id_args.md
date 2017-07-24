# alch_network_options_id() . '_args'

Dynamic filter `alch_network_options_id() . '_args'` is similar to [`alch_options_id() . '_args'`](alch_options_id_args.md). It can be used to filter the main network configuration settings before saving them in the database.

## Example

```php
//somewhere in functions.php

function change_alchemy_options_network_arguments( $networkArgs ) {
    // do something useful with the `$networkArgs`, it will contain all of the info about `tabs`, `repeaters` and `options` that will be used to create the Alchemy Network Options page
    
    // do not forget to pass them further
    return $networkArgs;
}

add_filter( alch_network_options_id() . '_args', 'change_alchemy_options_network_arguments', 10, 1 );
```
