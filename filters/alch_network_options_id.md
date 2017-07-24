# alch_network_options_id

Filter `alch_network_options_id` is similar to [`alch_options_id`](alch_options_id.md). It can be used to change the default network configuration option name, which is `alchemy_network_options`.

## Example

```php
//somewhere in functions.php

function change_default_alchemy_options_network_option() {
    return 'my-new-network-options-id';
}

add_filter( 'alch_network_options_id', 'change_default_alchemy_options_network_option' );
```

Thus, the Alchemy Options will get the new ID when it calls the [`alch_network_options_id` function](/functions/alch_network_options_id.md).